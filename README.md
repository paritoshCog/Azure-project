# Azure-project
Creating azure project using data factory and databricks for practice

Welcome to the Azure-project

1. Azure Architecture diagram
![Screenshot (28)](https://github.com/paritoshCog/Azure-project/assets/128465174/6a735cc3-b64d-4d22-8ca1-9bf1dd6426b5)

Its a practice project in which I have learn Azure datafactory for ingestion, azure datalake gen 2 for storage, azure databricks for transformation, azure synapse analytics for analysis. I have uploaded the screenshot of the azure portal. In this project, Firstly I have created the storage account then create two containers which are Raw data and Transformed data. I have used Azure data factory to collect data from source. In this project I take data from git-hub which I have downloaded from the Kaggle i.e. Tokyo-Olympic. The data is in .CSV format. I created pipeline line in azure data factory where http format is the source. I put the data into the Raw container. I use the azure Databricks service to transform the raw data. I setup the connection of raw container with azure Databricks(The codes are uploaded in the repository). After the basic transformation in azure Databricks, uploaded the data into the transformed container.

There are few ways to connect storage account with databricks:
1. using accessing keys, but its not an efficient way
2. using SAS(shared access signature) tokens, restrict for specific time, allow specific permission, limited access to private keys. Recommended for external client.
   * we can generate SAS token withing specific container and provide specific permissions like read, write....

**spark.conf.set("fs.azure.account.auth.type.<storage-account>.dfs.core.windows.net", "SAS")
spark.conf.set("fs.azure.sas.token.provider.type.<storage-account>.dfs.core.windows.net", "org.apache.hadoop.fs.azurebfs.sas.FixedSASTokenProvider")
spark.conf.set("fs.azure.sas.fixed.token.<storage-account>.dfs.core.windows.net", "<sas-token-key>")

dbutils.fs.ls("abfss://<container>@<storageaccountname>.dfs.core.windows.net")
**
  
4. using service principle
5. by creating key vault.
  * create azure key vault, add secrets to key vault ---> create databricks secret scope ---> get secret using dbutils.secrets.get (access notbook/cluster/jos)
  * create secret scope by adding #/secrets/createScope in dashboard URL --> configure the scope --> put DNS name and Resource ID of azure key vault.
  * DNS name (vault URI) and Resource ID is available in the azure key vault properties.

**    --> var = dbutils.secrets.get(scope = "<scope_name>", key = "<key_name>"   // we will assign the value to a variable then use it as secrete key
    --> spark.conf.set("fs.azure.account.key.<storage-account>.dfs.core.windows.net", var)**

-1. access key of storage account 

![Screenshot (36)](https://github.com/paritoshCog/Azure-project/assets/128465174/e6fd93f1-3e07-4944-a50b-2cb2669323ba)


0. Screenshot of databricks
   
![Screenshot (35)](https://github.com/paritoshCog/Azure-project/assets/128465174/a0155dbe-7c4b-4240-8b16-f855c87f525b)


All the steps are can be done with the help of azure synapse analytics, all the services are already integrated in the azure synapse analytics like Datafactory, Databricks, SQL etc.

I use azure synapse analytics to use SQL on the data.

2. Data pipeline in azure datafactory

![Screenshot (29)](https://github.com/paritoshCog/Azure-project/assets/128465174/00ce36ae-abe2-4cea-87fb-91ae67b8616b)


3. Azure datalake gen 2

![Screenshot (30)](https://github.com/paritoshCog/Azure-project/assets/128465174/d5fa9401-7dcd-4757-90ee-836ce3d371e7)


4. Azure dashboard (resources)


![Screenshot (31)](https://github.com/paritoshCog/Azure-project/assets/128465174/b62970f0-77be-415d-86ad-8cb14ac5842f)


5. Azure synapse analytics


![Screenshot (33)](https://github.com/paritoshCog/Azure-project/assets/128465174/49efc057-1e13-4006-937a-02a8b8efbaac)





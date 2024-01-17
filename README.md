# Azure-project
Creating azure project using data factory and databricks for practice

Welcome to the Azure-project

1. Azure Architecture diagram
![Screenshot (28)](https://github.com/paritoshCog/Azure-project/assets/128465174/6a735cc3-b64d-4d22-8ca1-9bf1dd6426b5)

Its a practice project in which I have learn Azure datafactory for ingestion, azure datalake gen 2 for storage, azure databricks for transformation, azure synapse analytics for analysis. I have uploaded the screenshot of the azure portal. In this project, Firstly I have created the storage account then create two containers which are Raw data and Transformed data. I have used Azure data factory to collect data from source. In this project I take data from git-hub which I have downloaded from the Kaggle i.e. Tokyo-Olympic. The data is in .CSV format. I created pipeline line in azure data factory where http format is the source. I put the data into the Raw container. I use the azure Databricks service to transform the raw data. I setup the connection of raw container with azure Databricks(The codes are uploaded in the repository). After the basic transformation in azure Databricks, uploaded the data into the transformed container.

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





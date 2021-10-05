az login

az account set --subscription "6bb00255-5486-4db1-96ca-5baefc18b0b2"

az configure --defaults group=Test-AzureGovernance

az bicep build --file main.bicep --outfile azuredeploy.json

az ts create --name ToyCosmosDBAccount --location westus --display-name "Cosmos DB account" --description "This template spec creates a Cosmos DB account that meets our company's requirements." --version 1.0 --template-file azuredeploy.json
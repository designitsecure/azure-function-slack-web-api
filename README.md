# azure-function-slack-web-api

This repo demonstrates a problem with slack/web-api 7.8.0 when running in an azure function.

## Create supporting azure resources for the function
1. Login to azure
```
az login
```
2. Copy the `.env-sample` file to `.env` and edit as needed
3. Run the `scripts/create-azure-resources.sh` script

## Tets the function locally
Get the $AZURE_STORAGE_ACCOUNT connection string and set it as the value of `AzureWebJobsStorage` in the `local.settings.json` file.  
Start the vscode debugger `Attach to Node Functions`.  

Hit the local URL with your web browser. Observe the slack message is sent to the channel.  

## Deploy the function
```
func azure functionapp publish $AZURE_FUNCTION_APP
```

Hit the local URL with your web browser. Observe the slack message is not sent to the channel.  
# acumatica-hackathon-2023

Github Action leveraging Acumatica's REST API for publishing customizations.

## REST API
### Login

https://{{baseUrl}}/entity/auth/login

```json
{
"name" : "githubservice",
"password" : "Theta",
"company" : "Company",
"branch" : ""
}
```

### Import

https://{{baseUrl}}/CustomizationApi/Import
```json
{
    "projectLevel": 1,
    "isReplaceIfExists": true,
    "projectName": "ThetaHackathon",
    "projectDescription": "Customization Project for Team Theta",
    "projectContentBase64": "UEsDBBQAAAAIAHaHOFaekXSEuWEAAB6BAAALAAAA ..."
}
```

### Check Project Validation
https://{{baseUrl}}/CustomizationApi/publishBegin

```json
{
    "isMergeWithExistingPackages": false,
    "isOnlyValidation": true,
    "isOnlyDbUpdates": false,
    "isReplayPreviouslyExecutedScripts": false,
    "projectNames": [ "ThetaHackathon" ],
    "tenantMode": "Current"
}
```

To check the status of a validation or publication, use publishEnd endpoint.  You may need to check periodically every 30 seconds to see if the isComplete flag is true. <br />
https://hackathon.acumatica.com/Theta/CustomizationApi/publishEnd

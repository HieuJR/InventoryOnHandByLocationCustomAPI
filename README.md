# Inventory On Hand By Location Custom API

This repository contains the code and resources for the **Inventory On Hand By Location Custom API**. The project simply expose the custom Inventory On Hand By Location Entity in Dynamics 365 Finance and Operations.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Managing inventory across multiple locations can be a complex task, especially when there is a lack of access to inventory on hand information by API. The Inventory On Hand By Location Custom API aims to simplify this process by providing a custom Inventory On Hand By Location Entity that allows users to retrieve inventory data in Dynamics 365 Finance and Operations using OData.

## Features

- **Inventory On Hand Management**: Users can access the Inventory On Hand data in Dynamics 365 Finance and Operations using OData.

## Installation

- Similar to the other Dynamics FO custom projects


## Usage

Once the project is built and synced, you can use the following steps to get started:

- Prequisites: Please follow these steps to collect CLIENT_ID, CLIENT_SECRET, TENANT_ID.

- Go to https://portal.azure.com/. From the Home menu, navigate to 'App Registrations' to locate the appropriate applications.
  ![PiSYKBSdiS](https://github.com/HieuJR/InventoryOnHandByLocationCustomAPI/assets/105049467/58357796-3540-46c0-929c-b0b09243f7be)

1. Make sure you have an access token to access the following APIs.
  - Input:
  ```
   curl --location --globoff 'https://login.microsoftonline.com/{{TENENT_ID}}/oauth2/token' \
   --header 'Content-Type: application/x-www-form-urlencoded' \
   --data-urlencode 'resource={{DYNAMICS365_BASEURL}}' \
   --data-urlencode 'client_id={{CLIENT_ID}}' \
   --data-urlencode 'client_secret={{CLIENT_SECRET}}' \
   --data-urlencode 'grant_type=client_credentials' \
   --data-urlencode 'ternant_id={{TENANT_ID}}'
  ```
  - Output:
  ```json
  {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1684751997",
    "not_before": "1684748097",
    "resource": "{{DYNAMICS365_BASEURL}}",
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIng1dCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiJodHRwczovL2hleGFzeW5jZm9zYW5kYm94MzBhYjA1YjIzZTg2ZDgzMGFvcy5heGNsb3VkLmR5bmFtaWNzLmNvbS8iLCJpc3MiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC9lZTdmOTk5MS04OGYxLTRlMzUtYjJjMS0xOGM0ZTUxYTQ2OTgvIiwiaWF0IjoxNjg0NzQ4MDk3LCJuYmYiOjE2ODQ3NDgwOTcsImV4cCI6MTY4NDc1MTk5NywiYWlvIjoiRTJaZ1lCRGpVNXd5dVZ2cGM3dDFnT0VxRnpWYkFBPT0iLCJhcHBpZCI6IjYwODQwMDdjLTEwOGMtNDcxMi1hMmY2LTE0OGVhNzhiOGZiMiIsImFwcGlkYWNyIjoiMSIsImlkcCI6Imh0dHBzOi8vc3RzLndpbmRvd3MubmV0L2VlN2Y5OTkxLTg4ZjEtNGUzNS1iMmMxLTE4YzRlNTFhNDY5OC8iLCJvaWQiOiI4NTJmYmIyZC02ZDAwLTRjYTMtOWY1OS0yYTFkYmFkMjAwYWIiLCJyaCI6IjAuQVNvQWtabF83dkdJTlU2eXdSakU1UnBHbUJVQUFBQUFBQUFBd0FBQUFBQUFBQUFxQUFBLiIsInJvbGVzIjpbIkNvbm5lY3Rvci5GdWxsQWNjZXNzIl0sInN1YiI6Ijg1MmZiYjJkLTZkMDAtNGNhMy05ZjU5LTJhMWRiYWQyMDBhYiIsInRpZCI6ImVlN2Y5OTkxLTg4ZjEtNGUzNS1iMmMxLTE4YzRlNTFhNDY5OCIsInV0aSI6IjN5WmRHcHY2azBPcUhUcGVCX2dTQUEiLCJ2ZXIiOiIxLjAifQ.bLzXrXAufhWtpgSfVUdkhomIVOqM0yF6uCoCZWgvygMGyG8NgrzcrDrbxdTSgC_Lv0TMJZj9fbxJN3RIJ_DeYo9J-sF1d558sO9TtMsrd9cB0hFvvk_SzdTTT4jtLbshZi69cPqh04WJmlaMLQVKkDB_ZrpXZ78fYJosk8fBSZeKayJ0uzhU72x1_jnre36Me6EQXmsm0eNNvnSScd_ozGTkGmmuGRIHJXicQYcwDS6H1bP8xHWJLEo0aK-sLb_jxm0xP-hCP39J1e-hCjy81Bv95G3FbW58OuAJDMyV69bYDyiMHjhjbg48TvbJVZHYHBve90vzlLB0eS9FsjjdUA"
}
  ```
![Postman_oOahWkOvKl](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/e3f36d04-8b63-47fe-85aa-5ad796d50a70)

2. Test if the entity has data or not.
- Input:
   ```
   curl --location '{{DYNAMICS365_BASEURL}}/data/' \
   --header 'Authorization: Bearer {{MS_ACCESS_TOKEN}}'
   ```
- Output:
  ```json
  {
    "@odata.context": "{{DYNAMICS365_BASEURL}}/data/$metadata",
    "value": [
         {
            "name": "InventoryOnHandByLocations",
            "kind": "EntitySet",
            "url": "InventoryOnHandByLocations"
        },
        {
            "name": "PaymentOrderTypes",
            "kind": "EntitySet",
            "url": "PaymentOrderTypes"
        },
        {
            "name": "RecruitingRequestSkills",
            "kind": "EntitySet",
            "url": "RecruitingRequestSkills"
        },
        {
            "name": "TaxCodeLimits",
            "kind": "EntitySet",
            "url": "TaxCodeLimits"
        },
        {
            "name": "BenefitsWorkerAnnualSalaries",
            "kind": "EntitySet",
            "url": "BenefitsWorkerAnnualSalaries"
        },
        {
            "name": "LeaseBookGroupRelations",
            "kind": "EntitySet",
            "url": "LeaseBookGroupRelations"
        },
        {
            "name": "BudgetReservationTypes",
            "kind": "EntitySet",
            "url": "BudgetReservationTypes"
        },
        {
            "name": "ProductionOrderHeaders",
            "kind": "EntitySet",
            "url": "ProductionOrderHeaders"
        },
        {
            "name": "VendInvoiceRegisterHeaders",
            "kind": "EntitySet",
            "url": "VendInvoiceRegisterHeaders"
        },
        {
            "name": "DeliveryModeChannelLines",
            "kind": "EntitySet",
            "url": "DeliveryModeChannelLines"
        },
        {
            "name": "AgreementTerms",
            "kind": "EntitySet",
            "url": "AgreementTerms"
        },
        {
            "name": "RetailMediaProductRelations",
            "kind": "EntitySet",
            "url": "RetailMediaProductRelations"
        }
        ]
   }
  ```
   
  ![Postman_mrjqe5EghN](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/afef51af-a0f1-44fb-a2d7-10ae9e02b4bf)

3. Test if the entity has data or not.
- Input:
   ```
     curl --location '{{DYANMICS365_BASEURL}}//data/InventoryOnHandByLocations%24filter=InventLocationId%20eq%20%27TEST%27%20and%20dataAreaId%20eq%20%27usrt%27&%24top=10' \
   --header 'Authorization: Bearer {{MS_ACCESS_TOKEN}}'
   ```
- Output:
   ```json
   {
    "@odata.context": "https://hexasyncfosandbox30ab05b23e86d830aos.axcloud.dynamics.com/data/$metadata#InventoryOnHandByLocations",
    "value": [
        {
            "@odata.etag": "W/\"JzE4NjMxNzAwNDIsNjg3MTk2MzgxOTcn\"",
            "dataAreaId": "usrt",
            "ItemId": "0021",
            "InventDimId": "#0000001000017152",
            "InventDimension6": "",
            "PdsCWPhysicalInvent": 0,
            "wMSPalletId": "",
            "InventProfileId_RU": "",
            "InventDimension7": "",
            "InventDimension2": "",
            "InventDimension9": "1900-01-01T00:00:00Z",
            "Registered": 0,
            "QuotationReceipt": 0,
            "InventSizeId": "",
            "InventDimension10": 0,
            "InventDimension11": "",
            "InventDimension12": "",
            "InventDimension3": "",
            "PdsCWArrived": 0,
            "OnOrder": 0,
            "PhysicalInvent": 9,
            "PdsCWQuotationReceipt": 0,
            "Deducted": 0,
            "PdsCWPostedQty": 0,
            "PdsCWReservOrdered": 0,
            "InventStatusId": "",
            "configId": "",
            "ReservPhysical": 0,
            "PdsCWQuotationIssue": 0,
            "ReservOrdered": 0,
            "IsExcludedFromInventoryValue": "No",
            "PdsCWPicked": 0,
            "PhysicalValueSecCur_RU": 0,
            "Closed": "No",
            "InventColorId": "",
            "ClosedQty": "No",
            "PdsCWRegistered": 0,
            "PdsCWOnOrder": 0,
            "InventDimension8": "",
            "LastUpdDateExpected": "2023-05-15T12:00:00Z",
            "InventSiteId": "CENTRAL",
            "InventLocationId": "TEST",
            "PostedValue": 237.51,
            "PhysicalValue": 0,
            "InventGtdId_RU": "",
            "PdsCWDeducted": 0,
            "AvailOrdered": 9,
            "Arrived": 0,
            "Ordered": 0,
            "LastUpdDatePhysical": "2023-05-15T12:00:00Z",
            "PdsCWOrdered": 0,
            "InventDimension4": "",
            "wMSLocationId": "",
            "AvailPhysical": 9,
            "PostedQty": 9,
            "InventStyleId": "",
            "PostedValueSecCur_RU": 0,
            "PdsCWAvailPhysical": 0,
            "InventDimension5": "",
            "PdsCWAvailOrdered": 0,
            "InventBatchId": "",
            "PdsCWReceived": 0,
            "LicensePlateId": "",
            "Received": 0,
            "InventDimension1": "",
            "Picked": 0,
            "InventSerialId": "",
            "PdsCWReservPhysical": 0,
            "QuotationIssue": 0,
            "InventOwnerId_RU": "",
            "InventVersionId": ""
        },
        {
            "@odata.etag": "W/\"JzE1MTI0NDc0MDksNjg3MTk2MzgxOTgn\"",
            "dataAreaId": "usrt",
            "ItemId": "test01",
            "InventDimId": "#0000001000017156",
            "InventDimension6": "",
            "PdsCWPhysicalInvent": 0,
            "wMSPalletId": "",
            "InventProfileId_RU": "",
            "InventDimension7": "",
            "InventDimension2": "",
            "InventDimension9": "1900-01-01T00:00:00Z",
            "Registered": 0,
            "QuotationReceipt": 0,
            "InventSizeId": "",
            "InventDimension10": 0,
            "InventDimension11": "",
            "InventDimension12": "",
            "InventDimension3": "",
            "PdsCWArrived": 0,
            "OnOrder": 0,
            "PhysicalInvent": 58,
            "PdsCWQuotationReceipt": 0,
            "Deducted": 0,
            "PdsCWPostedQty": 0,
            "PdsCWReservOrdered": 0,
            "InventStatusId": "",
            "configId": "",
            "ReservPhysical": 0,
            "PdsCWQuotationIssue": 0,
            "ReservOrdered": 0,
            "IsExcludedFromInventoryValue": "No",
            "PdsCWPicked": 0,
            "PhysicalValueSecCur_RU": 0,
            "Closed": "No",
            "InventColorId": "",
            "ClosedQty": "No",
            "PdsCWRegistered": 0,
            "PdsCWOnOrder": 0,
            "InventDimension8": "",
            "LastUpdDateExpected": "2023-05-15T12:00:00Z",
            "InventSiteId": "CENTRAL",
            "InventLocationId": "TEST",
            "PostedValue": 986,
            "PhysicalValue": 0,
            "InventGtdId_RU": "",
            "PdsCWDeducted": 0,
            "AvailOrdered": 58,
            "Arrived": 0,
            "Ordered": 0,
            "LastUpdDatePhysical": "2023-05-15T12:00:00Z",
            "PdsCWOrdered": 0,
            "InventDimension4": "",
            "wMSLocationId": "DC",
            "AvailPhysical": 58,
            "PostedQty": 58,
            "InventStyleId": "",
            "PostedValueSecCur_RU": 0,
            "PdsCWAvailPhysical": 0,
            "InventDimension5": "",
            "PdsCWAvailOrdered": 0,
            "InventBatchId": "",
            "PdsCWReceived": 0,
            "LicensePlateId": "",
            "Received": 0,
            "InventDimension1": "",
            "Picked": 0,
            "InventSerialId": "",
            "PdsCWReservPhysical": 0,
            "QuotationIssue": 0,
            "InventOwnerId_RU": "",
            "InventVersionId": ""
        }
    ]
    }
   ```
![Postman_0Mw4o6KkBR](https://github.com/HieuJR/InventoryOnHandByLocationEntityProject/assets/105049467/d6fed7c8-0514-4d68-848e-2db796122bc7)

## Contributing

Contributions to the Inventory On Hand By Location Custom API are welcome! If you would like to contribute, please follow these steps:

1. Fork the repository on GitHub.

2. Create a new branch with a descriptive name for your feature or bug fix.

3. Implement your changes, adhering to the project's coding guidelines and best practices.

4. Commit and push your changes to your forked repository.

5. Submit a pull request, explaining the purpose and details of your contribution.

6. Wait for feedback and address any requested changes or questions.

Please note that all contributions are subject to review and acceptance by the project maintainers.

## License

Feel free to modify and distribute the codebase as per the terms of this license. Please contact trung.hieu@beehexa.com if you have any questions

[<< Back to HOME](README.md)

1. [Login](#login)
2. [Get Customers](#get-customers)

## Login

#### To call server APIs a token is required. To get this token using the below mentioned login API

We will share the `email` and `password` with you.

Login API retruns a `token` which you can use in rest of the APIs 

    /login [POST]
    
HEADER

    Content-Type:application/json
    
BODY
```javascript
{
  "email": "string",  // required
  "password": "string" // required
}
```

RESPONSE - code - 200
```javascript
{
  "result": {
    "token": <authToken>,
    "user": {UserModel}
  },
  "name": null,
  "code": null,
  "message": null  
}
```

## Get customers

API fetches customers list

    /pdn/customer [GET]

HEADER

    Content-Type:application/json
    status=1          // optional 1 for ACTIVE and 2 for INACTIVE
    Authorization : Bearer <token>
 
BODY
    
    NA
    
RESPONSE - code - 200
```javascript
{
  "result": [
    {
      "customerId": 32,
      "custName": "Maruti Suzuki",
      "customerUId": "MARUTISUZUKI",
      "contactNo": "9876543210",
      "pointOfContact": 24,
      "pointOfContactEmail": "abc@xyz.com",
      "pointOfContactName": "Jane Doe",
      "pointOfContactStatus": 1,
      "countryCode": "+1",
      "mobile": "XXXXXX",
      "address": "1089/A, Old Palam Gurgaon Road, Chakkarpur, Gurugram, Haryana 122001",
      "status": 1,
      "numberOfApproverLevel": 1,
      "createdOn": "1517824357000",
      "modifiedOn": "1517824357000",
      "numberOfDevices": 50,
      "consumedNumberOfDevices": 34,
      "licenceStartDate": "1517824357000",
      "licenceEndDate": "1517824357000",
      "approvalWorkFlow": "LAYOUT | LAYOUT_STRING | PLANOGRAM | PLANOGRAM_AND_LAYOUT | NONE",
      "isCustomerOnboarded": true,
      "alternatePhoneNumber": "XXXXXX",
      "contactNoCountryCode": "+1",
      "alternateNumberCountryCode": "+1",
      "uniqueCustomerIdMask": "AB6C3",
    }
  ],
  "name": null,
  "code": 20,
  "message": null
}
```

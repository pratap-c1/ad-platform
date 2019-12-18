[<< Back to HOME](README.md)

1. [Login](#login)
2. [Get Customers](#get-customers)
3. [Get Devices for PDN](#get-devices-for-pdn)

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
## Get Devices for PDN

    /pdn/device [GET]

QUERY

    status=1         // optional 1 for ACTIVE and 2 for INACTIVE

HEADER

    Authorization : Bearer <token>
    customerId : <customerId>


BODY

    NA

RESPONSE - code - 200
```javascript
{
  "result": [
    {
      "deviceId": 143,
      "clientGeneratedDeviceIdentifier": "77eaea49-a768-43e1-9446-e4ec76457c2f",
      "deviceName": "Cool Device",
      "deviceGroupId": 129,
      "deviceGroupName": "Cafeteria",
      "locationId": 82,
      "location": {
        "locationId": 82,
        "locationName": "Noida"
      },
      "deviceOs": "ANDROID|WINDOWS",
      "deviceWifiMacAddress": "fc:67:36:f6:a3:7e",
      "deviceEthernetMacAddress": "ac:e5:36:f6:7e:a3",
      "isAudioEnabled": "ON",
      "localServerIP": "192.168.0.54",
      "status": 1,
      "lastSyncTime": 156834993032,
      "lastAccess": 156834993032,
      "aspectRatioId": 12,
      "isManuallyAdded": true,
      "panels": [
        {
          "panelId": 132,
          "isAudioEnabled": "OFF",
          "panelStatus": "ON_HDMI_CONNECTED",
          "panelIp": "192.168.0.56",
          "deviceId": 323,
          "panelName": "First floor lobby",
          "panelSerialNumber": "SR445X4454",
          "status": 1,
          "timeOfPanelStatus": 156834993032,
          "panelActivityStatus": "ON",
          "hdmiActivityStatus": "CONNECTED",
          "panelControl": "RJ45"
        }
      ],
      "deviceConnectivity": "CONNECTED",
      "timeOfDeviceStatus": 156834993032,
      "inActiveTime": 156834993032,
      "appVersion": "2.5443.53",
      "camera": {
        "cameraId": 12,
        "deviceId": 143,
        "cameraType": "USB",
        "cameraIp": "192.168.23.55",
        "cameraPurpose": "ONLY_COLLECT_DATA"
      }
    }
  ],
  "name": null,
  "code": 20,
  "message": null
}
```

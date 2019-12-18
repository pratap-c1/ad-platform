[<< Back to HOME](README.md)

1. [Login](#login)
2. [Get Customers](#get-customers)
3. [Get Devices](#get-devices)
4. [Get Layout by ID](#get-layout-by-id)

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
## Get Devices

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

## Get Layout by ID

    /pdn/layout/<layoutId> [GET]

QUERY

    NA
    
HEADER

    Authorization : Bearer <token>
    customerId : <customerId>

BODY

    NA

RESPONSE - code - 200
```javascript
{
  "result": {
    "layoutId": 1232,
    "layoutName": "Cool Layout",
    "isPendingForApporval": true,
    "layoutDescription": "Layout description",
    "aspectRatio": {
      "aspectRatioId": 12123,
      "aspectRatio": "16:9",
      "defaultWidthInPixel": 864,
      "defaultHeightInPixel": 486,
      "status": 1
    },
    "totalDurationOfCampaignInSeconds": 1000,
    "createdByUserId": 15,
    "createdByFullName": "Abc Xyz",
    "associatedWithCampaignStrings": [
      {
        "layoutStringId": 13,
        "layoutStringName": "Cool layout String 1"
      },
      {
        "layoutStringId": 15,
        "layoutStringName": "Cool layout String 2"
      }
    ],
    "backgroundImageContentId": 878,
    "backgroundImageContentVersion": 12,
    "backgroundColor": "#888888",
    "transparencyInPercentage": 50,
    "audioStartBasedOnLayoutDurationInSeconds": 120,
    "audioEndBasedOnLayoutDurationInSeconds": 480,
    "audios": [
      {
        "contentId": 12,
        "contentVersion": 15,
        "order": 1
      },
      {
        "contentId": 16,
        "contentVersion": 3,
        "order": 2
      }
    ],
    "state": "DRAFT|SUBMITTED|APPROVED|PUBLISHED",
    "status": 1,
    "canApprove": false,
    "regions": [
      {
        "layoutRegionId": 7267,
        "layoutRegionName": "My cool region",
        "regionTransparencyInPercentage": 15,
        "isAudioEnabled": true,
        "zIndex": 12,
        "locations": [
          {
            "locationId": 12,
            "locationName": "Noida"
          },
          {
            "locationId": 122,
            "locationName": "Delhi"
          }
        ],
        "widthInPercentage": 50,
        "heightInPercentage": 30,
        "topLeftCoordinateXInPercentage": 13,
        "topLeftCoordinateYInPercentage": 18,
        "widthInPixel": 531,
        "heightInPixel": 260,
        "topLeftCoordinateXInPixel": 189,
        "topLeftCoordinateYInPixel": 694,
        "globalRegionContentPlaylistId": 123,
        "globalRegionContentPlaylistContents": [
          {
            "contentId": 323,
            "contentVersion": 1,
            "contentType": "ADVERTISEMENT", // PDN network should look for this content type
            "order": 2,
            "durationInSeconds": 600,
            "transparencyInPercentage": 0,
            "entryAnimationId": 329,
            "exitAnimationId": 329,
            "displayMode": "NORMAL|STRETCH-TO-FIT"
          },
          {
            "contentId": 84,
            "contentVersion": 19,
            "contentType": "VIDEO",
            "order": 1,
            "durationInSeconds": 800,
            "transparencyInPercentage": 30,
            "entryAnimationId": 329,
            "exitAnimationId": 329,
            "displayMode": "NORMAL|STRETCH-TO-FIT"
          }
        ]
      }
    ],
    "layoutTags": [
      {
        "layoutTag": "hello"
      },
      {
        "layoutTag": "test"
      },
      {
        "layoutTag": "world"
      }
    ],
    "workFlowActivity": [
      {
        "workFlowActivityType": "REJECT",
        "userId": 12,
        "fullName": "Ashok Kumar",
        "reason": "Background color was not good. Please change to yellow.",
        "approverLevel": 2,
        "roles": [
          {
            "roleId": 1,
            "roleName": "CUSTOMER_ADMIN"
          }
        ],
        "timestampOfActivity": 158446989797,
        "displayString": "L1 Ashok Kumar"
      },
      {
        "workFlowActivityType": "APPROVE",
        "userId": 18,
        "fullName": "Deepak",
        "approverLevel": 1,
        "roles": [
          {
            "roleId": 5,
            "roleName": "APPROVER"
          }
        ],
        "timestampOfActivity": 158446989797,
        "displayString": "L2 Deepak"
      },
      {
        "workFlowActivityType": "SUBMIT",
        "userId": 18,
        "fullName": "Naveen",
        "approverLevel": null,
        "roles": [
          {
            "roleId": 4,
            "roleName": "MAKER"
          }
        ],
        "timestampOfActivity": 158446989797,
        "displayString": "L2 Deepak"
      }
    ]
  },
  "name": null,
  "code": 0,
  "message": null
}
```

## Get schedule by deviceId (to be called by PDN server)

    /pdn/schedule/<deviceId>  [GET]
    
QUERY

    start-date=2018-12-30  // required
    end-date=2019-01-15    // required
    
HEADER

    Content-Type:application/json
    Authorization:Bearer {token}
    customerId: <customerId>

BODY

    NA

RESPONSE - code - 200
```javascript
{
  "result": {
    "deviceSchedule": {
      "deviceId": 1,
      "layouts": [
        {
          "layoutId": 1,
          "layoutType" : "NORMAL",
          "startDateTime": "2018-12-30 11:30:00",
          "endDateTime": "2018-12-30 13:30:00",
          "planogramId": 15,
          "planogramName" : "Weekend Sale planogram",
          "offsetInSeconds": 23
        },
        {
          "layoutId" : 2,
          "layoutType" : "ADVERTISEMENT",
          "startDateTime": "2018-12-30 14:30:00",
          "endDateTime": "2018-12-30 15:30:00",
          "planogramId": 26,
          "planogramName" : "All food and bevrages planogram",
          "offsetInSeconds": 0
        }
      ],
      "startDateTime": "2018-12-30",
      "endDateTime": "2019-01-15"
    }
  },
  "name": null,
  "code": null,
  "message": null
}
```

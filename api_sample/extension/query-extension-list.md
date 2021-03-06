# Query Extension List

Through this interface, developers could fetch basic information about S-Series extension list, like extension number, extension name, extension status, type, etc.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/extensionlist/query?token=6cad9cee6e2ad94570636e7b3690aeb2){version}[/extensionlist/query?token=6cad9cee6e2ad94570636e7b3690aeb2](https://192.168.5.150:8088/api/v1.0.0/extensionlist/query?token=6cad9cee6e2ad94570636e7b3690aeb2)

**Request parameters descriptions:**

No parameter. Only need to send the request.

**Response sample:**

{"status":"Success","extlist":\[{"extnumber":"1000","status":"Registered","type":"SIP","username":"Jayson","agentid":""},{"extnumber":"1001","status":"Unavailable","type":"SIP","username":"Erwin Co","agentid":""},{"extnumber":"1010","status":"Unavailable","type":"SIP","username":"lulu","agentid":""},{"extnumber":"1101","status":"Registered","type":"SIP","username":"Ina Zoiper","agentid":""},{"extnumber":"1102","status":"Registered","type":"SIP","username":"Ina Eyebeam","agentid":""},{"extnumber":"1103","status":"Unavailable","type":"SIP","username":"1103","agentid":""},{"extnumber":"1104","status":"Unavailable","type":"SIP","username":"1104","agentid":""},{"extnumber":"1105","status":"Unavailable","type":"SIP","username":"1105","agentid":""},{"extnumber":"3002","status":"unavailable","type":"SIP","username":"3002","agentid":""}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- |
| **&lt;extlist&gt;** | Object | Extension object | N/A |
| **&lt;extnumber&gt;** | Int | The extension number | 1000 |
| **&lt;status&gt;** | String | Current status of the extension | Unavailable, Registered, Ringing, Busy, Hold, Malfunction, Idle, Fxsnoport |
| **&lt;type&gt;** | String | The extension type | SIP, FXS |
| **\[port\]** | String | The extension port. When the extension is analog phone, the parameter will be displayed. | Span1\_Port3 |
| **&lt;username&gt;** | String | Username | Ina Tang |
| **\[agentid\]** | String | The agent ID to be announced in the greeting prompt. The parameter is null by default and, if it is not specified, the extension number will be announced instead. | 6103 |

**Possible error code: **30001

###  {#query-one-or-more-extensions}




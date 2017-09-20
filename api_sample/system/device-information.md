# Query Device Information

Through this interface, developers could fetch S-Series VoIP PBX device information. \(新增\)

**Request method: **POST

**Request address:**

** **[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/deviceinfo/query?token=7d20390952e15eb72b0a1df7172de65c){version}[/deviceinfo/query?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/deviceinfo/query?token=7d20390952e15eb72b0a1df7172de65c)

**Request parameters descriptions:**

No parameter. Only need to send the request.

**Response sample:**

{"status":"Success","deviceinfo":{"devicename":"Yeastar S100","sn":"369364835218","hardwarever":"V1.30 0000-0000","firmwarever":"30.5.0.109","systemtime":"2017-05-24 23:25:20 UTC-8","uptime":"03:25:04","extensionstatus":"7/100"}}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- |
| **&lt;devicename&gt;** | String | The device name | Yeastar S100 |
| **&lt;sn&gt;** | String | Serial Number | 369364835218 |
| **&lt;hardwarever&gt;** | String | The hardware version | V1.30 0000-0000 |
| **&lt;firmwarever&gt;** | String | The firmware version | 30.5.0.19 |
| **&lt;systemtime&gt;** | String | The system time | 2017-05-24 23:25:20 UTC-8 |
| **&lt;uptime&gt;** | String | Up time | 3:25:04 AM |
| **&lt;extensionstatus&gt;** | String | Current registered extension number/extension number in total | 7/100 |

**Possible error code: **30001


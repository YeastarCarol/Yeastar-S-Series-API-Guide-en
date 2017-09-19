## System {#system}

Through this interface, developers could fetch S-Series system information, like firmware version, hardware version, system time, etc.

### Device Information {#device-information}

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/deviceinfo/query?token=7d20390952e15eb72b0a1df7172de65c

**Request parameters descriptions:**

No parameter. Only need to send the request.

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;deviceinfo&quot;:{&quot;devicename&quot;:&quot;Yeastar S100&quot;,&quot;sn&quot;:&quot;369364835218&quot;,&quot;hardwarever&quot;:&quot;V1.30 0000-0000&quot;,&quot;firmwarever&quot;:&quot;30.4.0.107&quot;,&quot;systemtime&quot;:&quot;2017-05-24 23:25:20 UTC-8&quot;,&quot;uptime&quot;:&quot;03:25:04&quot;,&quot;extensionstatus&quot;:&quot;7/100&quot;}}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;devicename&gt;** | String | The device name | Yeastar S100 |
| **&lt;sn&gt;** | String | Serial Number | 369364835218 |
| **&lt;hardwarever&gt;** | String | The hardware version | V1.30 0000-0000 |
| **&lt;firmwarever&gt;** | String | The firmware version | 30.4.0.107 |
| **&lt;systemtime&gt;** | String | The system time | 2017-05-24 23:25:20 UTC-8 |
| **&lt;uptime&gt;** | String | Up time | 3:25:04 AM |
| **&lt;extensionstatus&gt;** | String | Current registered extension number / extension number in total | 7/100 |

**Possible error code:** 30001
# Query One or More IVRs

Through this interface, developers could fetch detailed information like IVR number, IVR name, keypress events, response timeout, etc. of one or more IVRs.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/ivr/query?token=6cad9cee6e2ad94570636e7b3690aeb2){version}[/ivr/query?token=6cad9cee6e2ad94570636e7b3690aeb2](https://192.168.5.150:8088/api/v1.0.0/ivr/query?token=6cad9cee6e2ad94570636e7b3690aeb2)

**Request sample:**

{"ivrid": "6500"}

**Request parameters descriptions:**

1. Sending no parameter means query all information.
2. With parameters in request, developers could query specific information. Separate them with ",". For example: {"ivrid": "6500,6501,6502"}.

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | String | Query one or more IVRs | 6202 |

**Response sample:**

{"status":"Success","ivr":\[{"ivrnumber":"6500","ivrname":"6500","prompt":"\[Default\]","promptrepeat":"3","responsetimeout":"3","digittimeout":"3","dialext":"on","dialoutboundroutes":"off","dialtocheckvoicemail":"off"}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrnumber&gt;** | String | The IVR number | 6500 |
| **&lt;ivrname&gt;** | String | The IVR name | 6202 |
| **\[prompt\]** | String | The IVR prompt | \[Default\] |
| **\[promptrepeat\]** | String | How many times will the prompt be repeated | 3 |
| **\[responsetimeout\]** | Int | Response timeout in seconds. | 3 |
| **\[digittimeout\]** | Int | Digit timeout in seconds. | 5 |
| **\[dialext\]** | String | Allow the caller to dial extension. | On: enable  off: disable |
| **\[dialoutboundroutes\]** | String | Allow the caller to dial through outbound routes. | On: enable  off: disable |
| **\[selectedrouters\]** | String | The route selected |  |
| **\[dialtocheckvoicemail\]** | String | Allow to check voicemail | On: enable  off: disable |

**Possible error code:** 10012, 30001


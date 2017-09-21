# Configure an Individual IVR

Through this interface, developers could configure IVR number, IVR name, etc. of an IVR.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/ivr/update?token=6cad9cee6e2ad94570636e7b3690aeb2){version}[/ivr/update?token=6cad9cee6e2ad94570636e7b3690aeb2](https://192.168.5.150:8088/api/v1.0.0/ivr/update?token=6cad9cee6e2ad94570636e7b3690aeb2)

**Request sample:**

{"ivrid": "6500","ivrnumber":"6501"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | String | A unique identifier of the configured IVR \(IVR number\) | 6202 |
| **&lt;ivrnumber&gt;** | String | Modified IVR number | 6204 |
| **&lt;ivrname&gt;\(改\)** | String | The IVR name | 6202, !$\(\)\/\#;,\"=&lt;&gt;&'\`^%@{}\| are invalid for IVR name. Neither is space valid. Maximum length is 31. Cannot be blank. |
| **\[promptrepeat\]** | String | How many times will the prompt be repeated | A range from 1 to 5 |
| **\[responsetimeout\]** | Int | Response timeout in seconds. | A range from 1 to 10 |
| **\[digittimeout\]** | Int | Digit timeout in seconds. | A range from 1 to 10 |
| **\[dialext\]** | String | Allow the caller to dial extension. | On: enable  Off: disable |
| **\[dialtocheckvoicemail\]** | String | Allow to check voicemail | On: enable  oOff: disable |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | IVR configuration result | Success or Failed |




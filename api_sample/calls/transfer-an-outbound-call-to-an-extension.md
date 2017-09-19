### Transfer an Outbound Call to an Extension {#transfer-an-outbound-call-to-an-extension}

Through this interface, an outbound call dialed out through the PBX's trunk can be transferred to an extension.

Note: the call can be transferred whether it's a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/outbound/transfer\_extension?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_extension?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"outboundid": "1495700976.276","extid": "1003"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | The outbound ID | 1495700976.276 |
| **&lt;extid&gt;** | Int | The extension number | 1000 |

**Response sample:**

{"status":"Success","callid":"1495700976.275"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700976.275 |

**Possible error code:** 10004, 10006, 10007, 30001

###  {#transfer-an-outbound-call-to-a-trunk}

###  {#transfer-an-outbound-call-to-an-ivr}




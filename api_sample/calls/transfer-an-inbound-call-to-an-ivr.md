### Transfer an Inbound call to an IVR {#transfer-an-inbound-call-to-an-ivr}

Through this interface, an inbound call from the PBX's trunk can be transferred to an IVR.

Note: the call can be transferred whether it's a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/inbound/transfer\_ivr?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_ivr?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"inboundid": "1495698591.209","ivrid": "6500"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | int | The inbound ID | 1495698591.209 |
| **&lt;ivrid&gt;** | int | The IVR number | 6500 |

**Response sample:**

{"status":"Success","callid":"1495698591.209"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495698591.209 |

**Possible error code:** 10004, 10006, 10012, 30001

###  {#transfer-an-inbound-call-to-a-trunk}




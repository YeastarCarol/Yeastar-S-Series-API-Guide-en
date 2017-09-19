### Transfer an Outbound Call to an IVR {#transfer-an-outbound-call-to-an-ivr}

Through this interface, an outbound call can be transferred to an IVR in order to:

1. Play audio to the called party of the outbound call

2. Send the keypress report to the application server when the called party's keypress triggers the relevant event.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_ivr?token=7d20390952e15eb72b0a1df7172de65c){version}[/outbound/transfer\_ivr?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_ivr?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"outboundid": "1495700976.276","ivrid": "6500"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | The outbound ID | 1495700976.276 |
| **&lt;ivrid&gt;** | Int | The IVR number | 6500 |

**Response sample:**

{"status":"Success","callid":"1495700976.275"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700976.275 |

**Possible error code:** 10004, 10007, 10012, 30001


### Dial an External Number in an IVR {#dial-an-external-number-in-an-ivr}

Through this interface, an external number will be dialed while in an IVR in order to:

1. Play audio to the dialed party when the call is established;

2. Send the keypress report to the application server when the dialed party's keypress triggers the relevant event.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/ivr/dial\_outbound?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/ivr/dial_outbound?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"ivrid": "6500","outto": "41000","fromext": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | String | The IVR number | 6500 |
| **&lt;outto&gt;** | String | The dialed external number \(the outbound dial pattern should be matched\) | 41000 |
| **&lt;fromext&gt;** | String | Which extension's call permission will be applied | 1000 |

**Response sample:**

{"status":"Success","callid":"1495700406.266"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700406.266 |

###  {#dial-an-external-number-in-a-queue}




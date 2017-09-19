### Transfer an Outbound Call to a Trunk {#transfer-an-outbound-call-to-a-trunk}

Through this interface, an outbound call dialed out through the PBX's trunk can be transferred to another trunk. As a result, the two numbers can establish calls with the PBX as the transit stop.

At least one trunk should be available at the time of transfer. And the outbound route's dial pattern should be matched.

Note: the call can be transferred whether it's a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_outbound?token=7d20390952e15eb72b0a1df7172de65c){version}[/outbound/transfer\_outbound?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_outbound?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"outboundid": "1495701184.282","outto": "22003","fromext": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | The outbound ID | 1495700976.275 |
| **&lt;outto&gt;** | String | The external number to dial | 22003 |
| **&lt;fromext&gt;** | String | Which extension's call permission will be applied | 1000 |

**Response sample:**

{"status":"Success","callid":"1495701183.281"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495701183.281 |

**Possible error code:** 10004, 10006, 10007, 30001


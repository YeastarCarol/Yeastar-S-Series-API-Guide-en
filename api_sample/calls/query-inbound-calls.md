### Query Inbound Calls {#query-inbound-calls}

Through this interface, developers could fetch detailed information like caller, callee, call status, etc. of all inbound calls coming from the trunks of the PBX.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/inbound/query?token=7d20390952e15eb72b0a1df7172de65c){version}[/inbound/query?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/inbound/query?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"inboundid": "1495698433.203"}

**Request parameters descriptions:**

1. Sending no parameter means query all information.
2. With parameters, developers could query one or more outbound calls. Separate them with ",".

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | Query all inbound calls | N/A |

**Response parameters:**

{"status":"Success","inbound":\[{"inboundid":"1495698433.203","from":"1000","to":"1002","trunk":"SIP-142","status":"Talking","callee":\[{"extid":"1002"}\]}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **\[inbound\]** | object | Inbound calls: calls from external numbers through the trunks | N/A |
| **&lt;inboundid&gt;** | int | The inbound ID. With this parameter, operations like forwarding, query, and hangup can be performed on this inbound call. | 1495698433.203 |
| **&lt;from&gt;** | String | The caller's number | 1000 |
| **&lt;to&gt;** | String | The callee's number | 5003 |
| **\[callee\]** | object | The called party of an inbound call, could be an extension, IVR, or an outbound ID. | 1005 |
| **&lt;trunk&gt;** | String | The name of the trunk that passes the inbound call | SIP |
| **\[status\]** | String | Call status | Talking: talking on the call |

**Possible error code:** 30001


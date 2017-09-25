# Query Outbound Calls

Through this interface, developers could fetch detailed information like caller, callee, call status, etc. of all calls dialing out via the trunks of the PBX.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/outbound/query?token=6cad9cee6e2ad94570636e7b3690aeb2){version}[/outbound/query?token=6cad9cee6e2ad94570636e7b3690aeb2](https://192.168.5.150:8088/api/v1.0.0/outbound/query?token=6cad9cee6e2ad94570636e7b3690aeb2)

**Request sample:**

{"outboundid": "1495705009.316"}

**Request parameters descriptions:**

1. Sending no parameter means query all outbound calls.
2. With parameters in request, developers could query one or more outbound calls. Separate them with ",".

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | Query all outbound calls | N/A |

**Response sample:**

{"status":"Success","outbound":\[{"outboundid":"1495705009.316","from":"1002","to":"41000","trunk":"SIP-142","status":"Talking"}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| &lt;**outbound&gt;** | Object | Outbound calls: calls to external numbers | N/A |
| **&lt;outboundid&gt;** | String | The outbound ID. With this parameter, operations like forwarding, query, and hangup can be performed on the outbound call. | 1495705009.316 |
| **&lt;from&gt;** | Int | caller ID | 1000 |
| **&lt;to&gt;** | Int | callee ID | 41000 |
| **&lt;trunk&gt;** | String | The name of the trunk that passes the outbound call | SIP-142 |
| &lt;**status&gt;** | String | Call status | Talking: talking on the call <br> Progress: progressing the call <br> Wait: Call Waiting |

**Possible error code:** 30001


### Call Back {#call-back}

Through this interface, the PBX will dial two external numbers consecutively, and the two numbers could be connected with the PBX as the transit stop.

**Operations**

Dial the calling party's number first. The call is answered. Then dial the called party's number. The call is answered. The two parties are therefore connected.

**Conditions**

1. The calls will rely on an extension's outbound call permission.

2. There are at least two available trunks.

3. The two calls need to match the outbound route.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/outbound/dial_outbound?token=7d20390952e15eb72b0a1df7172de65c){version}[/outbound/dial\_outbound?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/outbound/dial_outbound?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"caller": "1002","outto": "41000","fromext": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;caller&gt;** | String | The number of the calling party \(the outbound dial pattern should be matched\), which will be dialed first | 1002 |
| **&lt;outto&gt;** | String | The number of the called party \(the outbound dial pattern should be matched\), which will be dialed secondly | 41000 |
| **&lt;fromext&gt;** | Int | Which extension's call permission will be applied | 1000 |

**Response sample:**

{"status":"Success","callid":"1495701633.295"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495701633.295 |

**Possible error code:** 10004, 10006, 10012, 30001


### Make an Internal Call {#make-an-internal-call}

Through this interface, an extension could call another extension and establish the call.

Send the request to make extension A dial extension B. Extension A will ring first, extension B will ring after extension A picks up the call. If “autoanswer” is set to “yes”, extension A \(the calling party\) will hear the ring back tone, extension B \(the called party\) will hear the ringing.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extension/dial\_extension?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/dial_extension?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"caller": "1000","callee": "1002","autoanswer":"no"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;caller&gt;** | String | The caller extension | 1000 |
| **&lt;callee&gt;** | String | The callee extension | 1002 |
| **\[autoanswer\]** | String | Whether to auto answer the call or not. This parameter requires the SIP phone to support. It means "no" if the parameter has not been specified. | yes/no |

**Response sample:**

{"status":"Failed","errno":"10003"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10006, 30001


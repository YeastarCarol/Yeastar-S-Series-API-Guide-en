### Hang up an Inbound Call {#hang-up-an-inbound-call}

Through this interface, the specified inbound call can be terminated.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/inbound/hangup?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/inbound/hangup?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"inboundid": "1495698510.206"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | Hang up the specified inbound call | 1495698510.206 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10007, 10004, 30001


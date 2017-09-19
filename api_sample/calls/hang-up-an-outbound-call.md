### Hang up an Outbound Call {#hang-up-an-outbound-call}

Through this interface, the specified outbound call can be terminated.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/outbound/hangup?token=6cad9cee6e2ad94570636e7b3690aeb2){version}[/outbound/hangup?token=6cad9cee6e2ad94570636e7b3690aeb2](https://192.168.5.150:8088/api/v1.0.0/outbound/hangup?token=6cad9cee6e2ad94570636e7b3690aeb2)

**Request sample:**

{"outboundid": "1495705264.322"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | Hang up the specified outbound call | 1495705264.322 |

**Response parameters descriptions:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10007, 10004, 30001

###  {#hold-a-call}




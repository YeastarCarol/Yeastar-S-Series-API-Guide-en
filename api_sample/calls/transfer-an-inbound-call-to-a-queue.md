### Transfer an Inbound Call to a Queue {#transfer-an-inbound-call-to-a-queue}

Through this interface, an inbound call from an external number can be transferred to a queue. When the queue has idle agents, the call will be handled accordingly. As a result:

1. If there are idle agents in the queue, the call will be passed according to the ring strategy.

2. If all agents are busy, the call will wait in the queue and hear the music on hold. The first call in the queue will be answered first when the queue is idle.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_queue?token=7d20390952e15eb72b0a1df7172de65c){version}[/inbound/transfer\_queue?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_queue?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"inboundid": "1495700191.223","queueid": "6700"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | The inbound ID | 1495700191.223 |
| **&lt;queueid&gt;** | String | The queue number | 6700 |

**Response sample:**

{"status":"Success","callid":"1495700191.223"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700191.223 |

**Possible error code:** 10004, 10013, 30001

###  {#transfer-an-inbound-call-to-a-ring-group}




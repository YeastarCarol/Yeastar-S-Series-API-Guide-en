### Transfer an Inbound Call to a Ring Group {#transfer-an-inbound-call-to-a-ring-group}

Through this interface, an inbound call can be transferred to a ring group. As a result, the call will be handled according to the ring strategy when there are one or more available extensions in the group.

When Busy/No Answer

1. If no extension is available \(busy, DND\), following the ring group's settings, the call will wait until an available extension picks up.

2. If there are idle extensions, but the idle extension does not answer the call, the call will be directed to the next idle extension.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_ringgroup?token=7d20390952e15eb72b0a1df7172de65c){version}[/inbound/transfer\_ringgroup?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_ringgroup?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"inboundid": "1495700191.223","ringgroupid": "6200"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | The inbound ID | 1495700191.223 |
| **&lt;ringgroupid&gt;** | Int | The ring group number | 6200 |

**Response sample:**

{"status":"Success","callid":"1495700191.223”}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700191.223 |

**Possible error code:** 10004, 10006, 10014, 30001

###  {#send-text-messages-through-a-gsm-trunk}




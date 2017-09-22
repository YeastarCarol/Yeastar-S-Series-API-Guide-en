### Dial an External Number in a Queue {#dial-an-external-number-in-a-queue}

Through this interface, an outbound call made with an external number being dialed out through S-Series IPPBX’s trunk can be transferred to a queue as an inbound call after it is established. Once the call is transferred, extensions in the queue will ring according to the ring strategy.

Note: need to dial from an extension with route permission and the outbound dial pattern should be matched.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.1/queue/dial_outbound?token=25e9c77a705e6da650082dc1409fb68e){version}[/queue/dial\_outbound?token=25e9c77a705e6da650082dc1409fb68e](https://192.168.5.150:8088/api/v1.0.1/queue/dial_outbound?token=25e9c77a705e6da650082dc1409fb68e)

**Request sample:**

{ "queueid": "6700","outto": "118396210850","fromext": "1000000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt; queueid&gt;** | Int | The queue number | 6700 |
| **&lt;outto&gt;** | String | The external number | 118396210850 |
| **&lt;fromext&gt;** | String | Which extension's call permission will be applied | 1000000 |

**Response sample:**

{"status":"Success","callid":"1501126620.23"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1501126620.23 |

###  {#dial-an-external-number-in-a-ring-group}




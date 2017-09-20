### Dial an External Number in a Ring Group\(新增note\) {#dial-an-external-number-in-a-ring-group}

Through this interface, an outbound call made with an external number being dialed out through S-Series IPPBX’s trunk can be transferred to a ring group as an inbound call after it is established. Once the call is transferred, extensions in the ring group will ring according to the ring strategy.

Note: need to dial from an extension with route permission to and the outbound dial pattern should be matched.\(新增\)

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.1/ringgroup/dial_outbound?token=172970ee3f5f92fe65cd6bc17663b1f7){version}[/ringgroup/dial\_outbound?token=172970ee3f5f92fe65cd6bc17663b1f7](https://192.168.5.150:8088/api/v1.0.1/ringgroup/dial_outbound?token=172970ee3f5f92fe65cd6bc17663b1f7)

**Request sample:**

{ "ringgroupid": "6200","outto": "118396210850","fromext": "1000000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt; ringgroupid&gt;** | Int | The ring group number | 6200 |
| **&lt;outto&gt;** | String | The external number | 118396210850 |
| **&lt;fromext&gt;** | String | Which extension's call permission will be applied | 1000000 |

**Response sample:**

{"status":"Success","callid":"1501145750.391"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1501145750.391 |




# Inbound Call

If the trunk's API has Inbound Call Answering Control enabled, then when the trunk answers call, the PBX will send an Incoming event to the application server.

**Report sample:**

{"action":"Incoming","callid":"1495707950.331","inbound":{"from":"1000","to":"1002","trunk":"sip-142","inboundid":"1495707950.331"}}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Call coming in | Incoming |
| **&lt;callid&gt;** | String | A unique identifier of the call | 1495707950.331 |
| **&lt;inbound&gt;** | Object | Inbound call |  |
| **&lt;trunk&gt;** | String | The trunk name | sip-142 |
| **&lt;inboundid&gt;** | String | Inbound ID | 1495707950.331 |
| **&lt;from&gt;** | String | The caller's number | 1000 |
| **&lt;to&gt;** | String | The callee' number | 1002 |




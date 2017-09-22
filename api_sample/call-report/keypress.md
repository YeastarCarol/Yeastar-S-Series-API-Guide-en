# Keypress

This event is used report key pressed in the IVRs.

When a call reaches IVR, and the IVR's keypress event is triggered, the PBX will send the event to the application server.

**Report sample:**

{"action":"DTMF","callid":"1495705009.315","outbound":{"from":"1002","to":"41000","trunk":"SIP-142","outboundid":"1495705009.316"},"info":"\#"}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Keypress | DTMF |
| **&lt;callid&gt;** | String | A unique identifier of the call | 1495707950.331 |
| **&lt;inbound&#124;outbound&gt;** | Object | Inbound call/outbound call | N/A |
| **&lt;trunk&gt;** | String | The trunk name | sip-142 |
| **&lt;inboundid&gt;** | String | Inbound ID | 1495707950.331 |
| **&lt;from&gt;** | String | The caller's number | 1000 |
| **&lt;to&gt;** | String | The callee' number | 1002 |
| **&lt;info&gt;** | String | Keypress | \# |




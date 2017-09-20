# Call Released \(新增表格\)

The PBX will send a report to the application server when a call is released. In the report, the party who ends the call will appear first.

**Report sample:**

{"action":"BYE","callid":"1495706238.328","ext":{"extid":"1000"},"ext":{"extid":"1002"}}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Status | BYE |
| **\[extid\]** | String | The extension number \(caller/callee\) | 1002 |
| **&lt;inboundid\|outboundid&gt;** | String | The inbound ID/ outbound ID | 1495771030.366 |
| **\[from\]** | String | The caller's number | 1806354000 |
| **\[to\]** | String | The callee's number | 1237456 |
| &lt;**callid&gt;** | String | A unique identifier of the call | 1495771030.365 |




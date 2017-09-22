# Answer a Call

The PBX will send a report to the application server when an extension answers a call.

Answering call \(the called party\) and call answered \(the calling party\) coexist. In the report, the calling party's number will appear first.

**Report sample:**

{"action":"ANSWER","callid":"1495706238.328","ext":{"extid":"1000"},"ext":{"extid":"1002"}}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Status | ANSWER |
| **\[extid\]** | String | The extension number \(callee\) | 1002 |
| **&lt;inboundid&#124;outboundid&gt;** | String | The inbound ID / outbound ID | 1495771030.366 |
| **\[from\]** | String | The caller's number | 1806354000 |
| **\[to\]** | String | The callee's number | 1237456 |
| **\[callid\]** | String | A unique identifier of the call | 1495771030.365 |




# Call Answered

The PBX will send a report to the application server when the calling party's call is answered.

Answering call \(the called party\) and call answered \(the calling party\) coexist. In the report, the calling party's number will appear first.

**Report sample:**

{"action":"ANSWERED","callid":"1495706238.328","ext":{"extid":"1002"},"ext":{"extid":"1000"}}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Status | ANSWERED |
| **\[extid\]** | String | The extension number \(caller\) | 1002 |
| **&lt;inboundid&gt;** | String | The inbound ID | 1495771030.366 |
| **\[from\]** | String | The caller's number | 1806354000 |
| **\[to\]** | String | The callee's number | 1237456 |
| &lt;**callid&gt;** | String | A unique identifier of the call | 1495771030.365 |




# Call Released

The PBX will send a report to the application server when a call is released. In the report, if the calling party releases the call,  calling party's number will appear first and vice versa.

**Report sample:**

{"action":"BYE","callid":"1495706238.328","ext":{"extid":"1000"},"ext":{"extid":"1002"}}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- |
| **&lt;action&gt;** | String | Status | BYE |
| **\[extid\]** | String | The extension number \(caller/callee\) | 1002 |
| **&lt;inboundid&#124;outboundid&gt;** | String | The inbound ID / outbound ID | 1495771030.366 |
| **\[from\]** | String | The caller's number | 1806354000 |
| **\[to\]** | String | The callee's number | 1237456 |
| **&lt;callid&gt;** | String | A unique identifier of the call | 1495771030.365 |




# Call Transfer

When there is a call transferred inside the PBX, the PBX will send a report to the application server.

The report only includes operations performed by the extensions, for example, dialing "\*03" and "\*3" feature codes, follow me settings, etc. Transfer controlled by API will not be reported.

**Report sample:**

{"action":"Tranfer","callid":"1505291815.120","ext":{"extid":"1000"},"inbound":{"from":"102","to":"1000","trunk":"Apple\_test","inboundid":"1505291815.120"}}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Status | Transfer |
| **\[extid\]** | String | The extension number of the extension that initiates the transfer | 1002 |
| **&lt;inboundid&#124;outboundid&gt;** | String | The inbound ID/ outbound ID | 1495771030.366 |
| **\[from\]** | String | The caller's number | 1806354000 |
| **\[to\]** | String | The callee's number | 1237456 |
| **&lt;callid&gt;** | String | A unique identifier of the call | 1495771030.365 |




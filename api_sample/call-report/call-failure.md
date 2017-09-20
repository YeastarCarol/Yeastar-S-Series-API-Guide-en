# Call Failure\(新增表格\)

Generally, call failure event will appear in the response message of the API request. In certain circumstances, the PBX will send the report.

Call failure is defined as calls that are failed to connect.

Failure of calls initiated manually and by the API will both be reported.

**Report sample:**

**1.Extension outbound call restriction:**

{"action":"CallFailed","reason":"NO Outbound Restriction","callid":"1495420603.349"}

**2.DND enabled:**

{"action":"CallFailed","reason":"DND","callid":"1495186077.229","ext":{"extid":"1005"}}

**3.No available trunks:**

{"action":"CallFailed","reason":"Line unreachable","callid":"1495184155.216","ext":{"extid":"1002"}}

**4.Extension A dials extension B, extension B \(call forwarding disabled\) rejects the call:**

{"action":"CallFailed","reason":"User busy","callid":"1505294245.162"}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Status | CallFailed |
| **&lt;reason&gt;** | String | Call failure reason | No Outbound Restriction, DND, Line unreachable, User busy |
| **&lt;callid&gt;** | String | A unique identifier of the call | 1495771030.365 |
| **\[ext\]** | Int | The extension number of the extension that failed to established the call | 1002 |




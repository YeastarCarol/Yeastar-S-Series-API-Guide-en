# Ring Back\(新增表格\)

当分机响铃时，IPPBX向应用服务器推送该事件报告。注：该类事件只有在使用API接口进行拨号的时候才会上报，用户使用话机拨打时，此类事件不会上报。

The PBX will send a report to the application server when the called party \(extension/inbound call\) rings back the calling party. But only when then the ring back is triggered by a dial using the API, the report will be sent, namely, if a ring back is triggered by a dial made from an extension, the report will not be sent.

**Note：**ringing \(the called party\) and ring back \(the calling party\) coexist. Calls with external numbers and internal calls will both be reported. In the report, the party who triggers the call will appear first.

**Report sample:**

{"action":"ALERT","callid":"1495706238.328","ext":{"extid":"1002"}}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Status | ALERT |
| **\[extid\]** | String | The extension number \(caller\) | 1002 |
| **&lt;inboundid&gt;** | String | The inbound ID | 1495771030.366 |
| **\[from\]** | String | The caller's number | 1806354000 |
| **\[to\]** | String | The callee's number | 1237456 |
| **\[callid\]** | String | A unique identifier of the call | 1495771030.365 |




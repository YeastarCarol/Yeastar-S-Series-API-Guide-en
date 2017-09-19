# Query One or More Extensions

Through this interface, developers could fetch detailed information about an individual extension or multiple extensions. For example, developers could query the advanced settings of an extension. When there are multiple requests, separate them with commas.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/extension/query?token=7d20390952e15eb72b0a1df7172de65c){version}[/extension/query?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/query?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000"}

**Request parameters descriptions:**

1. Sending no parameter means query all information.
2. With parameters in request, developers could query specific information. Separate them with ",". For example, {"extid": "1000,1001,1002"}

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | int | The extension number of the extension to be queried | 1000 |

**Response sample:**

{"status":"Success","extinfos":\[{"extnumber":"1000","username":"Jayson","status":"Registered","type":"SIP","callerid":"1000","registername":"1000","registerpassword":"xMn5W4Gs","maxregistrations":"1","loginpassword":"5e12ba8dd1083a7f946e457cf3c18779","email":"","moblie":"","language":"System Default","hasvoicemail":"on","enablevmtoemail":"off","vmsecret":"1000","alwaysforward":"off","noanswerforward":"on","ntransferto":"Voicemail","ntransferprefix":"","busyforward":"on","btransferto":"Voicemail","btransferprefix":"","ringsimultaneous":"off","mobileprefix":"","enablemobile":"off","allowbeingmonitored":"off","monitormode":"Disabled","ringtimeout":"30","maxduration":"Follow System","dnd":"off","callrestriction":"off","agentid":""}\]}

**Response parameters descriptions:**

| Parameter Name | Type | Description | Sample |
| :--- | :--- | :--- | :--- |
| &lt;extinfos&gt; | object | Object | N/A |
| &lt;extnumber&gt; | int | The extension number | 1000 |
| &lt;username&gt; | string | The username | Ina Tang |
| &lt;status&gt; | string | Extension current status | Unavailable, Registered, Ringing, Busy, Hold, Malfunction, Idle, Fxsnoport |
| &lt;type&gt; | string | The extension type | SIP, FXS |
| \[port\] | string | The extension port | Span1\_Port3 |
| &lt;callerid&gt; | string | Caller ID | 1000 |
| &lt;registername&gt; | string | The registration name | 1000 |
| &lt;registerpassword&gt; | string | The registration password | Displayed in plain text |
| &lt;maxregistrations&gt; | int | Allowed maximum concurrent registrations | 5 |
| &lt;loginpassword&gt; | string | The login password | Displayed in MD5 cipher text |
| &lt;email&gt; | string | The email address | ina@yeastar.com |
| &lt;mobile&gt; | string | The mobile number | 134899999999 |
| &lt;language&gt; | string | The language of the system prompt | System default |
| &lt;hasvoicemail&gt; | string | Enable or disable Voicemail feature | On: enable  Off: disable |
| &lt;vmsecret&gt; | int | The voicemail password | 3000 |
| &lt;enablevmtoemail&gt; | string | Whether to enable Send Voicemail to Email feature or not | On: enable   Off: disable |
| \[alwaysforward\] | string | Enable or disable Always Call Forwarding feature | On: enable   Off: disable |
| \[atransferto\] \[atransferext\] \[atransferprefix\] \[atransfernum\] | string | Alway Call Forwarding destination. If choosing to always forward calls to an extension, the designated extension number should be configured; if choosing to always forward calls to an external number, the external number and the corresponding call rule should be configured. | Voicemail: voicemail Extension: ext1000 Mobile Number: mobile1399999999Custom Number: number95923333 |
| \[noanswerforward\] | string | Enable or disable No Answer Call Forwarding feature | On: enable  Off: disable |
| \[ntransferto\] \[ntransferext\] \[ntransferprefix\] \[ntransfernum\] | string | No answer call forwarding destination. If choosing to always forward calls to an extension, the designated extension number should be configured; if choosing to always forward calls to an external number, the external number and the corresponding call rule should be configured. | Voicemail: voicemail Extension: ext1000 Mobile Number: mobile1399999999 Custom Number: number95923333 |
| \[busyforward\] | string | Enable or disable When Busy Call Forwarding feature | On: enable  Off: disable |
| \[btransferto\] \[btransferext\] \[btransferprefix\] \[btransfernum\] | string | When busy call forwarding destination. If choosing to always forward calls to an extension, the designated extension number should be configured; if choosing to always forward calls to an external number, the external number and the corresponding call rule should be configured. | Voicemail: voicemail Extension: ext1000 Mobile Number: mobile1399999999 Custom Number: number95923333 |
| \[enablemobile\] | string | Enable or disable Mobility Extension feature | On: enable  Off: disable |
| \[ringsimultaneous\] | string | Enable or disable Simultaneous Ringing of Mobility Extension | On: enable  Off: disable |
| \[mobileprefix\] | string | A prefix match ing the outbound route | Blank or a specific prefix |
| &lt;allowbeingmonitored&gt; | string | Allow being monitored | On: enable  Off: disable |
| &lt;monitormode&gt; | string | The monitor mode | Options: Disable, Extensive, Listen, Whisper, Barge-in |
| &lt;ringtimeout&gt; | string | The ring timeout in seconds | 30 |
| &lt;maxduration&gt; | string | The maximum call duration allowed in seconds | 600 |
| &lt;dnd&gt; | string | Enable or disable DND feature | On: enable  Off: disable |
| &lt;callrestriction&gt; | string | Enable or disable outbound dialing restriction | On: enable  Off: disable |
| &lt;agentid&gt; | string | The agent ID to be announced in the greeting prompt. This parameter is null by default and, if left null, the extension number will be announced automatically. | 6362 |
| \[inbound\] | object | Inbound calls, external numbers dial-in | N/A |
| &lt;inboundid&gt; | int | The inbound ID. With this parameter, operations like forwarding, query, and hangup can be performed. | 156785 |
| &lt;from&gt; | string | The caller's number | 1000 |
| &lt;to&gt; | string | The callee's number | 5003 |
| &lt;trunk&gt; | string | The name of the trunk that passes the inbound call | Sip-trunk |
| \[outbound\] | object | Outbound calls: calls to external numbers | N/A |
| &lt;ouboundid&gt; | string | The outbound ID. With this parameter, operations like forwarding, query,andhangup can be performed. | 1 |
| &lt;from&gt; | string | The caller's number | 1000 |
| &lt;to&gt; | string | The callee's number | 5003 |
| &lt;trunk&gt; | string | The name of the trunk that passes the outbound call | Sip-trunk |
| \[ext\] | object | The call party of an inbound call |  |
| &lt;extid&gt; | int | The extension number of the extension that is on the line with the queried extension | 1001 |

**Possible error code: **30001

###  {#configure-an-individual-extension}




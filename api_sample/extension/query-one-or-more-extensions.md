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
| **&lt;extid&gt;** | Int | The extension number of the extension to be queried | 1000 |

**Response sample:**

{"status":"Success","extinfos":\[{"extnumber":"1000","username":"Jayson","status":"Registered","type":"SIP","callerid":"1000","registername":"1000","registerpassword":"xMn5W4Gs","maxregistrations":"1","loginpassword":"5e12ba8dd1083a7f946e457cf3c18779","email":"","moblie":"","language":"System Default","hasvoicemail":"on","enablevmtoemail":"off","vmsecret":"1000","alwaysforward":"off","noanswerforward":"on","ntransferto":"Voicemail","ntransferprefix":"","busyforward":"on","btransferto":"Voicemail","btransferprefix":"","ringsimultaneous":"off","mobileprefix":"","enablemobile":"off","allowbeingmonitored":"off","monitormode":"Disabled","ringtimeout":"30","maxduration":"Follow System","dnd":"off","callrestriction":"off","agentid":""}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- |
| **&lt;extinfos&gt;** | Object | Object | N/A |
| **&lt;extnumber&gt;** | Int | The extension number | 1000 |
| **&lt;username&gt;** | String | The username | Ina Tang |
| **&lt;status&gt;** | String | Extension current status | Unavailable, Registered, Ringing, Busy, Hold, Malfunction, Idle, Fxsnoport |
| **&lt;type&gt;** | String | The extension type | SIP, FXS |
| **\[port\]** | String | The extension port | Span1\_Port3 |
| **&lt;callerid&gt;** | String | Caller ID | 1000 |
| **&lt;registername&gt;** | String | The registration name | 1000 |
| **&lt;registerpassword&gt;** | String | The registration password | Displayed in plain text |
| **&lt;maxregistrations&gt;** | Int | Allowed maximum concurrent registrations | 5 |
| **&lt;loginpassword&gt;** | String | The login password | Displayed in MD5 cipher text |
| **&lt;email&gt;** | String | The email address | ina@yeastar.com |
| **&lt;mobile&gt;** | String | The mobile number | 134899999999 |
| **&lt;language&gt;** | String | The language of the system prompt | System Default |
| **&lt;hasvoicemail&gt;** | String | Enable or disable Voicemail feature | on: enable   off: disable |
| **&lt;vmsecret&gt;** | Int | The voicemail password | 3000 |
| **&lt;enablevmtoemail&gt;** | String | Whether to enable Send Voicemail to Email feature or not | on: enable <br> off: disable |
| **\[alwaysforward\]** | String | Enable or disable Always Call Forwarding feature | on: enable <br> off: disable |
| **\[atransferto\]\[atransferext\] \[atransferprefix\] \[atransfernum\]** | String | Alway Call Forwarding destination. When forwarding destination is an extension number, the designated extension number should be configured; When forwarding destination is a custom number, the custom number and the corresponding call rule should be configured. | Voicemail: voicemail Extension: ext1000   Mobile Number: mobile1399999999   Custom Number: number95923333 |
| **\[noanswerforward\]** | String | Enable or disable No Answer Call Forwarding feature | on: enable  <br>off: disable |
| **\[ntransferto\] \[ntransferext\] \[ntransferprefix\] \[ntransfernum\]** | String | No answer call forwarding destination. When forwarding destination is an extension number, the designated extension number should be configured; when the forwarding destion is a custom number, the custom number and the corresponding call rule should be configured. | Voicemail: voicemail Extension: ext1000 Mobile Number: mobile1399999999 Custom Number: number95923333 |
| **\[busyforward\]** | String | Enable or disable When Busy Call Forwarding feature | on: enable <br> off: disable |
| **\[btransferto\] \[btransferext\] \[btransferprefix\] \[btransfernum\]** | String | When busy call forwarding destination. When the forwarding destination is an extension, the designated extension number should be configured; when the forwarding destination is a custom number, the custom number and the corresponding call rule should be configured. | Voicemail: voicemail Extension: ext1000 Mobile Number: mobile1399999999 Custom Number: number95923333 |
| **\[enablemobile\]** | String | Enable or disable Mobility Extension feature | on: enable <br> off: disable |
| **\[ringsimultaneous\]** | String | Enable or disable Simultaneous Ringing of Mobility Extension | on: enable  off: disable |
| **\[mobileprefix\]** | String | A prefix match ing the outbound route | Blank or a specific prefix |
| **&lt;allowbeingmonitored&gt;** | String | Allow being monitored | on: enable <br> off: disable |
| **&lt;monitormode&gt;** | String | The monitor mode | Options: Disable, Extensive, Listen, Whisper, Barge-in |
| **&lt;ringtimeout&gt;** | String | The ring timeout in seconds | 30 |
| **&lt;maxduration&gt;** | String | The maximum call duration allowed in seconds | 600 |
| **&lt;dnd&gt;** | String | Enable or disable DND feature | on: enable <br> off: disable |
| **&lt;callrestriction&gt;** | String | Enable or disable outbound dialing restriction | on: enable <br> off: disable |
| **&lt;agentid&gt;** | String | The agent ID to be announced in the greeting prompt. If left null, the extension number will be announced instead. It is null by default. | 6362 |
| **\[inbound\]** | Object | Inbound calls, external numbers dial-in | N/A |
| **&lt;inboundid&gt;** | String | The inbound ID. With this parameter, operations like forwarding, query, and hangup can be performed. | 156785 |
| **&lt;from&gt;** | String | The caller's number | 1000 |
| **&lt;to&gt;** | String | The callee's number | 5003 |
| **&lt;trunk&gt;** | String | The name of the trunk that passes the inbound call | Sip-trunk |
| **\[outbound\]** | Object | Outbound calls: calls to external numbers | N/A |
| **&lt;ouboundid&gt;** | String | The outbound ID. With this parameter, operations like forwarding, query,andhangup can be performed. | 1 |
| **&lt;from&gt;** | String | The caller's number | 1000 |
| **&lt;to&gt;** | String | The callee's number | 5003 |
| **&lt;trunk&gt;** | String | The name of the trunk that passes the outbound call | Sip-trunk |
| **\[ext\]** | Object | The call party of an inbound call |  |
| **&lt;extid&gt;** | Int | The extension number of the extension that is on the line with the queried extension | 1001 |

**Possible error code: **30001

###  {#configure-an-individual-extension}




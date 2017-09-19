## Extension {#extension}

### Query Extension List {#query-extension-list}

Through this interface, developers could fetch basic information about S-Series extension list, like extension number, extension name, extension status, type, etc.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extensionlist/query?token=6cad9cee6e2ad94570636e7b3690aeb2](https://192.168.5.150:8088/api/v1.0.0/extensionlist/query?token=6cad9cee6e2ad94570636e7b3690aeb2)

**Request parameters descriptions:**

No parameter. Only need to send the request.

**Response sample:**

{"status":"Success","extlist":\[{"extnumber":"1000","status":"Idle","type":"FXS","port":"Span2-Port1","username":"1000"},{"extnumber":"1001","status":"Idle","type":"FXS","port":"Span2-Port2","username":"1001"},{"extnumber":"1002","status":"Registered","type":"SIP","username":"Amy"},{"extnumber":"1003","status":"Registered","type":"SIP","username":"1003"},{"extnumber":"1004","status":"Registered","type":"SIP","username":"1004"},{"extnumber":"1005","status":"Registered","type":"IAX","username":"1005"},{"extnumber":"1006","status":"Unavailable","type":"SIP","username":"Lisa"}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
|  | **&lt;extlist&gt;** | Object | Extension objects. |
| **&lt;extnumber&gt;** | String | The extension number | 1000 |
| **&lt;status&gt;** | String | Current status of the extension. | Unavailable, Registered, Ringing, Busy, Hold, Malfunction, Idle, Fxsnoport |
| **&lt;type&gt;** | String | The extension type | SIP,FXS |
| **\[port\]** | String | The extension port | Span1\_Port3 |
| **&lt;username&gt;** | String | The name | Ina Tang |

**Possible error code:** 30001

### Query One or More Extensions {#query-one-or-more-extensions}

Through this interface, developers could fetch detailed information about an individual extension or multiple extensions. For example, developers could query the advanced settings of an extension. When there are multiple requests, separate them with commas.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extension/query?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/query?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000"}

**Request parameters descriptions:**

1. Sending no parameter means query all information.
2. With parameters in request, developers could query specific information. Separate them with ",". For example, {"extid": "1000,1001,1002"}

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Query one or more extensions | 1000 |

**Response sample:**

{"status":"Success","extinfos":\[{"extnumber":"1000","username":"1000","status":"Idle","type":"FXS","port":"Span2-Port1","callerid":"1000","registername":"","registerpassword":"Yeastar202","maxregistrations":"1","loginpassword":"27499b15c12640fd2dbb237bd23da850","email":"","moblie":"","language":"System Default","hasvoicemail":"on","enablevmtoemail":"off","vmsecret":"1000","alwaysforward":"off","noanswerforward":"on","ntransferto":"Voicemail","ntransferprefix":"","busyforward":"on","btransferto":"Voicemail","btransferprefix":"","ringsimultaneous":"off","mobileprefix":"","enablemobile":"off","allowbeingmonitored":"off","monitormode":"Disabled","ringtimeout":"30","maxduration":"Follow System","dnd":"off","callrestriction":"off"}\]}

**Response parameters descriptions:**

|  | **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- | :--- |
|  | **&lt;extinfos&gt;** | Object | Object | N/A |
|  | **&lt;extnumber&gt;** | String | The extension number | 1000 |
|  | **&lt;\*\***username&gt;\*\* | String | The user's name | Ina Tang |
|  | **&lt;status&gt;** | String | Extension current status | Unavailable, Registered, Ringing, Busy, Hold, Malfunction, Idle, Fxsnoport |
|  | **&lt;type&gt;** | String | The extension type | SIP,FXS |
|  | **&lt;port&gt;** | String | The extension port | Span1\_Port3 |
|  | **&lt;callerid&gt;** | String | Caller ID | 1000 |
|  | **&lt;registername&gt;** | String | The registration name | 1000 |
|  | **&lt;registerpassword&gt;** | String | The registration password | Displayed in plaintext |
|  | **&lt;maxregistrations&gt;** | Int | Allowed maximum concurrent registrations | 5 |
|  | **\[loginpassword\]** | String | The login password | Displayed in MD5 ciphertext |
|  | **\[email\]** | String | The Email address | ina@yeastar.com |
|  | **\[mobile\]** | String | The mobile number | 134899999999 |
|  | **\[language\]** | String | The language of the system prompt | Systemdefault |
|  | **\[hasvoicemail\]** | String | Enable or disable voicemail feature | On: enable |
|  | **\[vmsecret\]** | Int | The voicemail password | 3000 |
|  | **\[enablevmtoemail\]** | String | Whether to enable send voicemail to email feature or not | On: enable |
|  | **\[alwaysforward\]** | String | Enable or disable always call forwarding feature | On: enable |
|  | **\[atransferto\]** | String | Forward destination | Voicemail: voicemail |
|  | **\[noanswerforward\]** | String | Enable or disable no answer call forwarding feature | On: enable |
|  | **\[ntransferto\]** | String | Forward destination | Voicemail: voicemail |
|  | **\[busyforward\]** | String | Enable or disable when busy call forwarding feature | On: enable |
|  | **\[btransferto\]** | String | Forward destination | Voicemail: voicemail |
|  | **\[enablemobile\]** | String | Enable or disable Mobility Extension feature | On: enable |
|  | **\[ringsimultaneous\]** | String | Enable or disable simultaneous ringing of mobility extension | On: enable |
|  | **\[mobileprefix\]** | String | A prefix matching the outbound route | Blank or a specific prefix |
|  | **\[allowbeingmonitored\]** | String | Allow being monitored | On: enable |
|  | **\[monitormode\]** | String | The monitor mode | Options: Disable, Extensive, Listen, Whisper, Barge-in |
|  | **\[ringtimeout\]** | String | The ring timeout in seconds | 30 |
|  | **\[maxduration\]** | String | The maximum call duration allowed in seconds | 600 |
|  | **\[dnd\]** | String | Enable or disable DND feature | On: enable |
|  | **\[callrestriction\]** | String | Enable or disable outbound dialing restriction | On: enable |
|  | **\[inbound\]** | object | Inbound calls, external numbers dial-in | N/A |
|  | **&lt;inboundid&gt;** | int | The inbound ID. With this parameter, operations like forwarding, query, and hangup can be performed. | 156785 |
|  | **&lt;from&gt;** | String | The caller's number | 1000 |
|  | **&lt;to&gt;** | String | The callee's number | 5003 |
| \*\*\[ext | outer\]\*\* | object | The called party of an inbound call; could be an extension or an outbound call. | 6500 |
|  | **\[status\]** | String | Call status | Talking: talking on the call |
|  | **&lt;\*\***trunk&gt;\*\* | String | The name of the trunk that passes the inbound call | Sip-trunk |
|  | **\[outbound\]** | object | Outbound calls: calls to external numbers | N/A |
|  | **&lt;ouboundid&gt;** | int | The outbound ID. With this parameter, operations like forwarding, query, and hangup can be performed. | 1 |
|  | **&lt;from&gt;** | String | The caller's number | 1000 |
|  | **&lt;to&gt;** | String | The callee's number | 5003 |
|  | **&lt;trunk&gt;** | String | The name of the trunk that passes the outbound call | Sip-trunk |
|  | **\[status\]** | String | Call status | Talking: talking on the call |
|  | **&lt;agentid&gt;** | String | The agent ID to be announced in the greeting prompt. This parameter is optional. If left null, the extension number will be announced instead. It is null by default. | 6932 |

**Possible error code:** 30001

### Configure an Individual Extension {#configure-an-individual-extension}

Through this interface, developers could configure extension number, name, concurrent registrations, email address, mobility extension, etc. of an individual extension.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extension/update?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/update?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1002","username": "Amy"}

**Request parameters descriptions:**

|  | **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- | :--- |
|  | **&lt;extensionupdate&gt;** | String | Configure an individual extension | N/A |
|  | **&lt;extid&gt;** | String | The original extension number | 1001 |
|  | **\[extnumber\]** | String | Modified extension number | 1000 |
|  | **\[username\]** | String | The user's name | Letters and digits, maximum length 31. Could be blank. |
|  | **&lt;callerid&gt;** | String | The extension's Caller ID | Letters and digits, maximum length 31. Could be blank. |
|  | **\[registername\]** | String | The registration name | Letters and digits, maximum length 31. Cannot be blank. |
| **&lt;registerpassword&gt;** | String | The registration password | ;&\"\'\&lt;&gt; | \ are invalid for password. Neither is space character valid. |
|  | **&lt;maxregistrations&gt;** | String | Allowed maximum concurrent registrations | A range from 1 to 5 |
| **\[loginpassword\]** | String | The login password | ;&\"\'\&lt;&gt; | \ are invalid for password. Neither is space character valid. |
|  | **\[email\]** | String | The Email address | apple@yeastar.com |
|  | **\[mobile\]** | String | The mobile number | Digits. Maximum length is 31. |
|  | **\[hasvoicemail\]** | String | Enable or disable voicemail feature | On: enable |
|  | **\[enablevmtoemail\]** | String | Whether to enable send voicemail to email feature or not | On: enable |
|  | **\[vmsecret\]** | String | The voicemail password | Digits. Maximum length is 63. |
|  | **\[alwaysforward\]** | String | Enable or disable always call forwarding feature | On: enable |
|  | **\[atransferto\]** | String | Forward destination | Options: |
|  | **\[atransferext\]** | String | The extension ID, when the forward destination is extension. | 3002 |
|  | **\[atransferprefix\]** | String | The outbound calls prefix, when the forward destination is a custom number or the extension's associated mobile number | Digits. Maximum length is 7. |
|  | **\[atransfernum\]** | String | The number of the outbound call, when the forward destination is a custom number or the extension's associated mobile number | Digits. Maximum length is 15. The forward destination Custom Number can't be blank. |
|  | **\[noanswerforward\]** | String | Enable or disable no answer call forwarding feature | On: enable |
|  | **\[ntransferto\]** | String | Forward destination | Options: |
|  | **\[ntransferext\]** | String | The extension ID, when the forward destination is extension. | 3002 |
|  | **\[ntransferprefix\]** | String | The outbound calls prefix, when the forward destination is a custom number or the extension's associated mobile number. | Digits. Maximum length is 15. The forward destination Custom Number can't be blank. |
|  | **\[ntransfernum\]** | String | The number of the outbound call, when the forward destination is a custom number or the extension's associated mobile number. | Digits. Maximum length is 15. Cannot be blank. |
|  | **\[busyforward\]** | String | Enable or disable when busy call forwarding feature | On: enable |
|  | **\[btransferto\]** | String | Forward destination | Options: |
|  | **\[btransferext\]** | String | The extension ID, when the forward destination is extension. | 3002 |
|  | **\[btransferprefix\]** | String | The outbound calls prefix, when the forward destination is a custom number or the extension's associated mobile number. | Digits. Maximum length is 7. |
|  | **\[btransfernum\]** | String | The number of the outbound call, when the forward destination is a custom number or the extension's associated mobile number | Digits. Maximum length is 15. The forward destination Custom Number can't be blank. |
|  | **\[enablemobile\]** | String | Enable or disable Mobility Extension feature | On: enable |
|  | **\[ringsimultaneous\]** | String | Enable or disable simultaneous ringing of mobility extension | On: enable |
|  | **\[mobileprefix\]** | String | A prefix matching the outbound route | Digits. Maximum length is 7. |
|  | **\[allowbeingmonitored\]** | String | Allow being monitored | On: enable |
|  | **\[monitormode\]** | String | How to monitor the calls | Options: |
|  | **\[ringtimeout\]** | String | The ring timeout in seconds | Options: 15, 30, 60, 120, 300 |
|  | **\[maxduration\]** | String | The maximum call duration allowed in seconds | Options: |
|  | **\[dnd\]** | String | Enable or disable DND feature | On: enable |
|  | **\[callrestriction\]** |  | Enable or disable outbound dialing restriction | On: enable |
|  | **\[agentid\]** | String | The agent ID to be announced in the greeting prompt. This parameter is optional. If left null, the extension number will be announced instead. It is null by default. | 6932 |

**Possible error code:** 10006, 10007

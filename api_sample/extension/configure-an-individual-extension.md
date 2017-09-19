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
| **&lt;registerpassword&gt;** | String | The registration password | ;&\"\'\&lt;&gt; |  are invalid for password. Neither is space character valid. |
|  | **&lt;maxregistrations&gt;** | String | Allowed maximum concurrent registrations | A range from 1 to 5 |
| **\[loginpassword\]** | String | The login password | ;&\"\'\&lt;&gt; |  are invalid for password. Neither is space character valid. |
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


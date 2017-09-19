# Configure an Individual Extension

Through this interface, developers could configure extension number, name, concurrent registrations, email address, mobility extension, etc. of an individual extension.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/extension/update?token=7d20390952e15eb72b0a1df7172de65c){version}[/extension/update?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/update?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1002","username": "Amy"}

**Request parameters descriptions:**

| Parameter Name | Type | Description | Sample |
| :--- | :--- | :--- | :--- |
| &lt;extid&gt; | int | The extension number of the extension to be configured | 1001 |
| \[extnumber\] | int | Modified extension number | 1000 |
| \[username\] | string | The user's name | Letters and digits, maximum length 31. Could be blank. |
| \[callerid\] | string | The extension's Caller ID | Letters and digits, maximum length 31. Could be blank. |
| \[registername\] | string | The registration name | Letters and digits, maximum length 31. Cannot be blank. |
| \[registerpassword\] | string | The registration password | ;&\"\'\&lt;&gt;\|\ are invalid for password. Neither is space character valid. Maximum length is 31. Cannot be blank. |
| \[maxregistrations\] | string | Allowed maximum concurrent registrations | A range from 1 to 5 |
| \[loginpassword\] | string | The login password | ;&\"\'\&lt;&gt;\|\ are invalid for password. Neither is space character valid. Length from 6 to 63. |
| \[email\] | string | The Email address | apple@yeastar.com |
| \[mobile\] | string | The mobile number | Digits. Maximum length is 31.When calls are set to be forwarded to the extension's associated mobile number or when Mobility Extension is enabled, this cannot be blank. |
| \[hasvoicemail\] | string | Enable or disable Voicemail feature | On: enable  Off: disable |
| \[enablevmtoemail\] | string | Whether to enable Send Voicemail to Email feature or not | On: enable Off: disable |
| \[vmsecret\] | string | The voicemail password | Digits. Maximum length is 63. |
| \[alwaysforward\] | string | Enable or disable Always Call Forwarding feature | On: enable  Off: disable |
| \[atransferto\] | string | Always call forwarding destination | Options: Voicemail, Extension, Mobile Number, Custom Number |
| \[atransferext\] | string | The extension ID, when the forward destination is extension. | 3002 |
| \[atransferprefix\] | string | The outbound calls prefix, when the forward destination is a custom number or the extension's associated mobile number | Digits. Maximum length is 7. |
| \[atransfernum\] | string | The number of the outbound call, when the forward destination is a custom number or the extension's associated mobile number | Digits. Maximum length is 15. The forward destination Custom Number can't be blank. |
| \[noanswerforward\] | string | Enable or disable no answer call forwarding feature | On: enableOff: disable |
| \[ntransferto\] | string | No answer call forwarding destination | Options: Voicemail, Extension, Mobile Number, Custom Number |
| \[ntransferext\] | string | The extension ID, when the forward destination is extension. | 3002 |
| \[ntransferprefix\] | string | The outbound calls prefix, when the forward destination is a custom number or the extension's associated mobile number. | Digits. Maximum length is 15. The forward destination Custom Number can't be blank. |
| \[ntransfernum\] | string | The number of the outbound call, when the forward destination is a custom number or the extension's associated mobile number. | Digits. Maximum length is 15. Cannot be blank. |
| \[busyforward\] | string | Enable or disable when busy call forwarding feature | On: enable  Off: disable |
| \[btransferto\] | string | When busy call forwarding destination | Options: Voicemail, Extension, Mobile Number, Custom Number |
| \[btransferext\] | string | The extension ID, when the forward destination is extension. | 3002 |
| \[btransferprefix\] | string | The outbound calls prefix, when the forward destination is a custom number or the extension's associated mobile number. | Digits. Maximum length is 7. |
| \[btransfernum\] | string | The number of the outbound call, when the forward destination is a custom number or the extension's associated mobile number | Digits. Maximum length is 15. The forward destination Custom Number can't be blank. |
| \[enablemobile\] | string | Enable or disable Mobility Extension feature | On: enable Off: disable |
| \[ringsimultaneous\] | string | Enable or disable Simultaneous Ringing of Mobility Extension | On: enable  Off: disable |
| \[mobileprefix\] | string | A prefix matching the outbound route | Digits. Maximum length is 7. |
| \[allowbeingmonitored\] | string | Allow being monitored | On: enable  Off: disable |
| \[monitormode\] | string | How to monitor the calls | Options: Disabled, Extensive,Listen, Whisper, Barge-in |
| \[ringtimeout\] | string | The ring timeout in seconds | Options: 15, 30, 60, 120, 300 |
| \[maxduration\] | string | The maximum call duration allowed in seconds | Options: Follow System, Unlimited, 60, 300, 600, 900, 1800, 3600, 6000 |
| \[dnd\] | string | Enable or disable DND feature | On: enable  Off: disable |
| \[callrestriction\] | string | Enable or disable Outbound Dialing Restriction | On: enable  Off: disable |
| \[agentid\] | string | The agent ID to be announced in the greeting prompt. If left null, the extension number will be announced instead. It is null by default. | 6932 |

**Possible error code: **10006, 10007


### Change of Extension Status {#change-of-extension-status}

The PBX will send a report to the application server when the extension status changes. So the application server can sync the changes timely.

**Precondition:** need to enable extension's status monitor in the "Settings-&gt;PBX-&gt;General-&gt;API" of S-Series VoIP PBX Web interface.

**Extension Status Descriptions:**

* Ringing: send a report to the application server when an extension is ringing.
* Busy: send a report to the application server when an extension goes off-hook.

Note: an IP phone or analog phone is considered busy when it goes off-hook.

* Idle: send a report to the application server when an extension goes on-hook.
* Registered: send a report when the IP phone's status is changed from "unregistered" to "registered" or the phone's IP address has been changed.
* Unregistered: send a report when the IP phone's status is changed from “registered” to “unregistered”.

The following will trigger the status to change to “unregistered”:

1. Unregister the account on the IP phone.

2. Fail to refresh the registration in the subscription cycle due to power or network outage.

**Report sample:**

{"action":"ExtensionStatus","extension":"1010","status":"Registered"}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Status change of extension | ExtensionStatus |
| **&lt;extension&gt;** | Int | The number of extension with status change | 1010 |
| **&lt;status&gt;** | String | The status of extension after change | Registered |




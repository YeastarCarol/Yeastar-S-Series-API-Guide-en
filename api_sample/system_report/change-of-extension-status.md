### Change of Extension Status {#change-of-extension-status}

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


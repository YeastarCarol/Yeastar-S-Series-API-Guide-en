## System Report {#system-report}

### System Startup {#system-startup}

When the PBX finishes startup, a report will be sent to the application server.

**Report sample: N/A**

**Report parameters descriptions:**

1.  No parameter, just report the startup.
2.  Precondition: the application server is connected to the API server and finishes the authentication.

### Change of System Configuration {#change-of-system-configuration}

The PBX will send a report to the application server when the PBX’s configuration changes. So the application server can sync the changes timely.

At present, only the trunk and extension configuration change will be reported. But the detailed changes won&#039;t be provided in the report.

**Report sample:**

{&quot;action&quot;:&quot;ConfigChange&quot;,&quot;type&quot;:&quot;trunk&quot;,&quot;trunkname&quot;:&quot;SIP-142&quot;,&quot;operation&quot;:&quot;del&quot;}

### Change of Extension Status {#change-of-extension-status}

*   Ringing: send a report to the application server when an extension is ringing.
*   Busy: send a report to the application server when an extension goes off-hook.

Note: an IP phone or analog phone is considered busy when it goes off-hook.

*   Idle: send a report to the application server when an extension goes on-hook.
*   Registered: send a report when the IP phone&#039;s status is changed from &quot;unregistered&quot; to &quot;registered&quot; or the phone&#039;s IP address has been changed.
*   Unregistered: send a report when the IP phone&#039;s status is changed from “registered” to “unregistered”.

The following will trigger the status to change to “unregistered”:

1\. Unregister the account on the IP phone.

2\. Fail to refresh the registration in the subscription cycle due to power or network outage.

**Report sample:**

{&quot;action&quot;:&quot;ExtensionStatus&quot;,&quot;extension&quot;:&quot;1010&quot;,&quot;status&quot;:&quot;Registered&quot;}
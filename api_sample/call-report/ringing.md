# Ringing

The PBX will send a report to the application server when an extension is ringing.

Ringing \(the called party\) and ring back \(the calling party\) coexist. Calls with external numbers and internal calls will both be reported. In the report, the party who triggers the call will appear first.

**Report sample:**

**1.An internal call between extensions:**

{"action":"RING","callid":"1495706238.328","ext":{"extid":"1000"},"ext":{"extid":"1002"}}

**2.An external call:**

{"action":"RING","callid":"1495771030.365","outbound":{"from":"1002","to":"42003","trunk":"sip-142","outboundid":"1495771030.366"},"ext":{"extid":"1002"}}


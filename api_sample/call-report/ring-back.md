# Ring Back

The PBX will send a report to the application server when the called party \(extension/inbound call\) rings back the calling party.

Ringing \(the called party\) and ring back \(the calling party\) coexist. Calls with external numbers and internal calls will both be reported. In the report, the party who triggers the call will appear first.

**Report sample:**

{"action":"ALERT","callid":"1495706238.328","ext":{"extid":"1002"}}


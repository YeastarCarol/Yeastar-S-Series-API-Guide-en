# Call Transfer

When there is a call transferred inside the PBX, the PBX will send a report to the application server.

The report only includes operations performed by the extensions, for example, dialing "\*03" and "\*3" feature codes, follow me settings, etc. Transfer controlled by API will not be reported.

**Report sample:**

{"action":"Tranfer","callid":"1494834266.75","inbound":{"from":"3009","to":"2002","trunk":"DIGIT1","inboundid":"1494834266.75"}}


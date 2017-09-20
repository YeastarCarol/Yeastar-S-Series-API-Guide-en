# Keypress

This event is used report key pressed in the IVRs.

When a call reaches IVR, and the IVR's keypress event is triggered, the PBX will send the event to the application server.

**Report sample:**

{"action":"DTMF","callid":"1495705009.315","outbound":{"from":"1002","to":"41000","trunk":"SIP-142","outboundid":"1495705009.316"},"info":"\#"}


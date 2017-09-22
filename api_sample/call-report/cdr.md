# CDR

CDR is raw data of all call activities; records of all calls from the beginning to the end will be kept.

When a call is released, the PBX will send a report to the application server in real time.

**Report sample:**

**1. Extension's Internal Call:**

{"action":"NewCdr","callid":"1495779310.371","timestart":"2017-05-25 22:15:10","callfrom":"1002","callto":"1000","desttrunkname":"","callduraction":"3","talkduraction":"2","status":"ANSWERED","type":"Internal"}

**2. Extension Makes an External Call:**

{"action":"NewCdr","callid":"1505352615.274","timestart":"2017-09-14 09:30:15","callfrom":"1000","callto":"91000","desttrunkname":"Apple\_test","callduraction":"29","talkduraction":"29","status":"ANSWERED","type":"Outbound","pincode":"1000","recording":"20170914093038-1505352615.274-1000-91000-Outbound.wav"}

**3. External Number Dials Extension:**

{"action":"NewCdr","callid":"1505352445.265","timestart":"2017-09-14 09:27:25","callfrom":"102","callto":"1000","srctrunkname":"Apple\_test","callduraction":"38","talkduraction":"29","status":"ANSWERED","type":"Inbound","recording":"20170914092747-1505352445.265-102-1000-Inbound.wav"}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- |
| **&lt;cdrid&gt;** | String | The CDR ID | 123456789 |
| **&lt;callid&gt;** | String | A unique identifier for the call | 2000 |
| **\[timestart\]** | String | The start time of the call | 2017-09-14 09:30:15 |
| **\[callfrom\]** | String | The caller's number | 102 |
| **\[callto\]** | String | The callee's number | 1000 |
| **\[callduraction\]** | String | The call duration | 29 |
| **\[talkduraction\]** | String | The talk duration | 29 |
| **\[srctrunkname\]** | String | The name of the source trunk | Apple\_test |
| **\[dstrunkname\]** | String | The name of the destination trunk | Apple\_test |
| **\[status\]** | String | Call status | ANSWERED, NO ANSWER, FAILED, VOICEMAIL |
| **\[type\]** | String | The call type | Inbound, Outbound, Internal, Callback, Transfer |
| **\[pincode\]** | Int | The password | 1000 |
| **\[recording\]** | String | The name of the call recording file | 20170914092747-1505352445.265-102-1000-Inbound.wav |




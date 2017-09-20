# CDR

CDR is raw data of all call activities; records of all calls from the beginning to the end will be kept.

When a call is released, the PBX will send a report to the application server in real time.

**Report sample:**

**1.Extension's Internal Call:**

{"action":"NewCdr","callid":"1495779310.371","timestart":"2017-05-25 22:15:10","callfrom":"1002","callto":"1000","desttrunkname":"","callduraction":"3","talkduraction":"2","status":"ANSWERED","type":"Internal"}

**2.Extension Dials External Call:**

{"action":"NewCdr","callid":"1495779454.374","timestart":"2017-05-25 22:17:34","callfrom":"1002","callto":"41004","desttrunkname":"sip-142","callduraction":"4","talkduraction":"4","status":"ANSWERED","type":"Outbound"}

**3.External Number Dials Extension:**

{"action":"NewCdr","callid":"1495779821.377","timestart":"2017-05-25 22:23:41","callfrom":"1000","callto":"1002","srctrunkname":"sip-142","callduraction":"18","talkduraction":"9","status":"ANSWERED","type":"Inbound"}

**Report parameters descriptions:**

| Parameter Name | Type | Description | Sample |
| :--- | :--- | :--- | :--- |
| &lt;cdrid&gt; | string | The CDR ID | 123456789 |
| \[callid\] | string | A unique identifier for the call | 2000 |
| \[timestart\] | string | The start time of the call | 2017-05-25 22:26:20 |
| \[callfrom\] | string | The caller's number | 1000 |
| \[callto\] | string | The callee's number | 18000000 |
| \[callduraction\] | string | The call duration | 12:10:10 AM |
| \[talkduraction\] | string | The talk duration | 00:10:00 |
| \[srctrunkname\] | string | The name of the source trunk | Sps129 |
| \[dstrunkname\] | string | The name of the destination trunk | Sps128 |
| \[status\] | string | Call status | ANSWEREDNOANSWERFAILEDVOICEMAIL |
| \[type\] | string | The call type | Inbound, Outbound, Internal,Callback, Transfer |
| \[pincode\] | int | The password | 122 |
| \[recording\] | string | The name of the call recording file | hello001 |




## Call Report {#call-report}

### Ringing {#ringing}

The PBX will send a report to the application server when an extension is ringing.

Ringing \(the called party\) and ring back \(the calling party\) coexist. Calls with external numbers and internal calls will both be reported. In the report, the party who triggers the call will appear first.

**Report sample:**

1. **An internal call between extensions:**

{"action":"RING","callid":"1495706238.328","ext":{"extid":"1000"},"ext":{"extid":"1002"}}

1. **An external call:**

{"action":"RING","callid":"1495771030.365","outbound":{"from":"1002","to":"42003","trunk":"sip-142","outboundid":"1495771030.366"},"ext":{"extid":"1002"}}

### Ring Back {#ring-back}

The PBX will send a report to the application server when the called party \(extension/inbound call\) rings back the calling party.

Ringing \(the called party\) and ring back \(the calling party\) coexist. Calls with external numbers and internal calls will both be reported. In the report, the party who triggers the call will appear first.

**Report sample:**

{"action":"ALERT","callid":"1495706238.328","ext":{"extid":"1002"}}

### Answer a Call {#answer-a-call}

The PBX will send a report to the application server when an extension answers a call.

Answering call \(the called party\) and call answered \(the calling party\) coexist. In the report, the party who triggers the call will appear first.

**Report sample:**

{"action":"RI","callid":"1495706238.328","ext":{"extid":"1000"},"ext":{"extid":"1002"}}

### Call Answered {#call-answered}

The PBX will send a report to the application server when the calling party's call is answered.

Answering call \(the called party\) and call answered \(the calling party\) coexist. In the report, the party who triggers the call will appear first.

**Report sample:**

{"action":"ANSWERED","callid":"1495706238.328","ext":{"extid":"1002"},"ext":{"extid":"1000"}}

### Call Released {#call-released}

The PBX will send a report to the application server when a call is released. In the report, the party who ends the call will appear first.

**Report sample:**

{"action":"BYE","callid":"1495706238.328","ext":{"extid":"1000"},"ext":{"extid":"1002"}}

### Call Transfer {#call-transfer}

When there is a call transferred inside the PBX, the PBX will send a report to the application server.

The report only includes operations performed by the extensions, for example, dialing "_03" and "_3" feature codes, follow me settings, etc. Transfer controlled by API will not be reported.

**Report sample:**

{"action":"Tranfer","callid":"1494834266.75","inbound":{"from":"3009","to":"2002","trunk":"DIGIT1","inboundid":"1494834266.75"}}

### Call Failure {#call-failure}

Generally, call failure event will appear in the response message of the API request. In certain circumstances, the PBX will send the report.

Call failure is defined as calls that are failed to connect.

Failure of calls initiated manually and by the API will both be reported.

**Report sample:**

1. **Extension outbound call restriction:**

{"action":"CallFailed","reason":"NO Outbound Restriction","callid":"1495420603.349"}

1. **DND enabled:**

{"action":"CallFailed","reason":"DND","callid":"1495186077.229","ext":{"extid":"1005"}}

1. **No available trunks:**

{"action":"CallFailed","reason":"Line unreachable","callid":"1495184155.216","ext":{"extid":"1002"}}

1. **Extension A dials extension B, extension B \(call forwarding disabled\) rejects the call:**

{"action":"CallFailed","reason":"User busy","callid":"1495770583.355"}

### Inbound Call Request {#inbound-call-request}

If the trunk's API has Inbound Call Answering Control enabled, then whenever there's a call to this trunk, the PBX will send an INVITE event to the application server.

**Report sample:**

{"action":"Invite","callid":"1495707950.331","inbound":{"from":"1000","to":"1002","trunk":"sip-142","inboundid":"1495707950.331"}}

### Inbound Call {#inbound-call}

If the trunk's API has Inbound Call Answering Control enabled, then when the trunk answers call, the PBX will send an Incoming event to the application server.

**Report sample:**

{"action":"Incoming","callid":"1495707950.331","inbound":{"from":"1000","to":"1002","trunk":"sip-142","inboundid":"1495707950.331"}}

### Keypress {#keypress}

This event is used report key pressed in the IVRs.

When a call reaches IVR, and the IVR's keypress event is triggered, the PBX will send the event to the application server.

**Report sample:**

{"action":"DTMF","callid":"1495705009.315","outbound":{"from":"1002","to":"41000","trunk":"SIP-142","outboundid":"1495705009.316"},"info":"\#"}

### CDR {#cdr}

CDR is raw data of all call activities; records of all calls from the beginning to the end will be kept.

When a call is released, the PBX will send a report to the application server in real time.

**Report sample:**

1. **Extension's Internal Call:**

{"action":"NewCdr","callid":"1495779310.371","timestart":"2017-05-25 22:15:10","callfrom":"1002","callto":"1000","desttrunkname":"","callduraction":"3","talkduraction":"2","status":"ANSWERED","type":"Internal"}

1. **Extension Dials External Call:**

{"action":"NewCdr","callid":"1495779454.374","timestart":"2017-05-25 22:17:34","callfrom":"1002","callto":"41004","desttrunkname":"sip-142","callduraction":"4","talkduraction":"4","status":"ANSWERED","type":"Outbound"}

1. **External Number Dials Extension:**

{"action":"NewCdr","callid":"1495779821.377","timestart":"2017-05-25 22:23:41","callfrom":"1000","callto":"1002","srctrunkname":"sip-142","callduraction":"18","talkduraction":"9","status":"ANSWERED","type":"Inbound"}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;cdrid&gt;** | String | The CDR ID | 123456789 |
| **\[callid\]** | String | A unique identifier for the call | 2000 |
| **\[timestart\]** | String | The start time of the call | 2017-05-25 22:26:20 |
| **\[callfrom\]** | String | The caller's number | 1000 |
| **\[callto\]** | String | The callee's number | 18000000 |
| **\[callduraction\]** | String | The call duration | 12:10:10 AM |
| **\[talkduraction\]** | String | The talk duration | 00:10:00 |
| **\[srctrunkname\]** | String | The name of the source trunk | Sps129 |
| **\[dstrunkname\]** | String | The name of the destination trunk | Sps128 |
| **\[status\]** | String | Call status | ANSWERED |
| **\[type\]** | String | The call type | Inbound, Outbound, Internal, |
| **\[pincode\]** | Int | The password | 122 |
| **\[recording\]** | String | The name of the global recording file | hello001 |

### Acquire Global Recording files {#acquire-global-recording-files}

Through this interface, global recording files of a IPPBX can be acquired.

The acquisition method is as follows:

Step1: fetch the name of the global recording file through the “recording” parameter in the CDR event Step 2: get a random string consisting of numbers and characters, which is created by the system, by sending a request with the file name \(as the request example below\) to IPPBX

Step 3: combine the randon string with other elements to form a specific download request address

**Request method:** POST \(HTTPS\)

**Request address:**

[https://192.168.5.150:8088/api/v1.0.1/recording/get\_random?token=3efd4cd64e0d06e84a98230601428106](https://192.168.5.150:8088/api/v1.0.1/recording/get_random?token=3efd4cd64e0d06e84a98230601428106)

**Request sample:**

{"recording":"20170901181806-1504261084.7-1001-1003-Internal.wav"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;recording&gt;** | String | The name of the global recording file | hello001 |

**Response sample:**

{"status":"Success","recording":"20170901181806-1504261084.7-1001-1003-Internal.wav","random":"120732c546381fb020f17fba676b0ea0"}

**Response parameters:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;Status&gt;** | String | Result | Success or Failed |
| **&lt;recording&gt;** | String | The name of the global recording file | Hello001 |
| **&lt;random&gt;** | String | A random string created for global recording file download. It serves as a component of a specified request address for download. |  |

**Download request address sample \( random string combination method\):**

[https://192.168.5.150:8088/api/v1.0.1/recording/download?recording=20170724103619-1500860177.268-2000-2001-Internal.wav&amp;random=7e60c59d187783f06ccc03621c4ad736&amp;token=75c5891b32203d0615f9e3753a7cb779](https://192.168.5.150:8088/api/v1.0.1/recording/download?recording=20170724103619-1500860177.268-2000-2001-Internal.wav&amp;random=7e60c59d187783f06ccc03621c4ad736&amp;token=75c5891b32203d0615f9e3753a7cb779)

### Prompt Play End {#prompt-play-end}

This is used to report the event when the prompt played to the extension and the external number ends.

**Report sample:**

{"action":"PlayPromptEnd","callid":"1495780325.384","ext":{"extid":"1002"},"prompt":"111"}

### Customer Satisfaction Survey Result Sending {#customer-satisfaction-survey-result-sending}

Once the DTMF data is collected from callers, API will send the customer satisfaction survey result to the client automatically.

**Report sample:**

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;surveyresult&gt;** | String | The result of the customer satisfaction survey. \( the DTMF data collected from the caller\) | 1 |




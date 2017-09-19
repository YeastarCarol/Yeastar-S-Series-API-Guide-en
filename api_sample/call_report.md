## Call Report {#call-report}

### Ringing {#ringing}

The PBX will send a report to the application server when an extension is ringing.

Ringing (the called party) and ring back (the calling party) coexist. Calls with external numbers and internal calls will both be reported. In the report, the party who triggers the call will appear first.

**Report sample:**

1.  **An internal call between extensions:**

{&quot;action&quot;:&quot;RING&quot;,&quot;callid&quot;:&quot;1495706238.328&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1000&quot;},&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;}}

1.  **An external call:**

{&quot;action&quot;:&quot;RING&quot;,&quot;callid&quot;:&quot;1495771030.365&quot;,&quot;outbound&quot;:{&quot;from&quot;:&quot;1002&quot;,&quot;to&quot;:&quot;42003&quot;,&quot;trunk&quot;:&quot;sip-142&quot;,&quot;outboundid&quot;:&quot;1495771030.366&quot;},&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;}}

### Ring Back {#ring-back}

The PBX will send a report to the application server when the called party (extension/inbound call) rings back the calling party.

Ringing (the called party) and ring back (the calling party) coexist. Calls with external numbers and internal calls will both be reported. In the report, the party who triggers the call will appear first.

**Report sample:**

{&quot;action&quot;:&quot;ALERT&quot;,&quot;callid&quot;:&quot;1495706238.328&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;}}

### Answer a Call {#answer-a-call}

The PBX will send a report to the application server when an extension answers a call.

Answering call (the called party) and call answered (the calling party) coexist. In the report, the party who triggers the call will appear first.

**Report sample:**

{&quot;action&quot;:&quot;RI&quot;,&quot;callid&quot;:&quot;1495706238.328&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1000&quot;},&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;}}

### Call Answered {#call-answered}

The PBX will send a report to the application server when the calling party&#039;s call is answered.

Answering call (the called party) and call answered (the calling party) coexist. In the report, the party who triggers the call will appear first.

**Report sample:**

{&quot;action&quot;:&quot;ANSWERED&quot;,&quot;callid&quot;:&quot;1495706238.328&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;},&quot;ext&quot;:{&quot;extid&quot;:&quot;1000&quot;}}

### Call Released {#call-released}

The PBX will send a report to the application server when a call is released. In the report, the party who ends the call will appear first.

**Report sample:**

{&quot;action&quot;:&quot;BYE&quot;,&quot;callid&quot;:&quot;1495706238.328&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1000&quot;},&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;}}

### Call Transfer {#call-transfer}

When there is a call transferred inside the PBX, the PBX will send a report to the application server.

The report only includes operations performed by the extensions, for example, dialing &quot;*03&quot; and &quot;*3&quot; feature codes, follow me settings, etc. Transfer controlled by API will not be reported.

**Report sample:**

{&quot;action&quot;:&quot;Tranfer&quot;,&quot;callid&quot;:&quot;1494834266.75&quot;,&quot;inbound&quot;:{&quot;from&quot;:&quot;3009&quot;,&quot;to&quot;:&quot;2002&quot;,&quot;trunk&quot;:&quot;DIGIT1&quot;,&quot;inboundid&quot;:&quot;1494834266.75&quot;}}

### Call Failure {#call-failure}

Generally, call failure event will appear in the response message of the API request. In certain circumstances, the PBX will send the report.

Call failure is defined as calls that are failed to connect.

Failure of calls initiated manually and by the API will both be reported.

**Report sample:**

1.  **Extension outbound call restriction:**

{&quot;action&quot;:&quot;CallFailed&quot;,&quot;reason&quot;:&quot;NO Outbound Restriction&quot;,&quot;callid&quot;:&quot;1495420603.349&quot;}

1.  **DND enabled:**

{&quot;action&quot;:&quot;CallFailed&quot;,&quot;reason&quot;:&quot;DND&quot;,&quot;callid&quot;:&quot;1495186077.229&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1005&quot;}}

1.  **No available trunks:**

{&quot;action&quot;:&quot;CallFailed&quot;,&quot;reason&quot;:&quot;Line unreachable&quot;,&quot;callid&quot;:&quot;1495184155.216&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;}}

1.  **Extension A dials extension B, extension B (call forwarding disabled) rejects the call:**

{&quot;action&quot;:&quot;CallFailed&quot;,&quot;reason&quot;:&quot;User busy&quot;,&quot;callid&quot;:&quot;1495770583.355&quot;}

### Inbound Call Request {#inbound-call-request}

If the trunk&#039;s API has Inbound Call Answering Control enabled, then whenever there&#039;s a call to this trunk, the PBX will send an INVITE event to the application server.

**Report sample:**

{&quot;action&quot;:&quot;Invite&quot;,&quot;callid&quot;:&quot;1495707950.331&quot;,&quot;inbound&quot;:{&quot;from&quot;:&quot;1000&quot;,&quot;to&quot;:&quot;1002&quot;,&quot;trunk&quot;:&quot;sip-142&quot;,&quot;inboundid&quot;:&quot;1495707950.331&quot;}}

### Inbound Call {#inbound-call}

If the trunk&#039;s API has Inbound Call Answering Control enabled, then when the trunk answers call, the PBX will send an Incoming event to the application server.

**Report sample:**

{&quot;action&quot;:&quot;Incoming&quot;,&quot;callid&quot;:&quot;1495707950.331&quot;,&quot;inbound&quot;:{&quot;from&quot;:&quot;1000&quot;,&quot;to&quot;:&quot;1002&quot;,&quot;trunk&quot;:&quot;sip-142&quot;,&quot;inboundid&quot;:&quot;1495707950.331&quot;}}

### Keypress {#keypress}

This event is used report key pressed in the IVRs.

When a call reaches IVR, and the IVR&#039;s keypress event is triggered, the PBX will send the event to the application server.

**Report sample:**

{&quot;action&quot;:&quot;DTMF&quot;,&quot;callid&quot;:&quot;1495705009.315&quot;,&quot;outbound&quot;:{&quot;from&quot;:&quot;1002&quot;,&quot;to&quot;:&quot;41000&quot;,&quot;trunk&quot;:&quot;SIP-142&quot;,&quot;outboundid&quot;:&quot;1495705009.316&quot;},&quot;info&quot;:&quot;#&quot;}

### CDR {#cdr}

CDR is raw data of all call activities; records of all calls from the beginning to the end will be kept.

When a call is released, the PBX will send a report to the application server in real time.

**Report sample:**

1.  **Extension&#039;s Internal Call:**

{&quot;action&quot;:&quot;NewCdr&quot;,&quot;callid&quot;:&quot;1495779310.371&quot;,&quot;timestart&quot;:&quot;2017-05-25 22:15:10&quot;,&quot;callfrom&quot;:&quot;1002&quot;,&quot;callto&quot;:&quot;1000&quot;,&quot;desttrunkname&quot;:&quot;&quot;,&quot;callduraction&quot;:&quot;3&quot;,&quot;talkduraction&quot;:&quot;2&quot;,&quot;status&quot;:&quot;ANSWERED&quot;,&quot;type&quot;:&quot;Internal&quot;}

1.  **Extension Dials External Call:**

{&quot;action&quot;:&quot;NewCdr&quot;,&quot;callid&quot;:&quot;1495779454.374&quot;,&quot;timestart&quot;:&quot;2017-05-25 22:17:34&quot;,&quot;callfrom&quot;:&quot;1002&quot;,&quot;callto&quot;:&quot;41004&quot;,&quot;desttrunkname&quot;:&quot;sip-142&quot;,&quot;callduraction&quot;:&quot;4&quot;,&quot;talkduraction&quot;:&quot;4&quot;,&quot;status&quot;:&quot;ANSWERED&quot;,&quot;type&quot;:&quot;Outbound&quot;}

1.  **External Number Dials Extension:**

{&quot;action&quot;:&quot;NewCdr&quot;,&quot;callid&quot;:&quot;1495779821.377&quot;,&quot;timestart&quot;:&quot;2017-05-25 22:23:41&quot;,&quot;callfrom&quot;:&quot;1000&quot;,&quot;callto&quot;:&quot;1002&quot;,&quot;srctrunkname&quot;:&quot;sip-142&quot;,&quot;callduraction&quot;:&quot;18&quot;,&quot;talkduraction&quot;:&quot;9&quot;,&quot;status&quot;:&quot;ANSWERED&quot;,&quot;type&quot;:&quot;Inbound&quot;}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;cdrid&gt;** | String | The CDR ID | 123456789 |
| **[callid]** | String | A unique identifier for the call | 2000 |
| **[timestart]** | String | The start time of the call | 2017-05-25 22:26:20 |
| **[callfrom]** | String | The caller&#039;s number | 1000 |
| **[callto]** | String | The callee&#039;s number | 18000000 |
| **[callduraction]** | String | The call duration | 12:10:10 AM |
| **[talkduraction]** | String | The talk duration | 00:10:00 |
| **[srctrunkname]** | String | The name of the source trunk | Sps129 |
| **[dstrunkname]** | String | The name of the destination trunk | Sps128 |
| **[status]** | String | Call status | ANSWERED |
| **[type]** | String | The call type | Inbound, Outbound, Internal, |
| **[pincode]** | Int | The password | 122 |
| **[recording]** | String | The name of the global recording file | hello001 |

### Acquire Global Recording files {#acquire-global-recording-files}

Through this interface, global recording files of a IPPBX can be acquired.

The acquisition method is as follows:

Step1: fetch the name of the global recording file through the “recording” parameter in the CDR event Step 2: get a random string consisting of numbers and characters, which is created by the system, by sending a request with the file name (as the request example below) to IPPBX

Step 3: combine the randon string with other elements to form a specific download request address

**Request method:** POST (HTTPS)

**Request address:**

https://192.168.5.150:8088/api/v1.0.1/recording/get_random?token=3efd4cd64e0d06e84a98230601428106

**Request sample:**

{&quot;recording&quot;:&quot;20170901181806-1504261084.7-1001-1003-Internal.wav&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;recording&gt;** | String | The name of the global recording file | hello001 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;recording&quot;:&quot;20170901181806-1504261084.7-1001-1003-Internal.wav&quot;,&quot;random&quot;:&quot;120732c546381fb020f17fba676b0ea0&quot;}

**Response parameters:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;Status&gt;** | String | Result | Success or Failed |
| **&lt;recording&gt;** | String | The name of the global recording file | Hello001 |
| **&lt;random&gt;** | String | A random string created for global recording file download. It serves as a component of a specified request address for download. |  |

**Download request address sample ( random string combination method):**

https://192.168.5.150:8088/api/v1.0.1/recording/download?recording=20170724103619-1500860177.268-2000-2001-Internal.wav&amp;random=7e60c59d187783f06ccc03621c4ad736&amp;token=75c5891b32203d0615f9e3753a7cb779

### Prompt Play End {#prompt-play-end}

This is used to report the event when the prompt played to the extension and the external number ends.

**Report sample:**

{&quot;action&quot;:&quot;PlayPromptEnd&quot;,&quot;callid&quot;:&quot;1495780325.384&quot;,&quot;ext&quot;:{&quot;extid&quot;:&quot;1002&quot;},&quot;prompt&quot;:&quot;111&quot;}

### Customer Satisfaction Survey Result Sending {#customer-satisfaction-survey-result-sending}

Once the DTMF data is collected from callers, API will send the customer satisfaction survey result to the client automatically.

**Report sample:**

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;surveyresult&gt;** | String | The result of the customer satisfaction survey. ( the DTMF data collected from the caller) | 1 |
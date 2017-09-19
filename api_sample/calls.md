## Calls {#calls}

### Query Inbound Calls {#query-inbound-calls}

Through this interface, developers could fetch detailed information like caller, callee, call status, etc. of all inbound calls coming from the trunks of the PBX.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/inbound/query?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;inboundid&quot;: &quot;1495698433.203&quot;}

**Request parameters descriptions:**

1.  Sending no parameter means query all information.
2.  With parameters, developers could query one or more outbound calls. Separate them with &quot;,&quot;.

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | Query all inbound calls | N/A |

**Response parameters:**

{&quot;status&quot;:&quot;Success&quot;,&quot;inbound&quot;:[{&quot;inboundid&quot;:&quot;1495698433.203&quot;,&quot;from&quot;:&quot;1000&quot;,&quot;to&quot;:&quot;1002&quot;,&quot;trunk&quot;:&quot;SIP-142&quot;,&quot;status&quot;:&quot;Talking&quot;,&quot;callee&quot;:[{&quot;extid&quot;:&quot;1002&quot;}]}]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **[inbound]** | object | Inbound calls: calls from external numbers through the trunks | N/A |
| **&lt;inboundid&gt;** | int | The inbound ID. With this parameter, operations like forwarding, query, and hangup can be performed on this inbound call. | 1 |
| **&lt;from&gt;** | String | The caller&#039;s number | 1000 |
| **&lt;to&gt;** | String | The callee&#039;s number | 5003 |
| **[callee]** | object | The called party of an inbound call, could be an extension, IVR, or an outbound ID. | 1005 |
| **&lt;trunk&gt;** | String | The name of the trunk that passes the inbound call | SIP |
| **[status]** | String | Call status | Talking: talking on the call |

**Possible error code:** 30001

### Query Outbound Calls {#query-outbound-calls}

Through this interface, developers could fetch detailed information like caller, callee, call status, etc. of all calls dialing out via the trunks of the PBX.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/outbound/query?token=6cad9cee6e2ad94570636e7b3690aeb2

**Request sample:**

{&quot;outboundid&quot;: &quot;1495705009.316&quot;}

**Request parameters descriptions:**

1.  Sending no parameter means query all information.
2.  With parameters in request, developers could query one or more outbound calls. Separate them with &quot;,&quot;.

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | Query all outbound calls | N/A |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;outbound&quot;:[{&quot;outboundid&quot;:&quot;1495705009.316&quot;,&quot;from&quot;:&quot;1002&quot;,&quot;to&quot;:&quot;41000&quot;,&quot;trunk&quot;:&quot;SIP-142&quot;,&quot;status&quot;:&quot;Talking&quot;}]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **[outbound]** | object | Outbound calls: calls to external numbers | N/A |
| **&lt;outboundid&gt;** | int | The outbound ID. With this parameter, operations like forwarding, query, and hangup can be performed on the outbound call. | 1495705009.316 |
| **&lt;from&gt;** | String | caller ID | 1000 |
| **&lt;to&gt;** | String | callee ID | 5003 |
| **&lt;trunk&gt;** |  | The name of the trunk that passes the outbound call | Sip-142 |
| **[status]** | String | Call status | Talking: talking on the call |

**Possible error code:** 30001

### Hang up an Extension Call {#hang-up-an-extension-call}

Through this interface, the ongoing internal call of the specified extension can be terminated, and the operation result will be returned.

**Request method:** POST

**Request address:** https://192.168.5.150:8088/api/v1.0.0/extension/hangup?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Hang up the ongoing call of the specified extension | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10007, 10004, 30001

### Hang up an Inbound Call {#hang-up-an-inbound-call}

Through this interface, the specified inbound call can be terminated.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/inbound/hangup?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;inboundid&quot;: &quot;1495698510.206&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | Hang up the specified inbound call | 1495698510.206 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10007, 10004, 30001

### Hang up an Outbound Call {#hang-up-an-outbound-call}

Through this interface, the specified outbound call can be terminated.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/outbound/hangup?token=6cad9cee6e2ad94570636e7b3690aeb2

**Request sample:**

{&quot;outboundid&quot;: &quot;1495705264.322&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | Hang up the specified outbound call | 1495705264.322 |

**Response parameters descriptions:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10007, 10004, 30001

### Hold a Call {#hold-a-call}

Through this interface, the call of the specified extension can be put on hold. When put on hold, the extension can initiate a new call through API.

Use the &quot;Resume Call on Hold&quot; interface to resume the call. The call can also be resumed if the extension finishes the new call.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/hold?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Put the extension&#039;s call on hold | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001

### Resume Call on Hold {#resume-call-on-hold}

Through this interface, an on-hold call will be resumed.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/unhold?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Resume call on hold | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001

### Mute an Extension {#mute-an-extension}

Through this interface, the specified extension in a call can be muted. As a result, the other party in the call can&#039;t hear the specified extension talking, but the extension can still hear the other party. Use &quot;Unmute an Extension&quot; interface to cancel the mute. When the call finishes, the extension will also be unmuted.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/mute?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Mute an extension | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001

### Unmute an Extension {#unmute-an-extension}

Through this interface, the extension will be unmuted.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/unmute?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Unmute an extension | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001

### Listen Monitor {#listen-monitor}

Through this interface, an extension can monitor another extension&#039;s call in Listen mode.

**Operations**

1.  Extension A is idle, extension B is in a call (query extension list to get the extension status);
2.  Make extension A monitor extension B&#039;s call in Listen mode;
3.  If the operation is successful, extension A will auto answer and start monitoring the extension B&#039;s conversation.

**Conditions**

1.  The monitor extension&#039;s monitor mode should be Extensive or Listen;
2.  The monitored extension should allow being monitored; and it can only be monitored by one extension at the same time;
3.  The call monitor only happens to extensions registered on the same PBX.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/listen?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;listener&quot;: &quot;1005&quot;,&quot;listenedext&quot;: &quot;1002&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;listener&gt;** | String | The monitor | 1005 |
| **&lt;listenedext&gt;** | String | The monitored extension | 1002 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 10010, 10008, 10006, 10009, 30001

### Whisper Monitor {#whisper-monitor}

Through this interface, an extension can monitor another extension&#039;s call in Whisper mode. As a result, the monitor and the monitored extension can talk to each other, but the other party in the call can talk to the monitor.

**Operations**

1. Extension A is idle, extension B is in a call (query extension list to get the extension status);

2. Make extension A monitor extension B&#039;s call in Whisper mode;

3. If the operation is successful, extension A will auto answer and start monitoring the extension B&#039;s conversation.

**Conditions**

1\. The monitor extension&#039;s monitor mode should be Extensive or Whisper;

2\. The monitored extension should allow being monitored;

3\. The call monitor only happens to extensions registered on the same PBX.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/whisper?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;whisperer&quot;: &quot;1005&quot;,&quot;whisperedext&quot;: &quot;1002&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;whisperer&gt;** | String | The monitor | 1005 |
| **&lt;whisperedext&gt;** | String | The monitored extension | 1002 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 10010, 10008, 10006, 10009, 30001

### Barge-in Monitor {#barge-in-monitor}

Through this interface, an extension can barge in another extension&#039;s call. As a result, all the three parties can talk to each other.

**Operations**

1.  1. Extension A is idle, extension B is in a call (query extension list to get the extension status);
2.  Make extension A barge in extension B&#039;s call;
3.  If the operation is successful, extension A will auto answer and barge in the extension B&#039;s conversation.

**Conditions**

1.  The monitor extension&#039;s monitor mode should be Extensive or Barge-in;
2.  The monitored extension should allow being monitored;
3.  The call monitor only happens to extensions registered on the same PBX.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/barge?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;bargein&quot;: &quot;1005&quot;,&quot;bargedext&quot;: &quot;1002&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;bargein&gt;** | String | The monitor | 1000 |
| **&lt;bargedext&gt;** | String | The monitored extension | 1002 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 10010, 10008, 10006, 10009, 30001

### Make an Internal Call {#make-an-internal-call}

Through this interface, an extension could call another extension and establish the call.

Send the request to make extension A dial extension B. Extension A will ring first, extension B will ring after extension A picks up the call. If “autoanswer” is set to “yes”, extension A (the calling party) will hear the ring back tone, extension B (the called party) will hear the ringing.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/dial_extension?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;caller&quot;: &quot;1000&quot;,&quot;callee&quot;: &quot;1002&quot;,&quot;autoanswer&quot;:&quot;no&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;caller&gt;** | String | The caller extension | 1000 |
| **&lt;callee&gt;** | String | The callee extension | 1002 |
| **[autoanswer]** | String | Whether to auto answer the call or not. This parameter requires the SIP phone to support. It means &quot;no&quot; if the parameter has not been specified. | yes/no |

**Response sample:**

{&quot;status&quot;:&quot;Failed&quot;,&quot;errno&quot;:&quot;10003&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10006, 30001

### Make an Extension Dial an External Number {#make-an-extension-dial-an-external-number}

Through this interface, an extension could dial an external number through the PBX&#039;s trunk and establish the call. (This interface is only for dialing external numbers.)

**Conditions**

1.  The call will go through an outbound route, so the extension needs to have permission of dialing through that route.
2.  Send the request to make an extension dial an external number. The extension will ring first, pick up the call on the extension and the external number will be dialed. If “autoanswer” is set to “yes”, the calling party will hear the ring back tone, the called party will hear the ringing.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/dial_outbound?token=285f99b2221c6b8c12d52eba3a88a5f7

**Request sample:**

{&quot;extid&quot;: &quot;1002&quot;,&quot;outto&quot;: &quot;41000&quot;,&quot;autoanswer&quot;:&quot;no&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1002 |
| **&lt;outto&gt;** | String | The external number | 41000 |
| **[autoanswer]** | String | Whether to auto answer the call or not. This parameter only applies the SIP phone to support. It means &quot;no&quot; if the parameter has not been specified. | Yes/No |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495710387.333&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495710387.333 |

**Possible error code:** 10004, 10006, 100024, 30001

### Transfer an Inbound Call to an Extension {#transfer-an-inbound-call-to-an-extension}

Through this interface, an inbound call from the PBX&#039;s trunk can be transferred to an extension.

Note: the call can be transferred whether it&#039;s a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_extension?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;inboundid&quot;: &quot;1495698591.209&quot;,&quot;extid&quot;: &quot;1003&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | The inbound ID | 1495698591.209 |
| **&lt;extid&gt;** | String | The extension number | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495698591.209&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495698591.209 |

**Possible error code:** 10004, 10006, 30001

### Transfer an Inbound call to an IVR {#transfer-an-inbound-call-to-an-ivr}

Through this interface, an inbound call from the PBX&#039;s trunk can be transferred to an IVR.

Note: the call can be transferred whether it&#039;s a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_ivr?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;inboundid&quot;: &quot;1495698591.209&quot;,&quot;ivrid&quot;: &quot;6500&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | int | The inbound ID | 1495698591.209 |
| **&lt;ivrid&gt;** | int | The IVR number | 6500 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495698591.209&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495698591.209 |

**Possible error code:** 10004, 10006, 10012, 30001

### Transfer an Inbound Call to a Trunk {#transfer-an-inbound-call-to-a-trunk}

Through this interface, an inbound call from the PBX&#039;s trunk can be transferred to another trunk. As a result, the two external numbers can establish calls with the PBX as the transit stop.

At least one trunk should be available at the time of transfer. And the outbound route&#039;s dial pattern should be matched.

Note: the call can be transferred whether it&#039;s a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_outbound?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;inboundid&quot;: &quot;1495698843.215&quot;,&quot;outto&quot;: &quot;22003&quot;,&quot;fromext&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | The inbound ID | 1495698843.215 |
| **&lt;outto&gt;** | String | Transfer to this trunk number | 22003 |
| **&lt;fromext&gt;** | String | Which extension&#039;s call permission will be applied | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495698843.215&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495698843.215 |

**Possible error code:** 10004, 10006, 10007, 30001

### Transfer an Outbound Call to an Extension {#transfer-an-outbound-call-to-an-extension}

Through this interface, an outbound call dialed out through the PBX&#039;s trunk can be transferred to an extension.

Note: the call can be transferred whether it&#039;s a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_extension?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;outboundid&quot;: &quot;1495700976.276&quot;,&quot;extid&quot;: &quot;1003&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | The outbound ID | 1495700976.276 |
| **&lt;extid&gt;** | Int | The extension number | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495700976.275&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700976.275 |

**Possible error code:** 10004, 10006, 10007, 30001

### Transfer an Outbound Call to a Trunk {#transfer-an-outbound-call-to-a-trunk}

Through this interface, an outbound call dialed out through the PBX&#039;s trunk can be transferred to another trunk. As a result, the two numbers can establish calls with the PBX as the transit stop.

At least one trunk should be available at the time of transfer. And the outbound route&#039;s dial pattern should be matched.

Note: the call can be transferred whether it&#039;s a ringing call or an ongoing call.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_outbound?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;outboundid&quot;: &quot;1495701184.282&quot;,&quot;outto&quot;: &quot;22003&quot;,&quot;fromext&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | The outbound ID | 1495700976.275 |
| **&lt;outto&gt;** | String | The external number to dial | 22003 |
| **&lt;fromext&gt;** | String | Which extension&#039;s call permission will be applied | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495701183.281&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495701183.281 |

**Possible error code:** 10004, 10006, 10007, 30001

### Transfer an Outbound Call to an IVR {#transfer-an-outbound-call-to-an-ivr}

Through this interface, an outbound call can be transferred to an IVR in order to:

1\. Play audio to the called party of the outbound call

2\. Send the keypress report to the application server when the called party&#039;s keypress triggers the relevant event.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/outbound/transfer_ivr?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;outboundid&quot;: &quot;1495700976.276&quot;,&quot;ivrid&quot;: &quot;6500&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outboundid&gt;** | String | The outbound ID | 1495700976.276 |
| **&lt;ivrid&gt;** | Int | The IVR number | 6500 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495700976.275&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700976.275 |

**Possible error code:** 10004, 10007, 10012, 30001

### Dial an Extension in an IVR {#dial-an-extension-in-an-ivr}

Through this interface, an extension can be dialed while in an IVR in order to:

1\. Play audio to the extension;

2\. Send the keypress report to the application server when the extension&#039;s keypress triggers the relevant event.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/ivr/dial_extension?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;ivrid&quot;: &quot;6500&quot;,&quot;extid&quot;: &quot;1002&quot;,&quot;autoanswer&quot;:&quot;no&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | String | The IVR number | 6000 |
| **&lt;extid&gt;** | String | The extension number | 2000 |
| **&lt;autoanswer&gt;** | String | Whether the extension will auto answer the call or not. This parameter requires the SIP phone to support. It means &quot;no&quot; if the parameter has not been specified. | Yes/No |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495700350.261&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700350.261 |

**Possible error code:** 10004, 10006, 10012, 30001

### Dial an External Number in an IVR {#dial-an-external-number-in-an-ivr}

Through this interface, an external number will be dialed while in an IVR in order to:

1\. Play audio to the dialed party when the call is established;

2\. Send the keypress report to the application server when the dialed party&#039;s keypress triggers the relevant event.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/ivr/dial_outbound?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;ivrid&quot;: &quot;6500&quot;,&quot;outto&quot;: &quot;41000&quot;,&quot;fromext&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | String | The IVR number | 6500 |
| **&lt;outto&gt;** | String | The dialed external number (the outbound dial pattern should be matched) | 41000 |
| **&lt;fromext&gt;** | String | Which extension&#039;s call permission will be applied | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495700406.266&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700406.266 |

### Dial an External Number in a Queue {#dial-an-external-number-in-a-queue}

Through this interface, an outbound call made with an external number being dialed out through S-Series IPPBX’s trunk can be transferred to a queue as an inbound call after it is established. Once the call is transferred, extensions in the queue will ring according to the ring strategy.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.1/queue/dial_outbound?token=25e9c77a705e6da650082dc1409fb68e

**Request sample:**

{ &quot;queueid&quot;: &quot;6700&quot;,&quot;outto&quot;: &quot;118396210850&quot;,&quot;fromext&quot;: &quot;1000000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt; queueid&gt;** | String | The queue number | 6200 |
| **&lt;outto&gt;** | String | The external number | 18045924562 |
| **&lt;fromext&gt;** | String | Which extension&#039;s call permission will be applied | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1501126620.23&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call |  |

### Dial an External Number in a Ring Group {#dial-an-external-number-in-a-ring-group}

Through this interface, an outbound call made with an external number being dialed out through S-Series IPPBX’s trunk can be transferred to a ring group as an inbound call after it is established. Once the call is transferred, extensions in the ring group will ring according to the ring strategy.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.1/ringgroup/dial_outbound?token=172970ee3f5f92fe65cd6bc17663b1f7

**Request sample:**

{ &quot;ringgroupid&quot;: &quot;6200&quot;,&quot;outto&quot;: &quot;118396210850&quot;,&quot;fromext&quot;: &quot;1000000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt; ringgroupid&gt;** | String | The ring group number | 6400 |
| **&lt;outto&gt;** | String | The external number | 18045924562 |
| **&lt;fromext&gt;** | String | Which extension&#039;s call permission will be applied | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1501145750.391&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call |  |

### Call Back {#call-back}

Through this interface, the PBX will dial two external numbers consecutively, and the two numbers could be connected with the PBX as the transit stop.

**Operations**

Dial the calling party&#039;s number first. The call is answered. Then dial the called party&#039;s number. The call is answered. The two parties are therefore connected.

Conditions

1\. The calls will rely on an extension&#039;s outbound call permission.

2\. There are at least two available trunks.

3\. The two calls need to match the outbound route.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/outbound/dial_outbound?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;caller&quot;: &quot;1002&quot;,&quot;outto&quot;: &quot;41000&quot;,&quot;fromext&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;caller&gt;** | String | The number of the calling party (the outbound dial pattern should be matched), which will be dialed first | 1002 |
| **&lt;outto&gt;** | String | The number of the called party (the outbound dial pattern should be matched), which will be dialed secondly | 41000 |
| **&lt;fromext&gt;** | String | Which extension&#039;s call permission will be applied | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495701633.295&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495701633.295 |

**Possible error code:** 10004, 10006, 10012, 30001

### Transfer an Inbound Call to a Queue {#transfer-an-inbound-call-to-a-queue}

Through this interface, an inbound call from an external number can be transferred to a queue. When the queue has idle extensions, the call will be handled accordingly. As a result:

1\. If there are idle extensions in the queue, the call will be passed according to the ring strategy.

2\. If all extensions are busy, the call will wait in the queue and hear the MOH. The first call in the queue will be answered first when the queue is idle.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_queue?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;inboundid&quot;: &quot;1495700191.223&quot;,&quot;queueid&quot;: &quot;6700&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | int | The inbound ID | 1495700191.223 |
| **&lt;queueid&gt;** | String | The queue number | 6700 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495700191.223&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700191.223 |

**Possible error code:** 10004, 10013, 30001

### Transfer an Inbound Call to a Ring Group {#transfer-an-inbound-call-to-a-ring-group}

Through this interface, an inbound call can be transferred to a ring group. As a result, the call will be handled according to the ring strategy when there are one or more available extensions in the group.

When Busy/No Answer

1\. If no extension is available (busy, DND), following the ring group&#039;s settings, the call will wait until an available extension picks up.

2\. If there are idle extensions, but the idle extension does not answer the call, the call will be directed to the next idle extension.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/inbound/transfer_ringgroup?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;inboundid&quot;: &quot;1495700191.223&quot;,&quot;ringgroupid&quot;: &quot;6200&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | int | The inbound ID | 1495700191.223 |
| **&lt;ringgroupid&gt;** | int | The ring group number | 6200 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495700191.223”}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700191.223 |

**Possible error code:** 10004, 10006, 10014, 30001

### Send Text Messages through a GSM Trunk {#send-text-messages-through-a-gsm-trunk}

Through this interface, text messages can be sent to an external number through a GSM trunk.

Scenario: When you phone to your carrier to apply for a calling plan, you hear an IVR and press a specific key on your phone as instructed to request detailed information. As a result, a text message is sent to your phone shortly after it is required.

Note: A text message have a maximum length of 2000 characters and no emoji should be included.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.1/sms/send?token=42af22de1f4b884950310d132232b4b5

**Request sample:**

{&quot;trunk&quot;:&quot;GSM-trunk&quot;,&quot;phonenumber&quot;:&quot;18396210850&quot;,&quot;message&quot;:&quot;%E4%BD%A0%E5%A5%BD &quot;}

**Note: messages sent must be URL encoded.**

**An online coding tool for your reference: http://tool.oschina.net/encode?type=4**

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;phonenumber&gt;** | String | Phone number | 1804630**** |
| **&lt;message&gt;** | String | Encoded message content | %E4%BD%A0%E5%A5%BD |
| **&lt;trunk&gt;** | String | The name of the GSM trunk through which messages are sent | GSM-trunk |

**Response sample:**

Signal Correctly Sent: {&quot;status&quot;:&quot;Success&quot;,&quot;smsid&quot;:&quot;18396210850-1502874159&quot;}

Message Successfully Sent: {&quot;status&quot;:&quot;Success&quot;,&quot;smsid&quot;:&quot;18396210850-1502874159&quot;}

Message Sending Failed:

{&quot;action&quot;:&quot;sms-send&quot;,&quot;status&quot;:&quot;Failed&quot;,&quot;smsid&quot;:&quot;18396210850-1502874159&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10027

### Control Inbound Calls {#control-inbound-calls}

If the trunk&#039;s API has Inbound Call Answering Control enabled, then whenever there&#039;s a call to this trunk, the PBX will send the API report message of this event—the invite event—to the application server. The application server will have a set period of time (10 seconds by default) to control the inbound call. **The application server can perform the following operations:**

*   **accept:** if the application server wants the PBX to continue handle the call, then invocate the Accept API, and the call will be handled by the PBX accordingly;
*   **refuse:** if the application server wants the PBX to refuse the call (e.g. because the number is blacklisted), then invocate the Refuse API, and the PBX will hang up the call directly.
*   **When times out**

If the application server does not call any of the above two APIs in the set period of time, by default, the call will be accepted by the PBX and go to the relevant destination.

**Request method:** POST

**Request address:**

1.  **Accept:**

https://192.168.5.150:8088/api/v1.0.0/inbound/accept?token=15bc7e4a0934023e79a557e15ff1f69e

1.  **Refuse:**

https://192.168.5.150:8088 /api/v1.0.0/inbound/refuse?token=15bc7e4a0934023e79a557e15ff1f69e

**Request sample:**

{&quot;inboundid&quot;: &quot;1495703883.314&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | int | Accept the call with the specific inbound ID | 1495703883.314 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;accept&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001
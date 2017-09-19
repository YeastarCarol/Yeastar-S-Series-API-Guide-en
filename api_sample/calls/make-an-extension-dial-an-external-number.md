### Make an Extension Dial an External Number {#make-an-extension-dial-an-external-number}

Through this interface, an extension could dial an external number through the PBX's trunk and establish the call. \(This interface is only for dialing external numbers.\)

**Conditions**

1. The call will go through an outbound route, so the extension needs to have permission of dialing through that route.
2. Send the request to make an extension dial an external number. The extension will ring first, pick up the call on the extension and the external number will be dialed. If “autoanswer” is set to “yes”, the calling party will hear the ring back tone, the called party will hear the ringing.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/extension/dial_outbound?token=285f99b2221c6b8c12d52eba3a88a5f7){version}[/extension/dial\_outbound?token=285f99b2221c6b8c12d52eba3a88a5f7](https://192.168.5.150:8088/api/v1.0.0/extension/dial_outbound?token=285f99b2221c6b8c12d52eba3a88a5f7)

**Request sample:**

{"extid": "1002","outto": "41000","autoanswer":"no"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | Int | The extension number | 1002 |
| **&lt;outto&gt;** | String | The external number | 41000 |
| **\[autoanswer\]** | String | Whether to auto answer the call or not. This parameter only applies the SIP phone to support. It means "no" if the parameter has not been specified. | Yes/No |

**Response sample:**

{"status":"Success","callid":"1495710387.333"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495710387.333 |

**Possible error code:** 10004, 10006, 100024, 30001

###  {#transfer-an-inbound-call-to-an-extension}




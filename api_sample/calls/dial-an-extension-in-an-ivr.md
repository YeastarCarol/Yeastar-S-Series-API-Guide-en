### Dial an Extension in an IVR\(新增note\) {#dial-an-extension-in-an-ivr}

Through this interface, an extension can be dialed while in an IVR in order to:

1. Play audio to the extension;

2. Send the keypress report to the application server when the extension's keypress triggers the relevant event.

Note: need to dial from an extension with route permission and the outbound dial pattern should be matched.\(新增\)

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/ivr/dial_extension?token=7d20390952e15eb72b0a1df7172de65c){version}[/ivr/dial\_extension?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/ivr/dial_extension?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"ivrid": "6500","extid": "1002","autoanswer":"no"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | Int | The IVR number | 6500 |
| **&lt;extid&gt;** | String | The extension number | 1002 |
| **&lt;autoanswer&gt;** | String | Whether the extension will auto answer the call or not. This parameter requires the SIP phone to support. It means "no" if the parameter has not been specified. | Yes/No |

**Response sample:**

{"status":"Success","callid":"1495700350.261"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;callid&gt;** | String | A unique identifier for the call | 1495700350.261 |

**Possible error code:** 10004, 10006, 10012, 30001

###  {#dial-an-external-number-in-an-ivr}




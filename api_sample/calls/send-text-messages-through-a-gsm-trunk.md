### Send Text Messages through a GSM Trunk {#send-text-messages-through-a-gsm-trunk}

Through this interface, text messages can be sent to an external number through a GSM trunk.

Scenario: When you phone to your carrier to apply for a calling plan, you hear an IVR and press a specific key on your phone as instructed to request detailed information. As a result, a text message is sent to your phone shortly after it is required.

Note: A text message have a maximum length of 2000 characters and no emoji should be included.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.1/sms/send?token=42af22de1f4b884950310d132232b4b5){version}[/sms/send?token=42af22de1f4b884950310d132232b4b5](https://192.168.5.150:8088/api/v1.0.1/sms/send?token=42af22de1f4b884950310d132232b4b5)

**Request sample:**

{"trunk":"GSM-trunk","phonenumber":"18396210850","message":"%E4%BD%A0%E5%A5%BD "}

**Note: messages sent must be URL encoded.**

**An online coding tool for your reference: **[**https://www.urlencoder.org**](http://www.urlencoder.org)

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;phonenumber&gt;** | String | Phone number | 1804630_\*\*_ |
| **&lt;message&gt;** | String | Encoded message content | %E4%BD%A0%E5%A5%BD |
| **&lt;trunk&gt;** | String | The name of the GSM trunk through which messages are sent | GSM-trunk |

**Response sample:**

Signal Correctly Sent: {"status":"Success","smsid":"18396210850-1502874159"}

Message Successfully Sent: {"status":"Success","smsid":"18396210850-1502874445"}

Message Sending Failed:

{"action":"sms-send","status":"Failed","smsid":"18396210850-1502874159"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | Object | Result | sms-send |
| **&lt;status&gt;** | String | Result | Success or Failed |
| **&lt;smsid&gt;** | String | A unique identifier of the message | 18396210850-1502874159 |

**Possible error code:** 10027

###  {#control-inbound-calls}




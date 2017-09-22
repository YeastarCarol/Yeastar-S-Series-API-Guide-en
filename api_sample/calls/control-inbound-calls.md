# Control Inbound Calls

If the trunk's API has Inbound Call Answering Control enabled, then whenever there's a call to this trunk, the PBX will send the API report message of this event—the invite event—to the application server. The application server will have a set period of time \(10 seconds by default and unchangable\) to control the inbound call.

**The application server can perform the following operations:**

* **accept:** if the application server wants the PBX to continue handle the call, then invocate the Accept API, and the call will be handled by the PBX accordingly;
* **refuse:** if the application server wants the PBX to refuse the call \(e.g. because the number is blacklisted\), then invocate the Refuse API, and the PBX will hang up the call directly.

**When times out**

If the application server does not call any of the above two APIs in the set period of time, by default, the call will be accepted by the PBX and go to the relevant destination.

#### **Accept:**

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](#){version}[/inbound/accept?token=15bc7e4a0934023e79a557e15ff1f69e](#)

**Request sample:**

{"inboundid": "1495703883.314"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | Accept the call with the specific inbound ID | 1495703883.314 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;accept&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001

#### **Refuse:**

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088](#)/api/{version}/inbound/refuse?token=15bc7e4a0934023e79a557e15ff1f69e

**Request sample:**

{"inboundid": "1495703883.314"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;inboundid&gt;** | String | Refuse  the call with the specific inbound ID | 1495703883.314 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;accept&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001


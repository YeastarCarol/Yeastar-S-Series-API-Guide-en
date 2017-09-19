### Hold a Call {#hold-a-call}

Through this interface, the call of the specified extension can be put on hold. When put on hold, the extension can initiate a new call through API.

Use the "Resume Call on Hold" interface to resume the call. The call can also be resumed if the extension finishes the new call.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/extension/hold?token=7d20390952e15eb72b0a1df7172de65c){version}[/extension/hold?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/hold?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | Int | Put the extension's call on hold | 1000 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001


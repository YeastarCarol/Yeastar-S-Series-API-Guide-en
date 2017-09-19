### Unmute an Extension {#unmute-an-extension}

Through this interface, the extension will be unmuted.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extension/unmute?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/unmute?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Unmute an extension | 1000 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001


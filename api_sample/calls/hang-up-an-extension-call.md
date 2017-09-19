### Hang up an Extension Call {#hang-up-an-extension-call}

Through this interface, the ongoing internal call of the specified extension can be terminated, and the operation result will be returned.

**Request method:** POST

**Request address:** [https://192.168.5.150:8088/api/v1.0.0/extension/hangup?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/hangup?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Hang up the ongoing call of the specified extension | 1000 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10007, 10004, 30001


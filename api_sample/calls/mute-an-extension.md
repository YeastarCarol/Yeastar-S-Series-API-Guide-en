### Mute an Extension {#resume-call-on-hold}

Through this interface, the specified extension in a call can be muted. As a result, the other party in the call can't hear the specified extension talking, but the extension can still hear the other party. Use "Unmute an Extension" interface to cancel the mute. When the call finishes, the extension will also be unmuted.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extension/mute?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/mute?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | Mute an extension | 1000 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 30001

###  {#unmute-an-extension}




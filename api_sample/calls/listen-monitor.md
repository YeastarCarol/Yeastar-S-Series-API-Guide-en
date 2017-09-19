### Listen Monitor {#listen-monitor}

Through this interface, an extension can monitor another extension's call in Listen mode.

**Operations**

1. Extension A is idle, extension B is in a call \(query extension list to get the extension status\);
2. Make extension A monitor extension B's call in Listen mode;
3. If the operation is successful, extension A will auto answer and start monitoring the extension B's conversation.

**Conditions**

1. The monitor extension's monitor mode should be Extensive or Listen;
2. The monitored extension should allow being monitored; and it can only be monitored by one extension at the same time;
3. The call monitor only happens to extensions registered on the same PBX.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extension/listen?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/listen?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"listener": "1005","listenedext": "1002"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;listener&gt;** | String | The monitor | 1005 |
| **&lt;listenedext&gt;** | String | The monitored extension | 1002 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 10010, 10008, 10006, 10009, 30001

###  {#whisper-monitor}




### Whisper Monitor {#whisper-monitor}

Through this interface, an extension can monitor another extension's call in Whisper mode. As a result, the monitor and the monitored extension can talk to each other, but the other party in the call can talk to the monitor.

**Operations**

1. Extension A is idle, extension B is in a call \(query extension list to get the extension status\);

2. Make extension A monitor extension B's call in Whisper mode;

3. If the operation is successful, extension A will auto answer and start monitoring the extension B's conversation.

注：有的话机或软电话可能不支持自动应答，则话机或软电话会先响铃，手动接听后开始监听。

Note: some IP phone modols and softphones do not support auto answer. In this case, IP phones or softphones will ring first, and users need to pick up the call manually to start monitoring.

**Conditions**

1. The monitor extension's monitor mode should be Extensive or Whisper;

2. The monitored extension should allow being monitored;

3. The call monitor only happens to extensions registered on the same PBX.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/extension/whisper?token=7d20390952e15eb72b0a1df7172de65c){version}[/extension/whisper?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/whisper?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"whisperer": "1005","whisperedext": "1002"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;whisperer&gt;** | Int | The monitor | 1005 |
| **&lt;whisperedext&gt;** | Int | The monitored extension | 1002 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10007, 10010, 10008, 10006, 10009, 30001

###  {#barge-in-monitor}




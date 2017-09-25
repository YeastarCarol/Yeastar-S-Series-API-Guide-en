### Configure an Individual Queue {#configure-an-individual-queue}

Through this interface, developers could configure an individual queue.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/queue/update?token=7d20390952e15eb72b0a1df7172de65c){version}[/queue/update?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/queue/update?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"queueid": "6701","queuenumber":"6701"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- |
| **&lt;queueid&gt;** | Int | The requested queue number | 6701 |
| **\[queuenumber\]** | Int | The modified queue number | 6701 |
| **\[queuename\]** | String |The queue name | : ! $ ( ) / # ; , [ ] " = < > & ' ` ^ % @ { } &#124;  are invalid. Neither is space character valid. Maximum length is 31. Cannot be blank. |
| **\[password\]** | String | The password to join dynamic agent | Digits. Maximum length is 127. |
| **\[ringstrategy\]** | String | The ring strategy | Options: Ring All, Least Recent, Fewest Calls, Random, RRmemory, Linear |
| **\[failoveraction\]** | String | The failover destination. | Options: Hangup, Extension, Voicemail, IVR, Ring Group, Queue, Conference, Fax to Email, Dial by name |
| **\[failoverdest\]** | String | The failover destination. | N/A |
| **\[agents\]** | String | Static agents | 1000, 1001 |
| **\[agenttimeout\]** | Int | The agent timeout | Options: 10, 20, 30, 40 50 |
| **\[wrapuptime\]** | Int | The wrap-up time | Options: 10, 20, 30, 40 50 |
| **\[ringinuse\]** | String | Ring the members whose device are known to be “in use” | on: enable <br> off: disable |
| **\[retry\]** | Int | The number of seconds to wait before trying all the phones again | Options: 10, 20, 30, 40 50 |
| **\[maxwaittime\]** | Int | The caller max wait time | Options: 300, 600, 900, 1200, 1800 |
| **\[joinempty\]** | String | Allow callers to join a queue that has no agents | on: enable <br> off: disable |
| **\[leavewhenempty\]** | String | Callers already on hold will be forced out of a queue when no agents are available. | on: enable <br> off: disable |
| **\[announcepos\]** | String | Announce position of caller in the queue. | on: enable <br> off: disable |
| **\[announcefreq\]** | String | How often to announce queue position and estimated hold time. | Options: 0, 15, 30, 45, 60, 120, 180, 240, 300, 600, 1200 |
| **\[announceholdtime\]** | Int | Announce the hold time to the caller periodically | on: enable <br> off: disable |
| **\[userannouncefreq\]** | Int | How often to play the periodic announcements. | Options: 0, 15, 30, 45, 60, 120, 180, 240, 300, 600, 1200 |
| **\[breakoutkey\]** | String | The breakout key | Options: None, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, \*, \# |
| **\[breakoutaction\]** | String | The breakout action | Options: Hang up, Extension, Voicemail, IVR, Ring Group, Queue, Conference, Fax to Email, Dial by Name |
| **\[breakoutdest\]** | String | The breakout destination |  |
| **\[idannouncement\]** | String | The file name of the prompt that announces the agent ID. It is "None" by default. Note: When querying one or more queues, this parameter is bound to return value\(s\). | None |
| **\[satisfactionsurvey\]** | String | The file name of the prompt for customer satisfaction survey. It is "None" by default. If it is not specified, the prompt will not be played. | None |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | IVR configuration result | Success or Failed |

**Possible error code:** 10013, 10019, 30001


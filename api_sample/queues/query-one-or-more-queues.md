# Query One or More Queues

Through this interface, developers could query detailed information like queue number, queue name, static agents, dynamic agents, etc. of one or more queues. When there are multiple queries, separate the parameters with comma.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/queue/query?token=6cad9cee6e2ad94570636e7b3690aeb2){version}[/queue/query?token=6cad9cee6e2ad94570636e7b3690aeb2](https://192.168.5.150:8088/api/v1.0.0/queue/query?token=6cad9cee6e2ad94570636e7b3690aeb2)

**Request sample:**

{"queueid": "6701"}

**Request parameters descriptions:**

1. Sending no parameter means query all information.
2. With parameters in request, developers could query specific information. Separate them with ",". For example: {"queueid": "6500,6501,6502"}.

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;queueid&gt;** | String | Query one or more queues | 6202 |

**Response sample:**

{"status":"Success","queues":\[{"queuenumber":"6701","password":"","queuename":"6701","ringstrategy":"Ring All","failoveraction":"Hang up","agents":"1001,1002,1003,1004,1005,1006,","agenttimeout":"30","agentannounce":"\[None\]","wrapuptime":"30","ringinuse":"on","retry":"30","musiconhold":"\[None\]","maxwaittime":"1800","joinempty":"off","leavewhenempty":"on","joinannounce":"\[None\]","announcepos":"on","announcefreq":"30","announceholdtime":"on","userannounce":"\[None\]","userannouncefreq":"30","breakoutkey":"None","satisfactionsurvey":"None","idannouncement":"None"}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **\[queues\]** | object | Queues | N/A |
| **&lt;queuenumber&gt;** | int | The queue number | 6701 |
| **&lt;queuename&gt;** | String | The queue name | Productteam |
| **&lt;password&gt;** | String | The password to join dynamic agent | 123456 |
| **&lt;ringstrategy&gt;** | String | The ring strategy | Options: Ring All, Least Recent, Fewest Calls, Random, RRmemory, Linear |
| **&lt;failoveraction&gt;** | String | The failover destination. | Hang up |
| **\[agents\]** | String | Static agents | 1000, 1001 |
| **&lt;agenttimeout&gt;** | String | The agent timeout | 30 |
| **&lt;agentannounce&gt;** | String | The agent announcement | \[None\] |
| **&lt;wrapuptime&gt;** | Int | The wrap-up time | 30 |
| **&lt;ringinuse&gt;** | String | Ring the members whose device are known to be “in use” | On: enable  Off: disable |
| **&lt;retry&gt;** | Int | The number of seconds to wait before trying all the phones again | 30 |
| **&lt;musiconhold&gt;** | String | The on-hold music | \[None\] |
| **&lt;maxwaittime&gt;** | Int | The caller max wait time | 30 |
| **&lt;joinempty&gt;** | String | Allow callers to join a queue that has no agents | On: enable  Off: disable |
| **&lt;leavewhenempty&gt;** | String | Callers already on hold will be forced out of a queue when no agents are available. | On: enable  Off: disable |
| **\[joinannounce\]** | String | Announcement played to callers prior to joining the queue. | \[None\] |
| **&lt;announcepos&gt;** | String | Announce position of caller in the queue. | On: enable  Off: disable |
| **&lt;announcefreq&gt;** | String | How often to announce queue position and estimated hold time. | 30 |
| **&lt;announceholdtime&gt;** | Int | Announce the hold time to the caller periodically | 30 |
| **&lt;userannounce&gt;** | String | An periodic announcement | \[None\] |
| **&lt;userannouncefreq&gt;** | Int | How often to play the periodic announcements. | 30 |
| **\[breakoutkey\]** | String | The breakout key | None |
| **\[breakoutaction\]** | String | The breakout action |  |
| **\[breakoutdest\]** | String | The breakout destination |  |
| **\[idannouncement\]** | String | The file name of the prompt that announces the agent ID. It is "None" by default. Note: When querying one or more queues, this parameter is bound to return value\(s\). | None |
| **\[satisfactionsurvey\]** | String | The file name of the prompt for customer satisfaction survey. It is "None" by default. If it is not specified, the prompt will not be played. | None |

**Possible error code:** 10013, 30001


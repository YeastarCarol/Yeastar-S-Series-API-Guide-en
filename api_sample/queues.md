## Queues {#queues}

### Query One or More Queues {#query-one-or-more-queues}

Through this interface, developers could fetch detailed information like queue number, queue name, static agents, dynamic agents, etc. of one or more queues. When there are multiple queries, separate the parameters with comma.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/queue/query?token=6cad9cee6e2ad94570636e7b3690aeb2

**Request sample:**

{&quot;queueid&quot;: &quot;6701&quot;}

**Request parameters descriptions:**

1.  Sending no parameter means query all information.
2.  With parameters in request, developers could query specific information. Separate them with &quot;,&quot;. For example: {&quot;ivrid&quot;: &quot;6500,6501,6502&quot;}.

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;queueid&gt;** | String | Query one or more queues | 6202 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;queues&quot;:[{&quot;queuenumber&quot;:&quot;6701&quot;,&quot;password&quot;:&quot;&quot;,&quot;queuename&quot;:&quot;6700&quot;,&quot;ringstrategy&quot;:&quot;Ring All&quot;,&quot;failoveraction&quot;:&quot;Hang up&quot;,&quot;agents&quot;:&quot;1000,1001,1002,1003,1004,1005,1006,&quot;,&quot;agenttimeout&quot;:&quot;30&quot;,&quot;agentannounce&quot;:&quot;[None]&quot;,&quot;wrapuptime&quot;:&quot;30&quot;,&quot;ringinuse&quot;:&quot;on&quot;,&quot;retry&quot;:&quot;30&quot;,&quot;musiconhold&quot;:&quot;[None]&quot;,&quot;maxwaittime&quot;:&quot;1800&quot;,&quot;joinempty&quot;:&quot;off&quot;,&quot;leavewhenempty&quot;:&quot;on&quot;,&quot;joinannounce&quot;:&quot;[None]&quot;,&quot;announcepos&quot;:&quot;on&quot;,&quot;announcefreq&quot;:&quot;30&quot;,&quot;announceholdtime&quot;:&quot;on&quot;,&quot;userannounce&quot;:&quot;[None]&quot;,&quot;userannouncefreq&quot;:&quot;30&quot;,&quot;breakoutkey&quot;:&quot;None&quot;}]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **[queues]** | object | Queues | N/A |
| **&lt;queuenumber&gt;** | int | The queue number | 6701 |
| **&lt;queuename&gt;** | String | The queue name | Productteam |
| **&lt;password&gt;** | String | The password to join dynamic agent | 123456 |
| **&lt;ringstrategy&gt;** | String | The ring strategy | Options: |
| **&lt;failoveraction&gt;** | String | The failover destination. | Hang up |
| **[agents]** | String | Static agents | 1000 |
| **&lt;agenttimeout&gt;** | String | The agent timeout | 30 |
| **&lt;agentannounce&gt;** | String | The agent announcement | [None] |
| **&lt;wrapuptime&gt;** | Int | The wrap-up time | 30 |
| **&lt;ringinuse&gt;** | String | Ring the members whose device are known to be “in use” | on |
| **&lt;retry&gt;** | Int | The number of seconds to wait before trying all the phones again | 30 |
| **&lt;musiconhold&gt;** | String | The on-hold music | [None] |
| **&lt;maxwaittime&gt;** | Int | The caller max wait time | 30 |
| **&lt;joinempty&gt;** | String | Allow callers to join a queue that has no agents | [None] |
| **&lt;leavewhenempty&gt;** | String | Callers already on hold will be forced out of a queue when no agents are available. | on |
| **[joinannounce]** | String | Announcement played to callers prior to joining the queue. | [None] |
| **&lt;announcepos&gt;** | String | Announce position of caller in the queue. | on |
| **&lt;announcefreq&gt;** | String | How often to announce queue position and estimated hold time. | 30 |
| **&lt;announceholdtime&gt;** | Int | Announce the hold time to the caller periodically | 30 |
| **&lt;userannounce&gt;** | String | An periodic announcement | [None] |
| **&lt;userannouncefreq&gt;** | Int | How often to play the periodic announcements. | 30 |
| **[breakoutkey]** | String | The breakout key | None |
| **[breakoutaction]** | String | The breakout action |  |
| **[breakoutdest]** | String | The breakout destination |  |

**Possible error code:** 10013, 30001

### Configure an Individual Queue {#configure-an-individual-queue}

Through this interface, developers could configure an individual queue.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/queue/update?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;queueid&quot;: &quot;6701&quot;,&quot;queuenumber&quot;:&quot;6701&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;queueid&gt;** | int | The requested queue number | 6200 |
| **[queuenumber]** | int | The modified queue number | 6200 |
| **[queuename]** | String | The queue name | :!$()\\/#;,\\\&quot;=&lt;&gt;&amp;&#039;`^%@{}|\\are invalid. Neither is space character valid. |
| **[password]** | String | The password to join dynamic agent | Digits. Maximum length is 127. |
| **[ringstrategy]** | String | The ring strategy | Options: |
| **[failoveraction]** | String | The failover destination. | Options: |
| **[failoverdest]** | String | The failover destination. |  |
| **[agents]** | String | Static agents | 1000 |
| **[agenttimeout]** | Int | The agent timeout | Options: 10, 20, 30, 40 50 |
| **[wrapuptime]** | Int | The wrap-up time | Options: 10, 20, 30, 40 50 |
| **[ringinuse]** | String | Ring the members whose device are known to be “in use” | On: enable |
| **[retry]** | Int | The number of seconds to wait before trying all the phones again | Options: 10, 20, 30, 40 50 |
| **[maxwaittime]** | Int | The caller max wait time | Options: 300, 600, 900, 1200, 1800 |
| **[joinempty]** | String | Allow callers to join a queue that has no agents | On: enable |
| **[leavewhenempty]** | String | Callers already on hold will be forced out of a queue when no agents are available. | On: enable |
| **[announcepos]** | String | Announce position of caller in the queue. | On: enable |
| **[announcefreq]** | String | How often to announce queue position and estimated hold time. | Options: 0, 15, 30, 45, 60, 120, 180, 240, 300, 600, 1200 |
| **[announceholdtime]** | Int | Announce the hold time to the caller periodically | On: enable |
| **[userannouncefreq]** | Int | How often to play the periodic announcements. | Options: 0, 15, 30, 45, 60, 120, 180, 240, 300, 600, 1200 |
| **[breakoutkey]** | String | The breakout key | Options: |
| **[breakoutaction]** | String | The breakout action | Options: Hang up, Extension, Voicemail, IVR, Ring Group, Queue, Conference, Fax to Email, Dial by Name |
| **[breakoutdest]** | String | The breakout destination |  |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | IVR configuration result | Success or Failed |

**Possible error code:** 10013, 10019, 30001
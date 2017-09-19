## Hotel Wake-up Service {#hotel-wake-up-service}

### Add an Alarm {#add-an-alarm}

Note: the same alarm can be added to multiple extensions; separate the extension number with comma.

For example:

{&quot;extid&quot;:&quot;1000,1001&quot;,&quot;wakeup&quot;:[{&quot;time&quot;:&quot;00:45&quot;,&quot;type&quot;:&quot;onetime&quot;,&quot;repeats&quot;:&quot;3&quot;,&quot;repeatinterval&quot;:&quot;5&quot;}]}

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/wakeupcall/create?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;:&quot;1000&quot;,&quot;wakeup&quot;:[{&quot;time&quot;:&quot;00:45&quot;,&quot;type&quot;:&quot;onetime&quot;,&quot;repeats&quot;:&quot;3&quot;,&quot;repeatinterval&quot;:&quot;5&quot;}]}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |
| **&lt;wakeup&gt;** | Object | Object |  |
| **&lt;time&gt;** | String | Time | 11:22 |
| **&lt;type&gt;** | String | Type | Options: |
| **[weekdays]** | String | The options available when the above &lt;type&gt; is &quot;custom&quot; | Options: 1, 2, 3, 4, 5, 6, 0 |
| **[repeats]** | String | How many times will the alarm be repeated | Options: |
| **[Repeatinterval]** | String | The interval in minutes between each repeat | 1 |
| **[Prompt]** | String | The prompt played | helloworld, the file name of the custom prompt. Without the parameter, the default prompt &quot;macroform-cold_day&quot; will be played. |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Possible error code:** 10006, 10020, 30001

### Query an Alarm {#query-an-alarm}

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/wakeupcall/query?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;wakeups&quot;:[{&quot;extid&quot;:&quot;1000&quot;,&quot;wakeup&quot;:[{&quot;time&quot;:&quot;00:45&quot;,&quot;type&quot;:&quot;onetime&quot;,&quot;prompt&quot;:&quot;macroform-cold_day&quot;,&quot;repeats&quot;:&quot;3&quot;,&quot;repeatinterval&quot;:&quot;5&quot;}]}]

**Please refer to the parameters descriptions of Add an Alarm.**

### Modify an Alarm {#modify-an-alarm}

Note: can only modify one extension&#039;s alarm at a time.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/wakeupcall/update?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;:&quot;1000&quot;,&quot;time&quot;:&quot;00:45&quot;,&quot;wakeup&quot;:[{&quot;time&quot;:&quot;11:00&quot;,&quot;type&quot;:&quot;onetime&quot;,&quot;repeats&quot;:&quot;3&quot;,&quot;repeatinterval&quot;:&quot;5&quot;}]}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |
| **[time]** | String | The original alarm time | 11:00 |
| **[wakeup]** | Object |  |  |
| **[time]** | String | Time | 11:22 |
| **[type]** | String | Type | Options: |
| **[weekdays]** | String | The options available when the above [type] is &quot;custom&quot; | Options: 1, 2, 3, 4, 5, 6, 0 |
| **[repeats]** | String | How many times will the alarm be repeated | Options: |
| **[repeatinterval]** | String | The interval in minutes between each repeat | 1 |
| **[prompt]** | String | The prompt played | helloworld, the file name of the custom prompt |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Possible error code:** 100021, 10020, 30001

### Delete an Alarm {#delete-an-alarm}

Note: can only operate on one extension&#039;s alarm at a time.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/wakeupcall/delete?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;,&quot;time&quot;:&quot;11:00&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |
| **[time]** | String | Delete the specific alarm if the time is specified. Delete all alarms if the parameter is not sent. | 11:00 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Possible error code:** 10021, 30001

### Play Music to an Extension {#play-music-to-an-extension}

Note: can only operate on one extension at a time.

**Request method:** POST (HTTPS)

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/extension/playprompt?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;extid&quot;: &quot;1000&quot;,&quot;prompt&quot;:&quot;111&quot;,&quot;autoanswer&quot;:&quot;no&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |
| **&lt;prompt&gt;** | String | The custom music | 111, the file name of the custom music |
| **[autoanswer]** | String | Whether the extension will auto answer or not. This parameter requires the SIP phone to support. It means &quot;no&quot; if the parameter has not been specified. | yes/no |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495697869.171&quot;}

**Possible error code:** 10004, 10023, 10015, 10006, 30001

### Play Music to an External Number {#play-music-to-an-external-number}

Note: can only operate on one extension at a time.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/outbound/playprompt?token=7d20390952e15eb72b0a1df7172de65c

**Request sample:**

{&quot;outto&quot;: &quot;41000&quot;,&quot;prompt&quot;:&quot;111&quot;,&quot;fromext&quot;:&quot;1000&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outto&gt;** | String | The external number | 41000 |
| **&lt;prompt&gt;** | String | The custom music | 111, the file name of the custom music |
| **[fromext]** | String | Which extension&#039;s call permission will be applied | 1000 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;callid&quot;:&quot;1495701728.300&quot;}

**Possible error code:** 10004, 10023, 10015, 10006, 30001

### Queue Agent ID Announcement and Customer Satisfaction Survey {#queue-agent-id-announcement-and-customer-satisfaction-survey}

Through this interface, developers can configure the agent ID to be announced in a greeting prompt, which is played when a call is established in a queue, and realize customer satisfaction survey with a custom prompt being played before it is hung up by the caller. To be more specific, when an inbound call reaches a queue and is picked up by an agent, the system will play a custom greeting to the caller announcing the ID of the agent answering the phone. And once the agent hangs up, another custom prompt for customer satisfaction survey will be played automatically to the caller. He may hear a prompt like this: “**_Thank you for your calling. If you are satisfied with this service, please press 1\. If not, please press 2\. You can hang up to end this call”. The system will collect the DFMF data when callers press the key. After it is done, the call will end with the ending prompt “Thank you for your calling”. (The ending prompt is a default system prompt and can not be changed. )_**

**_Precondition: All custom prompts needed should be uploaded to and be included in S-Series IPPBX custom prompt list._**

**Request address:**

https://192.168.5.150:8088 /api/v1.0.1/queue/update?token=42af22de1f4b884950310d132232b4b5 HTTP/1.1

**Request sample:**

{ &quot;queueid&quot;: &quot;6700&quot;,&quot;satisfactionsurvey&quot;:&quot;hello001&quot;,&quot;satisfactionsurvey&quot;:&quot;hello002&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **[idannouncement]** | String | The name of the prompt to be played. The prompt will not be played if not configured. The default name is [none]. | hello001 |
| **[agentid]** | String | The agent ID to be announced in the greeting prompt. This parameter is not required. If left null, the extension number will be announced instead. It is null by default. | 6932 |
| **[satisfactionsurvey]** | String | The name of the customer satisfaction survey prompt. The prompt will not be played if not configured. The default name is [none]. | hello002 |
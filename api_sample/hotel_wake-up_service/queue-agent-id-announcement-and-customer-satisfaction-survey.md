### Queue Agent ID Announcement and Customer Satisfaction Survey {#queue-agent-id-announcement-and-customer-satisfaction-survey}

Through this interface, developers can configure the agent ID to be announced in a greeting prompt, which is played when a call is established in a queue, and realize customer satisfaction survey with a custom prompt being played before it is hung up by the caller. To be more specific, when an inbound call reaches a queue and is picked up by an agent, the system will play a custom greeting to the caller announcing the ID of the agent answering the phone. And once the agent hangs up, another custom prompt for customer satisfaction survey will be played automatically to the caller. He may hear a prompt like this: “_**Thank you for your calling. If you are satisfied with this service, please press 1. If not, please press 2. You can hang up to end this call”. The system will collect the DFMF data when callers press the key. After it is done, the call will end with the ending prompt “Thank you for your calling”. \(The ending prompt is a default system prompt and can not be changed. \)**_

_**Precondition: All custom prompts needed should be uploaded to and be included in S-Series IPPBX custom prompt list.**_

**Request address:**

[https://192.168.5.150:8088](https://192.168.5.150:8088) /api/v1.0.1/queue/update?token=42af22de1f4b884950310d132232b4b5 HTTP/1.1

**Request sample:**

{ "queueid": "6700","satisfactionsurvey":"hello001","satisfactionsurvey":"hello002"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **\[idannouncement\]** | String | The name of the prompt to be played. The prompt will not be played if not configured. The default name is \[none\]. | hello001 |
| **\[agentid\]** | String | The agent ID to be announced in the greeting prompt. This parameter is not required. If left null, the extension number will be announced instead. It is null by default. | 6932 |
| **\[satisfactionsurvey\]** | String | The name of the customer satisfaction survey prompt. The prompt will not be played if not configured. The default name is \[none\]. | hello002 |




## Trunk {#trunk}

### Query Trunk List {#query-trunk-list}

Through this interface, developers could fetch basic information like trunk name, trunk status, trunk type, etc. of all trunks.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/trunklist/query?token=7d20390952e15eb72b0a1df7172de65c

**Request parameters descriptions:**

No parameter. Only need to send the request.

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;trunklist&quot;:[{&quot;trunkname&quot;:&quot;DIGIT1&quot;,&quot;status&quot;:&quot;Down&quot;,&quot;type&quot;:&quot;E1&quot;,&quot;port&quot;:&quot;Span1-Port1&quot;},{&quot;trunkname&quot;:&quot;FXO2-3&quot;,&quot;status&quot;:&quot;Idle&quot;,&quot;type&quot;:&quot;FXO&quot;,&quot;port&quot;:&quot;Span2-Port3&quot;},{&quot;trunkname&quot;:&quot;FXO2-4&quot;,&quot;status&quot;:&quot;Fault&quot;,&quot;type&quot;:&quot;FXO&quot;,&quot;port&quot;:&quot;Span2-Port4&quot;},{&quot;trunkname&quot;:&quot;BRI2-5&quot;,&quot;status&quot;:&quot;Fault&quot;,&quot;type&quot;:&quot;BRI&quot;,&quot;port&quot;:&quot;Span2-Port5&quot;},{&quot;trunkname&quot;:&quot;BRI2-6&quot;,&quot;status&quot;:&quot;Fault&quot;,&quot;type&quot;:&quot;BRI&quot;,&quot;port&quot;:&quot;Span2-Port6&quot;},{&quot;trunkname&quot;:&quot;GSM2-7&quot;,&quot;status&quot;:&quot;No SIM&quot;,&quot;type&quot;:&quot;GSM&quot;,&quot;port&quot;:&quot;Span2-Port7&quot;},{&quot;trunkname&quot;:&quot;SIP-142&quot;,&quot;status&quot;:&quot;Registered&quot;,&quot;type&quot;:&quot;SIP&quot;}]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;trunklist&gt;** | Object | Trunk object |
| **&lt;trunkname&gt;** | String | The trunk name | Sip trunk test |
| **&lt;status&gt;** | String | Current status of the trunk | Idle |
| **&lt;type&gt;** | String | The trunk type | SIP-Register, PSTN |
| **[port]** | String | The trunk port | Span1_Port3, 192.168.5.150 |

**Possible error code:** 30001

**Possible Status of All Types of Trunks**

| **FXO Trunk** | **BRI/E1/T1/J1** | **GSM/UMTS** | **SIP/IAX** |
| --- | --- | --- | --- |
| **1\. fault** | 1\. fault | 1\. power off | 1\. registering |
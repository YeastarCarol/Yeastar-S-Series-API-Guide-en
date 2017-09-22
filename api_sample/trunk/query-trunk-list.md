# Query Trunk List

Through this interface, developers could query basic information like trunk name, trunk status, trunk type, etc. of all trunks.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/trunklist/query?token=7d20390952e15eb72b0a1df7172de65c){version}[/trunklist/query?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/trunklist/query?token=7d20390952e15eb72b0a1df7172de65c)

**Request parameters descriptions:**

No parameter. Only need to send the request.

**Response sample:**

{"status":"Success","trunklist":\[{"trunkname":"DIGIT1","status":"Down","type":"E1","port":"Span1-Port1"},{"trunkname":"FXO2-3","status":"Idle","type":"FXO","port":"Span2-Port3"},{"trunkname":"FXO2-4","status":"Fault","type":"FXO","port":"Span2-Port4"},{"trunkname":"BRI2-5","status":"Fault","type":"BRI","port":"Span2-Port5"},{"trunkname":"BRI2-6","status":"Fault","type":"BRI","port":"Span2-Port6"},{"trunkname":"GSM2-7","status":"No SIM","type":"GSM","port":"Span2-Port7"},{"trunkname":"SIP-142","status":"Registered","type":"SIP"}\]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;trunklist&gt;** | Object | Object |  |
| **&lt;trunkname&gt;** | String | The trunk name | Sip trunk test |
| **&lt;status&gt;** | String | Current status of the trunk | Fault |
| **&lt;type&gt;** | String | The trunk type | SIP, FXO, GSM. BRI, E1 |
| **\[port\]** | String | The trunk port | Span1\_Port3 |

**Possible error code:** 30001

**Possible Status of All Types of Trunks**

| **FXO Trunk** | **BRI/E1/T1/J1** | **GSM/CDMA/UMTS** | **SIP/IAX** |
| :--- | :--- | :--- | :--- |
| 1. Fault <br> 2. Idle <br> 3. Busy | 1. Fault <br> 2. Alarm <br>                3. Down <br> 4. Up | 1. Power Off   <br>   2. Alarm <br> 3. No SIM <br> 4. No Signal <br>  5. Pin Error <br>  6. Unregister<br>   7. Busy <br> 8. Idle | 1. Registering <br> 2. Failure <br>  3. Registered \(Unmonitored\)                                           <br> 4. Disable  <br>   5. Unknown |




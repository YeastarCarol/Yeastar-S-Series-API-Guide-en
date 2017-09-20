# Customer Satisfaction Survey Result Sending\(表格内容有变\)

Once the DTMF pressed is collected from callers, API will send the customer satisfaction survey result to the client automatically.

**Report sample:**

{"action":"satisfaction","surveyresult":"1","callid":"1504460713.60"}

**Reportparameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| :--- | :--- | :--- | :--- |
| **&lt;action&gt;（新增）** | String | Customer satisfaction survey | satisfaction |
| **&lt;surveyresult&gt;** | String | The result of the customer satisfaction survey. \( the DTMF key pressed by the caller\) | 1 |
| **&lt;callid&gt;** | String | A unique identifier of the call | 1504460713.60 |




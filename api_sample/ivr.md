## IVR {#ivr}

### Query One or More IVRs {#query-one-or-more-ivrs}

Through this interface, developers could fetch detailed information like IVR number, IVR name, keypress events, response timeout, etc. of one or more IVRs.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/ivr/query?token=6cad9cee6e2ad94570636e7b3690aeb2

**Request sample:**

{&quot;ivrid&quot;: &quot;6500&quot;}

**Request parameters descriptions:**

1.  Sending no parameter means query all information.
2.  With parameters in request, developers could query specific information. Separate them with &quot;,&quot;. For example: {&quot;ivrid&quot;: &quot;6500,6501,6502&quot;}.

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | String | Query one or more IVRs | 6202 |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;ivr&quot;:[{&quot;ivrnumber&quot;:&quot;6500&quot;,&quot;ivrname&quot;:&quot;6500&quot;,&quot;prompt&quot;:&quot;[Default]&quot;,&quot;promptrepeat&quot;:&quot;3&quot;,&quot;responsetimeout&quot;:&quot;3&quot;,&quot;digittimeout&quot;:&quot;3&quot;,&quot;dialext&quot;:&quot;on&quot;,&quot;dialoutboundroutes&quot;:&quot;off&quot;,&quot;dialtocheckvoicemail&quot;:&quot;off&quot;}]}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrnumber&gt;** | String | The IVR number | 6500 |
| **&lt;ivrname&gt;** | String | The IVR name | 6202 |
| **[prompt]** | String | The IVR prompt | [Default] |
| **[promptrepeat]** | String | How many times will the prompt be repeated | 3 |
| **[responsetimeout]** | Int | Response timeout in seconds. | 3 |
| **[digittimeout]** | Int | Digit timeout in seconds. | 5 |
| **[dialext]** | String | Allow the caller to dial extension. | On: enable |
| **[dialoutboundroutes]** | String | Allow the caller to dial through outbound routes. | On: enable |
| **[selectedrouters]** | String | The route selected |  |
| **[dialtocheckvoicemail]** | String | Allow to check voicemail | On: enable |

**Possible error code:** 10012, 30001

### Configure an Individual IVR {#configure-an-individual-ivr}

Through this interface, developers could configure IVR number, IVR name, etc. of an IVR.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/ivr/update?token=6cad9cee6e2ad94570636e7b3690aeb2

**Request sample:**

{&quot;ivrid&quot;: &quot;6500&quot;,&quot;ivrnumber&quot;:&quot;6501&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ivrid&gt;** | String | A unique identifier of the configured IVR (IVR number) | 6202 |
| **&lt;ivrnumber&gt;** | String | Modified IVR number | 6204 |
| **&lt;ivrname&gt;** | String | The IVR name | E.g. 6202\. |
| **[promptrepeat]** | String | How many times will the prompt be repeated | A range from 1 to 5 |
| **[responsetimeout]** | Int | Response timeout in seconds. | A range from 1 to 10 |
| **[digittimeout]** | Int | Digit timeout in seconds. | A range from 1 to 10 |
| **[dialext]** | String | Allow the caller to dial extension. | On: enable |
| **[dialtocheckvoicemail]** | String | Allow to check voicemail | On: enable |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | IVR configuration result | Success or Failed |
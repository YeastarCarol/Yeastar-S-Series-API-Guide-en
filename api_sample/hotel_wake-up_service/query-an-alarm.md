### Query an Alarm {#query-an-alarm}

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/wakeupcall/query?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/wakeupcall/query?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |

**Response sample:**

{"status":"Success","wakeups":\[{"extid":"1000","wakeup":\[{"time":"00:45","type":"onetime","prompt":"macroform-cold\_day","repeats":"3","repeatinterval":"5"}\]}\]

**Please refer to the parameters descriptions of Add an Alarm.**

###  {#modify-an-alarm}




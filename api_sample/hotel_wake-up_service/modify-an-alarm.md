### Modify an Alarm {#modify-an-alarm}

Note: can only modify one extension's alarm at a time.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/wakeupcall/update?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/wakeupcall/update?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid":"1000","time":"00:45","wakeup":\[{"time":"11:00","type":"onetime","repeats":"3","repeatinterval":"5"}\]}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |
| **\[time\]** | String | The original alarm time | 11:00 |
| **\[wakeup\]** | Object |  |  |
| **\[time\]** | String | Time | 11:22 |
| **\[type\]** | String | Type | Options: |
| **\[weekdays\]** | String | The options available when the above \[type\] is "custom" | Options: 1, 2, 3, 4, 5, 6, 0 |
| **\[repeats\]** | String | How many times will the alarm be repeated | Options: |
| **\[repeatinterval\]** | String | The interval in minutes between each repeat | 1 |
| **\[prompt\]** | String | The prompt played | helloworld, the file name of the custom prompt |

**Response sample:**

{"status":"Success"}

**Possible error code:** 100021, 10020, 30001

###  {#delete-an-alarm}



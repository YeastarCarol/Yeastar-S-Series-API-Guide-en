### Delete an Alarm {#delete-an-alarm}

通过本接口可删除某个分机存在的闹铃。

Through this interface, developers could delete alarm\(s\) for specific extension.

Note: can only operate on one extension's alarm at a time.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/wakeupcall/delete?token=7d20390952e15eb72b0a1df7172de65c){version}[/wakeupcall/delete?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/wakeupcall/delete?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000","time":"11:00"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |
| **\[time\]** | String | Delete the specific alarm if the time is specified. Delete all alarms if the parameter is not sent. | 11:00 |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10021, 30001


###  {#play-music-to-an-extension}

### Play Music to an External Number {#play-music-to-an-external-number}

Note: can only operate on one extension at a time.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/outbound/playprompt?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/outbound/playprompt?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"outto": "41000","prompt":"111","fromext":"1000"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outto&gt;** | String | The external number | 41000 |
| **&lt;prompt&gt;** | String | The custom music | 111, the file name of the custom music |
| **\[fromext\]** | String | Which extension's call permission will be applied | 1000 |

**Response sample:**

{"status":"Success","callid":"1495701728.300"}

**Possible error code:** 10004, 10023, 10015, 10006, 30001


### Play Music to an Extension {#play-music-to-an-extension}

Note: can only operate on one extension at a time.

**Request method:** POST \(HTTPS\)

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/extension/playprompt?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/playprompt?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid": "1000","prompt":"111","autoanswer":"no"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | String | The extension number | 1000 |
| **&lt;prompt&gt;** | String | The custom music | 111, the file name of the custom music |
| **\[autoanswer\]** | String | Whether the extension will auto answer or not. This parameter requires the SIP phone to support. It means "no" if the parameter has not been specified. | yes/no |

**Response sample:**

{"status":"Success","callid":"1495697869.171"}

**Possible error code:** 10004, 10023, 10015, 10006, 30001


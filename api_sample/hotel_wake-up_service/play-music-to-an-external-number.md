###  {#play-music-to-an-extension}

### Play Music to an External Number {#play-music-to-an-external-number}

通过本接口可给外线号码播放提示音，IPPBX拨打外线，外线响铃接起后，听到提示音。支持多段提示音拼接播放。请求时多段提示音用‘+’号连接。注：该提示音文件名不能为纯数字，也不能有‘+’号。

Through this interface, developers could play music to an external number. The workflow is as follows: the PBX system dials an external number and the moment the outbound call is established, the music will be played automatically. Multiple pieces of music can be played consecutively as if it were one; separate the file names of different pieces of music with "+" in the request. Be sure that the file name of music cannot be a pure number, nor can it include the character "+".

**前提条件：**所有的提示音必须为已经上传至IPPBX的自定义提示音。

**Precondition:** all custom music used must be uploaded to the PBX system Custom Prompt list beforehand.

**说明：**PSTN外线拨出去时，不管终端话机有没有接起线路已经接通，这属于特殊情况，此接口对PSTN无效。

**Note: **this interface does not take effect on PSTN line. Because the moment an outbound call is dialed out through the PSTN trunk, whether it is picked up or not, the call is established.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/outbound/playprompt?token=7d20390952e15eb72b0a1df7172de65c){version}[/outbound/playprompt?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/outbound/playprompt?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"outto": "41000","prompt":"hello111","fromext":"1000"}

{ "outto": "1000000","prompt":"1+queue1+queue2","autoanswer":"no"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;outto&gt;** | String | The external number | 41000 |
| **&lt;prompt&gt;** | String | The custom music | hello111, the file name of the custom music |
| **\[fromext\]** | Int | Which extension's call permission will be applied | 1000 |

**Response sample:**

{"status":"Success","callid":"1495701728.300"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10023, 10015, 10006, 30001


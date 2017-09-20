### Play Music to an Extension {#play-music-to-an-extension}

通过本接口可给分机播放提示音，IPPBX拨打分机，分机响铃接起后，听到提示音。支持多段提示音拼接播放。请求时多段提示音用‘+’号连接。注：该提示音文件名不能为纯数字，也不能有‘+’号。

Through this interface, developers could play music to an extension. The workflow is as follows: the PBX system dials a specific extension number and after the extension rings and the call gets picked up, the music will be played automatically. Multiple pieces of music can be played consecutively as if it were one; separate the file names of different pieces of music with "+" in the request.

Note: the file name of music cannot be a pure number, nor can it  include the character "+". 

**前提条件：**所有的提示音必须为已经上传至IPPBX的自定义提示音。

**Precondition:** all custom music used must be uploaded to the PBX system Custom Prompt list beforehand.

**Request method:** POST \(HTTPS\)

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/extension/playprompt?token=7d20390952e15eb72b0a1df7172de65c){version}[/extension/playprompt?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/extension/playprompt?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

**Play only one prompt:** {"extid": "1000","prompt":"hello111","autoanswer":"no"}

**Play consecutive multiple prompts:** { "extid": "1000000","prompt":"1+queue1+queue2","autoanswer":"no"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | Int | The extension number | 1000 |
| **&lt;prompt&gt;** | String | The custom music | hello111, the file name of the custom music |
| **\[autoanswer\]** | String | Whether the extension will auto answer or not. This parameter requires the SIP phone to support. It means "no" if the parameter has not been specified. | yes/no |

**Response sample:**

{"status":"Success","callid":"1495697869.171"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10004, 10023, 10015, 10006, 30001


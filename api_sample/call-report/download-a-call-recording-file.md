# Download a Call Recording File

Through this interface, call recording files of the S-Series VoIP PBX can be acquired.

How to:

Step1: fetch the name of the global recording file through the “recording” parameter in the CDR event

Step 2: get a random string consisting of numbers and characters, which is created by the system, by sending a request with the file name \(as the request example below\) to S-Series.

Step 3: combine the random string with other elements to form a specific download address.

**说明：**随机串的有效时长为30秒，并且每个随机串使用过一次则失效。

**Request method: **POST\(HTTPS\)

**Request address: **[https://192.168.5.150:8088/api/v1.0.1/recording/get\_random?token=3efd4cd64e0d06e84a98230601428106](https://192.168.5.150:8088/api/v1.0.1/recording/get_random?token=3efd4cd64e0d06e84a98230601428106)

**Request sample:**

{"recording":"20170901181806-1504261084.7-1001-1003-Internal.wav"}

**Request parameters descriptions:**

| Parameter Name | Type | Description | Sample |
| :--- | :--- | :--- | :--- |
| &lt;recording&gt; | string | The name of the call recording file | hello001 |

**Response sample:**

{"status":"Success","recording":"20170901181806-1504261084.7-1001-1003-Internal.wav","random":"120732c546381fb020f17fba676b0ea0"}

**Responseparameters:**

| Parameter Name | Type | Description | Sample |
| :--- | :--- | :--- | :--- |
| &lt;status&gt; | string | Result | Success or Failed |
| &lt;recording&gt; | string | The name of the global recording file | Hello001 |
| &lt;random&gt; | string | A random string created for call recording file download. It serves as a component of a specified request address for download. |  |

**Download requestaddresssample\(random string combination method\):**

[https://192.168.5.150:8088/api/v1.0.1/recording/download?recording=20170724103619-1500860177.268-2000-2001-Internal.wav&random=7e60c59d187783f06ccc03621c4ad736&token=75c5891b32203d0615f9e3753a7cb779](https://192.168.5.150:8088/api/v1.0.1/recording/download?recording=20170724103619-1500860177.268-2000-2001-Internal.wav&random=7e60c59d187783f06ccc03621c4ad736&token=75c5891b32203d0615f9e3753a7cb779)


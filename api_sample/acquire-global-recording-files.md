# Acquire Auto Recording files

Through this interface, auto recording files of an IPPBX can be acquired.

**The acquisition method is as follows:**

Step 1: fetch the name of the auto recording file through the “recording” parameter in the CDR event

Step 2: get a random string consisting of numbers and characters, which is created by the system, by sending a request with the file name \(as the request example below\) to IPPBX

Step 3: combine the random string with other elements to form a specific download request address

**Note: **the random string is only valid for 30 seconds, and each random string can be used only once.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.1/recording/get_random?token=3efd4cd64e0d06e84a98230601428106){version}[/recording/get\_random?token=3efd4cd64e0d06e84a98230601428106](https://192.168.5.150:8088/api/v1.0.1/recording/get_random?token=3efd4cd64e0d06e84a98230601428106)

**Request sample:**

{"recording":"20170901181806-1504261084.7-1001-1003-Internal.wav"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;recording&gt;** | String | The name of the auto recording file | hello001 |

**Response sample:**

{"status":"Success","recording":"20170901181806-1504261084.7-1001-1003-Internal.wav","random":"120732c546381fb020f17fba676b0ea0"}

**Response parameters:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;Status&gt;** | String | Result | Success or Failed |
| **&lt;recording&gt;** | String | The name of the auto recording file | Hello001 |
| **&lt;random&gt;** | String | A random string created for auto recording file download. It serves as a component of a specified request address for download. | N/A |

**Download request address sample \( random string combination method\):**

[https://192.168.5.150:8088/api/v1.0.1/recording/download?recording=20170724103619-1500860177.268-2000-2001-Internal.wav&random=7e60c59d187783f06ccc03621c4ad736&token=75c5891b32203d0615f9e3753a7cb779](https://192.168.5.150:8088/api/v1.0.1/recording/download?recording=20170724103619-1500860177.268-2000-2001-Internal.wav&amp;random=7e60c59d187783f06ccc03621c4ad736&amp;token=75c5891b32203d0615f9e3753a7cb779)


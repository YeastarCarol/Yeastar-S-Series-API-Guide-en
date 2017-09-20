# "**Apply All" Interface（新增页面）**

In general, when developers do some system or extension configurations mentioned in this guide, like configuring an extension or IVR, using the S-Series API, the new settings will be applied automatically after the corresponding requests succeed. In order to avoid some exception that configuration made through the API failed to be applied because of the high frequency of system automatic apply, developers can invocate this interface to apply all settings after all operations are done.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/{version}/apply?token=4444ed5e207395035e4ec29a6bf09ece](https://192.168.5.150:8088/api/{version}/apply?token=4444ed5e207395035e4ec29a6bf09ece)

**Request parameters descriptions:**

No parameter. Only need to send the request.

**Request sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |




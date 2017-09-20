# 应用（Apply）**接口**

# **Apply All Interface**

使用API配置分机或者IVR等时，配置成功后会自动应用。为避免使用API配置时频繁应用出现应用不生效情况，用户可在统一配置完毕后，调用此接口统一应用一次。

In general, when developers do some system or extension configurations mentioned in this guide, like configuring an extension or IVR, using the S-Series API, the new settings will be applied automatically after the corresponding requests succeed. In order to avoid some exception that configuration using API failed to be applied resulted by the high frequency of system automatic apply, developers can invocate this interface to apply all settings after all operations are done.

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




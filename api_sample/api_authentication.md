## API Authentication {#api-authentication}

### Login {#login}

S-Series VoIP PBX API uses username and password credentials for authentication. The application server must provide the correct username and password for API to process the request.

注：密码需用户自己使用MD5加密之后的32位小写密码进行验证。如果密码连续错误五次，则该第三方应用的IP将会被锁10分钟。

**Note: **you need to encrypt the password with MD5 first for authentication. After encryption, the password should consist of 32 lowercase letters. If you enter the wrong password consecutively for 5 times, the IP address of the application server will be blocked for 10 minutes.

**Request Method:** POST

**Request address: **[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/login){version}[/login](https://192.168.5.150:8088/api/v1.0.0/login)

**Request sample:**

{"username": "api","password": "2d7257a528679d01a19c70e3fa773620","port": "8260"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;username&gt;** | String | The API username configured in the IPPBX  Programming Interface | api |
| **&lt;password&gt;** | String | The API password configured in the IPPBX Programming Interface | Password composed of 32 lowercase letters with MD5 encrypted |
| **&lt;port&gt;** | String | The port number, this port will be used by the application server to monitor the report sent by API. | 0&lt;port&lt;65536 |
| **\[url\]** | String | URL of the application server. This URL is used to specify the sending path of the event report to the application server. If the parameter is not configured, the event report will be sent to the application sever by default. |  |

**Response sample:**

{"status":"Success","token":"48a7d7481a5355aa4fb5dc285edeb40e"}

**Response parameters descriptions:**

**Note: all the succeeding requests will require the "token" returned here.**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Request Status | Success, Failure |
| **&lt;token&gt;** | String | Token for interface invocation. All the succeeding requests require the token. | 1ec8bde364f8e37c0dd14f476fba114c |

注：所有的API请求都需要带上登录返回的token，且该token有效时长为30分钟，30分钟内如果API和第三方应用没有任何事件交互（如：第三方应用发送API请求），则该token将被IPPBX系统清除。可通过心跳包接口延长token的有效时长，每发送一次心跳包可使token的有效时长延长30分钟。

**Note: **all API requests will require the "token" returned here. The token is valid only for 30 minutes, within which, if there is no event interaction between S-Series API and the application server \(for example, the application server sends API request to S-Series VoIP PBX\), the token will be erased by the IPPBX system. The application server can prolong the validity time of the token by sending a Heartbeat packet to the IPPBX via the Heartbeat packet interface. Every time a packet is sent, the token validity time will be prolonged for 30 minutes.

**Possible error code:** 20003

### Heartbeat Packet {#heartbeat-packet}

With heartbeat packet, S-Series VoIP PBX can update IP, Port, and URL. Token can also be updated, so to avoid failure of report if token was erased after 1900s.

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/v1.0.0/heartbeat?token=48a7d7481a5355aa4fb5dc285edeb40e](https://192.168.5.150:8088/api/v1.0.0/heartbeat?token=48a7d7481a5355aa4fb5dc285edeb40e)

**Request sample:**

{"ipaddr": "192.168.11.144","port": "8260","url":"1112121212"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ipaddr&gt;** | String | IP | 192.168.12.144 |
| **&lt;port&gt;** | String | The port number, this port will be used by the application server to monitor the report sent by API. | 0&lt;port&lt;65536 |
| **\[url\]** | String | URL of the application server |  |

### Logout {#logout}

**Request method:** POST

**Request sample:**

[https://192.168.5.150:8088/api/v1.0.0/logout?token=48a7d7481a5355aa4fb5dc285edeb40e](https://192.168.5.150:8088/api/v1.0.0/logout?token=48a7d7481a5355aa4fb5dc285edeb40e)

**Response sample:**

{"status":"Success"}


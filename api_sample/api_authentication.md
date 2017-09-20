## API Authentication（新增2个Note，表格内容，） {#api-authentication}

### Login {#login}

S-Series VoIP PBX API uses username and password credentials for authentication. The application server must provide the correct username and password for API to process the request.

**Note: **you need to encrypt the password with MD5 first for authentication. After encryption, the password should consist of 32 lowercase letters. If you enter the wrong password consecutively for 5 times, the IP address of the application server will be blocked for 10 minutes.（新增）

**Request Method:** POST

**Request address: **[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/login){version}[/login](https://192.168.5.150:8088/api/v1.0.0/login)

**Request sample:**

{"username": "api","password": "2d7257a528679d01a19c70e3fa773620","port": "8260"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;username&gt;（改）** | String | The API username configured in the "Settings-&gt;PBX-&gt;General-&gt;API" of S-Series VoIP PBX Web interface. | api |
| **&lt;password&gt;\(改\)** | String | The API password configured in the "Settings-&gt;PBX-&gt;General-&gt;API" of S-Series VoIP PBX Web interface. | Password composed of 32 lowercase letters with MD5 encrypted |
| **&lt;port&gt;** | String | The port number, this port will be used by the application server to monitor the report sent by API. | 0&lt;port&lt;65536 |
| **\[url\]（改）** | String | URL of the application server. This URL is used to specify the sending path of the event report to the application server. If the parameter is not specified, the event report will be sent to the IP address of theapplication sever by default. |  |

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

当连接IPPBX的第三方应用的IP地址、监听端口或者URL有变更的时候，可通过API的心跳包接口对IP, Port, URL进行更新。同时当第三方应用和API没有事件交互的时候，可利用此接口定期发送请求从而更新token的有效时长，避免token在1800秒超时后被清除，造成事件不会上报以及请求失败。

With heartbeat packet, S-Series VoIP PBX can update IP, Port, and URL of the conntected 3rd party application server if there are any changes. In addition, when there is no event interaction between the application server and S-Series API, heartbeat packets can be sent to the IPPBX periodically to prolong the validity time of the token, so to avoid failure of report if the token was erased after 1800s.

注：发送一次心跳包请求可使token的有效时长延长1800秒。

**Note:** every time a heartbeat packet is sent, the validity time of the token will be prolonged for 1800s.

**Request method:** POST

**Request address: **[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/heartbeat?token=48a7d7481a5355aa4fb5dc285edeb40e){version}[/heartbeat?token=48a7d7481a5355aa4fb5dc285edeb40e](https://192.168.5.150:8088/api/v1.0.0/heartbeat?token=48a7d7481a5355aa4fb5dc285edeb40e)

**Request sample:**

{"ipaddr": "192.168.5.150","port": "8260","url":"1112121212"}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ipaddr&gt;** | String | Updated IP address of the application server | 192.168.5.150 |
| **&lt;port&gt;** | String | Updated port number; this port will be used by the application server to monitor the report sent by API. | 0&lt;port&lt;65536 |
| **\[url\]** | String | Updated URL of the application server |  |

**Response sample:**

{"status":"Success"}

### Logout

**Note:** The token used in the Request sample below is the token returned when S-Series API login authentication is passed.

**Request method:** POST

**Request sample:**

[https://192.168.5.150:8088/api/](#){version}[/logout?token=48a7d7481a5355aa4fb5dc285edeb40e](#)

**Response sample:**

{"status":"Success"}


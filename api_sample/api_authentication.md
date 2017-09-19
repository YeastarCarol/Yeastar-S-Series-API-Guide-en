## API Authentication {#api-authentication}

### Login {#login}

S-Series VoIP PBX API uses username and password credentials for authentication. The application server must provide the correct username and password for API to process the request.

Note: you need to encrypt the password with MD5 first for authentication.

**Request Method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/login

**Request sample:**

{&quot;username&quot;: &quot;api&quot;,&quot;password&quot;: &quot;2d7257a528679d01a19c70e3fa773620&quot;,&quot;port&quot;: &quot;8260&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;username&gt;** | String | The API username | api |
| **&lt;password&gt;** | String | The API password | MD5 encrypted |
| **&lt;port&gt;** | String | The port number, this port will be used by the application server to monitor the report sent by API. | 0&lt;port&lt;65536 |
| **[url]** | String | URL of the application server |  |

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;,&quot;token&quot;:&quot;48a7d7481a5355aa4fb5dc285edeb40e&quot;}

**Response parameters descriptions:**

**Note: all the succeeding requests will require the &quot;token&quot; returned here.**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Request Status | Success, Failure |
| **&lt;token&gt;** | String | Token for interface invocation. All the succeeding requests require the token. | 1ec8bde364f8e37c0dd14f476fba114c |

**Possible error code:** 20003

### Heartbeat Packet {#heartbeat-packet}

With heartbeat packet, S-Series VoIP PBX can update IP, Port, and URL. Token can also be updated, so to avoid failure of report if token was erased after 1900s.

**Request method:** POST

**Request address:**

https://192.168.5.150:8088/api/v1.0.0/heartbeat?token=48a7d7481a5355aa4fb5dc285edeb40e

**Request sample:**

{&quot;ipaddr&quot;: &quot;192.168.11.144&quot;,&quot;port&quot;: &quot;8260&quot;,&quot;url&quot;:&quot;1112121212&quot;}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;ipaddr&gt;** | String | IP | 192.168.12.144 |
| **&lt;port&gt;** | String | The port number, this port will be used by the application server to monitor the report sent by API. | 0&lt;port&lt;65536 |
| **[url]** | String | URL of the application server |  |

### Logout {#logout}

**Request method:** POST

**Request sample:**

https://192.168.5.150:8088/api/v1.0.0/logout?token=48a7d7481a5355aa4fb5dc285edeb40e

**Response sample:**

{&quot;status&quot;:&quot;Success&quot;}
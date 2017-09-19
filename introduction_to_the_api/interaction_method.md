## Interaction Method {#interaction-method}

S-Series VoIP PBX interacts with the application server through HTTPS protocol: sends HTTPS request, and receives the application server's HTTPS response. S-Series VoIP PBX and the application server both act as a server and a client for each other.

**Interaction Protocol**

The default interaction protocol is HTTPS. It will use the same protocol of the S-Series VoIP PBX webpage. It is recommended that the user replace it with a certificate issued by a professional provider.

**Contents**

Contents are defined by .json.

**Interaction Method**

There are two interaction methods between S-Series VoIP PBX and the application server.

1. The application server sends request to S-Series VoIP PBX.

In this case, the application server is the client, and S-Series PBX will function as the server. The picture below shows this scenario: the application server initiates the call and the query.

说明：所有API请求都需带上API登录验证时所返回的的Token，即API的调用接口凭证。并且该token有效时长为30分钟，30分钟内如果API和第三方应用没有任何事件交互（如：第三方应用向IPPBX发送API请求；API向第三方应用发送事件报告），则该token将被IPPBX系统清除。第三方应用可通过心跳包接口向IPPBX发送心跳包的方式更新token的有效时长，每发送一次心跳包可使token的有效时长延长30分钟。

Note: All API requests require the token returned when S-Series API login authentication is passed, namely, the token for interface invocation, which is valid only for 30 minutes. Within the validity time of the token, if there is no event interaction between S-Series API and the application server \( for example, the application server sends API request to S-Series VoIP PBX, or S-Series API sends event report to the application server\), the token will be erased by the S-Series VoIP PBX. The application server can prolong the validity time of the token by sending a Heartbeat packet to the IPPBX via the Heartbeat packet interface. Every time a packet is sent, the token validity time will be prolonged for 30 minutes.

![interaction method](../assets/interaction_method.png)

2. S-Series VoIP PBX pushes notifications to the application server.

In this case, the application server is the server, and S-Series VoIP PBX will function as the client.

**Condition:** the application server needs to pass the S-Series API authentication and establish connection with S-Series API.

The picture below shows this scenario: S-Series VoIP PBX notifies the application server with the change of extension's call status.

![interaction method-2](../assets/interaction_method-2.png)


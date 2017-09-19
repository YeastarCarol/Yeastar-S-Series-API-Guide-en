## Interaction Method {#interaction-method}

S-Series VoIP PBX interacts with the application server through HTTPS protocol: sends HTTPS request, and receives the application server&#039;s HTTPS response. S-Series VoIP PBX and the application server both act as a server and a client for each other.

*   **Interaction Protocol**

The default interaction protocol is HTTPS. It will use the same protocol of the S-Series VoIP PBX webpage. It is recommended that the user replace it with a certificate issued by a professional provider.

*   **Contents**

Contents are defined by .json.

### Interaction Method {#interaction-method-0}

There are two interaction methods between S-Series VoIP PBX and the application server.

1\. The application server sends request to S-Series VoIP PBX.

In this case, the application server is the client, and S-Series PBX will function as the server. The picture below shows this scenario: the application server initiates the call and the query.

![interaction method](../assets/interaction_method.png)

2\. S-Series VoIP PBX pushes notifications to the application server.

In this case, the application server is the server, and S-Series VoIP PBX will function as the client.

Condition: the application server needs to pass the S-Series API authentication and establish connection with S-Series API.

The picture below shows this scenario: S-Series VoIP PBX notifies the application server with the change of extension&#039;s call status.

![interaction method-2](../assets/interaction_method-2.png)
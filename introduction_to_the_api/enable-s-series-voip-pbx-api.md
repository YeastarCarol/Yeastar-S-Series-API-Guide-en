# Enable S-Series VoIP PBX API（步骤1的2\) 3\) 4\),来电接听控制有更改，新增状态监控） {#enable-s-series-voip-pbx-api}

Before using API, the 3rd party software needs to establish connection with S-Series VoIP PBX and S-Series API requires username and password authentication.

The following are instructions on enabling the API feature and configuring API parameters.

1.Log in S-Series Web interface. Enter "Settings-&gt;PBX-&gt;General-&gt;API".

1\) Check "Enable".

2\) Input the username and password. The password should be a combination of uppercase and lowercase letters and numbers.

Note: the username and the password here will be used by the 3rd party software to establish connection with S-Series VoIP PBX through S-Series API.

3\) Choose the extensions that require status monitoring. All extensions are chosen by default. Whenever the extension status changes \(for example,  the call status of extension changes from Busy to Idle\), the API will send a report of trunk status changing to the application server.

![](/assets/3.png)

4\) Decide if the trunks need to enable Status Monitor \(enable by default\), Control Inbound Call Answering, and Control Inbound Call Destination.

**Control Inbound Call Answering**

If enabled, all inbound calls to the trunk will be handled by the API client first. The API client can decide whether to answer or decline that call within 10 seconds. When it times out, the call will be answered.

Answer: if the call is answered,  it will be directed to the destination defined in inbound route.

Decline: if the call is declined, it will be hung up without reaching out to the IPPBX, and the call will not be recorded on the IPPBX Call Logs.

**Control Inbound Call Destination**

If enabled, all inbound calls to the trunk will not go to the destination defined in inbound route. Instead, the API client has 10 seconds to direct the call to a designated destination. When it times out, the call will go to the default inbound route destination.

**Status Monitoring **

If enabled, whenever there is a change in trunk status \(for example, the trunk status changes from "Registered" to "Unregistered"\), the API will send a report of trunk status changing to the application server.

![](/assets/4.png)


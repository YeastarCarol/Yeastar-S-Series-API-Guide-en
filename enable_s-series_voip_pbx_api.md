# Enable S-Series VoIP PBX API {#enable-s-series-voip-pbx-api}

Before using API, the 3rd party software needs to establish connection with S-Series VoIP PBX and S-Series API requires username and password authentication.

The following are instructions on enabling the API feature and configuring API parameters.

1.  Log in S-Series Web interface. Enter &quot;Settings-&gt;PBX-&gt;General-&gt;API&quot;.
2.  Check &quot;Enable&quot;.
3.  Input the username and password. The password should be a combination of uppercase and lowercase letters and numbers.
4.  Choose the extensions that require status monitoring.
5.  Decide if the trunks need to enable Status Monitor, Control Inbound Call Answering, and Control Inbound Call Destination.

*   **Control** Inbound **Call Answering**

If enabled, all inbound calls to the trunk will be handled by the API client first. The API client can decide whether to answer or decline that call within 10 seconds. When it times out, the call will be answered.

*   **Control** Inbound **Call Destination**

If enabled, all inbound calls to the trunk will not go to the destination defined in inbound route. Instead, the API client has 10 seconds to direct the call to a designated destination. When it times out, the call will go to the default inbound route destination.
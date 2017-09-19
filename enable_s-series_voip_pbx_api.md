# Enable S-Series VoIP PBX API {#enable-s-series-voip-pbx-api}

Before using API, the 3rd party software needs to establish connection with S-Series VoIP PBX and S-Series API requires username and password authentication.

The following are instructions on enabling the API feature and configuring API parameters.

1.Log in S-Series Web interface. Enter "Settings-&gt;PBX-&gt;General-&gt;API".

1\) Check "Enable".

2\) Input the username and password. The password should be a combination of uppercase and lowercase letters and numbers.

3\) Choose the extensions that require status monitoring. 默认所有都勾选，则当该分机状态有变更时（如：分机状态从忙变为空闲），API会主动向第三方应用发送中继状态变更的事件报告。All extensions are chosen by default. Whenever the extension status changes \(for example,  the call status of extension changes from Busy to Idle\),  S-Series API will send a report of trunk status changing to the application server.

![](/assets/3.png)

4\) Decide if the trunks need to enable Status Monitor, Control Inbound Call Answering, and Control Inbound Call Destination.

**Control Inbound Call Answering**

勾选来电接听控制之后，当该条中继有来电时先交由第三方应用处理，可选择接受或者拒绝该来电。

接受：如果第三方应用选择接受该来电，则该来电直接进入对应呼入路由目的地。

拒绝：如果第三方应用选择拒绝该来电，则该来电将被直接挂断，而不会到达IPPBX，IPPBX上也不会有该来电的通话记录。

IPPBX将留有10秒给第三方应用处理的时间，超时则默认第三方应用接受该来电，则该来电直接进入对应呼入路由的目的地。

If enabled, all inbound calls to the trunk will be handled by the API client first. The API client can decide whether to answer or decline that call within 10 seconds. When it times out, the call will be answered.

Answer: if the call is answered,  it will be directed to the destination defined in inbound route.

Decline: if the call is declined, it will be hung up without reaching out to the IPPBX, and the call will not be recorded on the IPPBX Call Logs.

**Control Inbound Call Destination**

If enabled, all inbound calls to the trunk will not go to the destination defined in inbound route. Instead, the API client has 10 seconds to direct the call to a designated destination. When it times out, the call will go to the default inbound route destination.

**状态监控**

勾选中继的状态监控后，当该中继状态有变更时（如：中继状态从注册上变为注册失败），API会主动向第三方应用发送中继状态变更的事件报告。

**Status Monitoring **

If enabled, whenever the trunk status changes \(for example, the trunk status changes from Registered to Unregistered\), S-Series API will send a report of trunk status changing to the application server.

![](/assets/4.png)


### Add an Alarm {#add-an-alarm}

通过本接口可以给分机设置闹铃。

Through this interface, developers could add alarm to extensions.

说明：支持多个分机一起添加闹铃相同的闹铃，且一次只能添加一个闹铃，如一次添加多个则只有第一个生效。如需多个分机添加同一个闹铃，则分机之间使用逗号隔开。

Note: the same alarm can be added to multiple extensions; separate the extension number with comma. Only one alarm can be added for one time. If multiple alarms are added for a time, only the first alarm added will take effect.

For example:

{"extid":"1000,1001","wakeup":\[{"time":"00:45","type":"onetime","repeats":"3","repeatinterval":"5"}\]}

**Request method:** POST

**Request address:**

[https://192.168.5.150:8088/api/](https://192.168.5.150:8088/api/v1.0.0/wakeupcall/create?token=7d20390952e15eb72b0a1df7172de65c){version}[/wakeupcall/create?token=7d20390952e15eb72b0a1df7172de65c](https://192.168.5.150:8088/api/v1.0.0/wakeupcall/create?token=7d20390952e15eb72b0a1df7172de65c)

**Request sample:**

{"extid":"1000","wakeup":\[{"time":"00:45","type":"onetime","repeats":"3","repeatinterval":"5"}\]}

**Request parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;extid&gt;** | Int | The extension number | 1000 |
| **&lt;wakeup&gt;** | Object | Object |  |
| **&lt;time&gt;** | String | Time | 11:22 |
| **&lt;type&gt;** | String | Type, when the &lt;type&gt; is "onetime", the alarm will be deleted after the alarmhas repeated for designated times. | Options: onetime, everyday, custom |
| **\[weekdays\]** | String | The options available when the above &lt;type&gt; is "custom" | Options:1, 2, 3, 4, 5, 6, 0      1 to 6 correspond to Monday to Saturday, 0 corresponds to Sunday |
| **\[repeats\]** | String | How many times will the alarm be repeated | Options: 1, 2, 3 |
| **\[Repeatinterval\]** | String | The interval in minutes between each repeat | 5 |
| **\[Prompt\]** | String | The prompt played | helloworld, the file name of the custom prompt. Without the parameter, the default prompt "macroform-cold\_day" will be played. |

**Response sample:**

{"status":"Success"}

**Response parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;status&gt;** | String | Result | Success or Failed |

**Possible error code:** 10006, 10020, 30001

###  {#query-an-alarm}




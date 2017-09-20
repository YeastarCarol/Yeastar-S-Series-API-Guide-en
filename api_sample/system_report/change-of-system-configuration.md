### Change of System Configuration（新增表格） {#change-of-system-configuration}

The PBX will send a report to the application server when the PBX’s configuration changes. So the application server can sync the changes timely.

At present, only the trunk and extension configuration change will be reported. But the detailed changes won't be provided in the report.

**Report sample:**

{"action":"ConfigChange","type":"trunk","trunkname":"SIP-142","operation":"del"}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;configchange&gt;** | String | Configuration change | N/A |
| **&lt;type&gt;** | String | Type | Trunk, extension |
| **&lt;trunkname&gt;** | String | The name of trunk with configuration change | S-142 |
| **&lt;operation&gt;** | String | Operation | add, delete, update |




# Prompt Play End

This is used to report the event when the prompt played to the extension and the external number ends.

**Report sample:**

**Prompt played to extension ends:**

{"action":"PlayPromptEnd","callid":"1495780325.384","ext":{"extid":"1002"},"prompt":"appletest"}

**Prompt played to external number ends:**

{"action":"PlayPromptEnd","callid":"1505352996.281","outbound":{"trunkname":"Apple\_test"},"prompt":"appletest"}

**Report parameters descriptions:**

| **Parameter Name** | **Type** | **Description** | **Sample** |
| --- | --- | --- | --- |
| **&lt;action&gt;** | String | Prompt play end | PlayPromptEnd |
| **&lt;prompt&gt;** | String | The file name of the prompt played | appletest |
| **&lt;callid&gt;** | String | A unique identifier of the call | 1495780325.384 |
| **&lt;outbound&gt;** | Object | Whether it's an inbound or outbound call|  N/A|
| **&lt;trunkname&gt;** | String | Trunk name | Apple_test |




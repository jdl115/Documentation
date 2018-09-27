---
uid: unity-statistics
---

## Statistics
During a game session Trivver Unity SDK sends some information to Trivver’s servers regarding [AdSpots](xref:adspot), [Branded Assets](xref:branded_asset) and [Generic Assets](xref:generic_asset) that a user sees and interacts with. This information is then used to calculate statistics that help both a developer and an advertiser to evaluate the effectiveness of their effort into the game and the advertising campaign. Also, this information is used for billing purposes and compensation accrual.

There are two types of data that is sent to the servers: Viewability and Engagement.

### Viewability ###
[!include[](shared/unity-viewability.md)]

### Engagement  
[!include[](shared/unity-engagement.md)]

## Technical information
Trivver SDK uses long-lived TCP connections to send the statistics. Typically only one long-lived connection to one of the servers is active in a time but in case of network failures or others network-related issues Trivver SDK may reconnect to another server to guarantee timely delivery of the statistics.

If a network partition occurs Trivver SDK tries to send already collected statistics several times before remove it from the processing.

The statistics is sent outside of the main game loop and cannot affect the game process.

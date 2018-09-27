---
uid: unity-settings
---

In Trivver settings developer can set up all necessary parameters for Trivver Unity SDK. All this settings are stored in a special file called “Trivver settings.asset” that is located at “Assets/Trivver/Resources/” path and can be viewed in Unity Inspector.  
Trivver settings can be accessed via Trivver menu or by selecting that file. 
> [!NOTE]
> Make sure that inspector tab is opened to be able to see Trivver Settings.  

![Trivver settings](../../images/trivver_settings.png "Trivver settings")

| Property          | Description|
|-------------------|------------|
| Login/Password    | To be able set the game, it's version or to make AdSpot [synchronization](xref:unity-sync-term) you have to be logged in with active Trivver developer account. | 
| Game              | Here you have to select the game that you've created in the dashboard. |
| Version           | Set current version of the game. For more details about versions see [Versions and publishing](xref:unity-versions)
| Game Measurement  | All [branded assets](xref:unity-branded-asset) are measured in real world units. And when they are downloaded in your game they will appear with that real size. If the scale of your  game doesn't correspond to 1 unit = 1m accordance you have to adjust this parameter.|
| Use SmartTab      | Enables/disables SmartTab. See [SmartTab section](xref:smarttab) for more information. If unchecked, SmartTab is fully ignored in the system.|
| Enable on start   | If true, SmartTab open button is shown right after Trivver initialization. Otherwise developer has to show it from code.  ```Trivver.TrivverSDK.SmartTab.Enable();``` |
| Interrupt loading | This feature interrupts asset loading if AdSpot was seen by gamer. So there is now visible object replace effect on the screen.
| Sync Data         | Opens [Sync Data window](xref:unity-sync-term). |
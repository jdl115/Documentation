# Glossary

## AdSpot
AdSpot is a center of Trivver Unity SDK. In general it is a place for ads - an area in your game where you want [branded asset](xref:unity-branded-asset-term) to be loaded and displayed. AdSpot defines which [branded asset](xref:unity-branded-asset-term) will be loaded in it (by Categories) and how this asset will be positioned, aligned and scaled (if needed).  
In AdSpot properties you define Categories that will define what assets are going to be loaded in it.  
When you create new AdSpot you will see blue cube called “AdSpot Volume”. It shows the volume that defines maximum size of the downloaded branded asset. Also there are arrows with labels that shows direction  of the spot. For example if you place spot for TV you place it on the wall with forward direction looking from the wall.  
You can adjust this Volume by dragging green handles or in the inspector menu. In general it is very similar to setting size of Box Collider in Unity.  
AdSpot can be created via Trivver menu in two ways:  
**Create AdSpot** - create new AdSpot with small cube as [generic asset](xref:unity-generic-asset-term). It is supposed that you will replace that cube with your own model at later time.  
**Create AdSpot for selected object** - create AdSpot based on selected object, i.e. AdSpot will be placed, oriented and scaled to fit selected object size. And then this object will be set as a child of the created AdSpot.
![AdSpot](../../images/adspot.png "AdSpot")

If you delete child of the AdSpot it becomes "empty". Yellow plane gizmo displays that. You have to add your own model (called [generic asset](xref:unity-generic-asset-term)) to AdSpot that will be shown in case if there is no suitable [branded asset](xref:unity-branded-asset-term) on the server or there is any problems with network. This model is called [generic asset](xref:unity-generic-asset-term).  
To add [generic asset](xref:unity-generic-asset-term) to AdSpot you have to add this asset to your scene as a child of the AdSpot. 
When branded asset is loaded generic asset is replaced by it.  
Select AdSpot to see all it's properties in the inspector.
> [!NOTE]
> AdSpot сan only have one child. If there is more than one child in AdSpot it will not work properly.


![AdSpot with generic object](../../images/adspot_positioning.gif "AdSpot with generic object")
![AdSpot inspector](../../images/adspot_inspector.png "AdSpot inspector")
![AdSpot Hierarchy](../../images/adspot_hierarchy.png "AdSpot Hierarchy")


| Property              | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Guid                  | AdSpot unique identifier used by the Trivver system. It is generated when you create or duplicate AdSpot.                                                                                                                                                                                                                                                                                                                                                                               |
| Categories            | AdSpot Categories define what [branded asset](xref:unity-branded-asset-term) will be loaded from the server. To assign/remove categories yoo have to press "Edit" button below Categories control. You may define as many categories as you like to describe more precisely what object you want to be loaded into the spot. For example: Vehicle, Car, Cabriolet, sport car                                                                                                                                                                                   |
| Description           | Short description of the AdSpot.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Scaling               | After loading [branded asset](xref:unity-branded-asset-term) there might be situation that it is bigger than AdSpot Volume. In this situation AdSpot will rescale branded asset according to this parameter. </br> <ul> <li> **Fit if bigger** - branded asset will be resized only if it is bigger than AdSpot Volume. The asset will be proportionally scaled down while it is fit into the Volume. If the asset is smaller than AdSpot Volume it will stay with original size. </li> <li> **Fit Always** - branded asset will always be re-scaled to fit the volume. So, if for example downloaded asset is smaller than volume it will be scaled up to fit the volume. </li> </ul>                              |
| Asset loading scheme  | <ul> <li> **OnStart** - asset will be loaded to the AdSpot on it’s Start function automatically when the scene loaded.  </li> <li> **Manually** - after level loading AdSpot won’t request any [branded asset](xref:unity-branded-asset-term) until @Trivver.AdSpot.LoadBrandedAsset is called for this spot. </li> <ul>                                                                                                                                                                                                               |
| Use only cached assets | Used when `OnStart` asset loading scheme is used. AdSpot will load asset only if that asset was cashed in #Asset pool so it can be loaded and displayed instantly.                                                                                                                                                                                                                                                                                                                        |
| Display gizmo         | Shows/Hides AdSpot gizmo (blue box with arrows)                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Align position        | Align position matrix defines two things: first it defines where the pivot point of the AdSpot is placed. Second it defines how #branded asset is aligned within the AdSpot.For example if you set matrix to mid, mid, back - pivot point of AdSpot will be place in the center of bottom face of AdSpot Volume.                                                                                                                            |
| Volume                | AdSpot Volume in numbers. This is absolute size value in world units. If you somehow scaled AdSpot, the size of the volume will be recalculated.                                                                                                                                                                                                                                                                                                                                        |
| Reset volume          | Set the Volume size as the size of [generic asset](xref:unity-generic-asset-term)                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Take screenshot       | For more convenient managing of AdSpots on the server or in AdSpot browser (upcoming feature) you can create screenshots for each AdSpot. All screenshots are saved in special Trivver folder and can be removed by developer at any time without any harm to the system. Because in Unity it is hard to catch AdSpot deletion in the editor, screenshots are not deleted if you delete AdSpot. To remove unused screenshots you can use “Delete unused previews” tool in Trivver menu. |

## AdSpot Volume
AdSpot volume defines volume in space that can be covered by downloaded [branded object](xref:branded-asset-term).  
You can see it as a blue cube if display gizmo checked in AdSpot properties. It can be adjusted directly in scene view by dragging green dots, or by setting size in the inspector.

## Branded asset
Model provided by advertiser. This is asset that is received from the server and placed in [AdSpot](xref:unity-adspot-term).

## Engagement
**TODO**

## Generic asset
Model that developer place in [AdSpot](xref:unity-adspot-term). This model is used when [branded asset](xref:unity-generic-asset-term) is not loaded. When you create [AdSpot](xref:unity-adspot-term) you have to add generic asset as a child of the spot.

## Trivver main menu
After import you have Plugins/Trivver folder. And new ‘Trivver’ item in the Unity main menu.

![Trivver menu](../../images/trivver_menu.png "Trivver menu")  

Menu item | Description
----------|------------
Edit settings | Open Trivver settings in the inspector. For more info see [sdk set up section](xref:unity-setup)
Sync data with server | Open AdSpot synchronization dialog. This item is enabled only if you are logged in as a developer in Trivver Settings. For more info see [Synchronization section](xref:unity-sync)
Delete unused previews | Delete unused preview images from ```Assets/Trivver/Editor/AdSpotScreenshots/``` folder.
Create AdSpot | Create empty AdSpot in currently opened scene.
Create AdSpot for selected object | Create new AdSpot in place of the selected object and place this object in the created AdSpot.
Create Preloader for scene | Add scene preloader in to currently opened scene. For more info see [Asset preloading section](xref:unity-preloading)
Create preloader for game | Add Game preloader in to currently opened scene. For more info see [Asset preloading section](xref:unity-preloading)
Legacy Unity 5.5 mode | Use this option if you are using Unity 5.5 version. It disables some features available only in Unity 5.6 and above.

## Pre-loading
There are few options how [branded assets](xref:branded-asset-term) can be loaded to [AdSpot](xref:unity-adspot-term):
- (Default) [AdSpot](xref:unity-adspot-term) automatically starts loading asset at ```AdSpot.Start()```.
- Loading must be triggered manually by @Trivver.AdSpot.LoadBrandedAsset call.

It is not a secret that loading of 3d models and textures requires CPU time. We do our best to reduce this load,
but some developers do not trust 3rd party components, especially in such thin place as performance.
For this case, we introduced the opportunity to pre-load [branded assets](xref:branded-asset-term) before game / scene starts.

We have @Trivver.TrivverSDK.AssetPool, it holds all loaded assets cache. Every time [AdSpot](xref:unity-adspot-term) requires branded asset, it requests it from AssetPool. 

And depending on [AdSpot](xref:unity-adspot-term) `Use only cached assets` option, asset will be requested from server (or not):

![Use only cached assets]( ../../images/use_only_cached_asset.png "Use only cached assets")

if `Use only cached assets` is checked and AssetPool does not contain requested [Asset](xref:branded-asset-term) - it will never be loaded for that [AdSpot](xref:unity-adspot-term).

Thus if you don't want [Asset](xref:branded-asset-term) loading occur during game play. It is possible to do it
at game or scene loading, by simple pre-loading assets to AssetPool. Next time [AdSpot](xref:unity-adspot-term) will request [Asset](xref:branded-asset-term) -- it will be already loaded. 

### Assets Pre-loader

![pre-loading]( ../../images/preloading_setup.png "pre-loading")

1. Create ```AssetsPreloaderScene``` from prefab (or add `Cache Assets for scene` to existing `GameObject`)
2. Set Target Scene field, name of next scene. 
3. Set timeout.

Result: After scene run -- asset loading will be triggered for all [AdSpots](xref:unity-adspot-term) which have been synced from `FirstScene`. When loading will be finished -- component will Load next scene.

#### Fields description

| Field                     | Description                                                                                                                          |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Start Automatically       | Start pre-loading at MonoBehavior.Start(). If it is not checked -- loading can be started by `CacheAssetsForScene.Startpreloading()` |
| Timeout Seconds           | It is possible to restrict maximum loading time.                                                                                     |
| On Finish                 | Allows to subscribe on pre-loading finish.                                                                                            |
| On Progress               | Subscribe on this event if it is required to track loading progress.                                                                 |
| Target Scene              | Name of scene which will be loaded after pre-loading.                                                                                 |
| Load Scene When Finished  | Load `Target Scene` when pre-loading will be finished.    |

> [!NOTE]
> It is worth to mention if pre-loading will fail it will also be considered as finish, and it will trigger OnFinish event and
> start scene loading. 

> [!NOTE]
> `Use only cached assets` helps to avoid second loading attempt at gameplay, if pre-loading was interrupted.

### Pre-loading from your code

- Write own component based on examples:

    ```
    Scripts/Examples/CacheAssetsByUidExample.cs
    Scripts/Examples/CacheAssetsExample.cs
    Scripts/Examples/CacheAssetsForGameExample.cs
    Scripts/Examples/CacheAssetsForSceneExample.cs
    ```
- Use helper functions from AssetPool:
    - @Trivver.IAssetPool.CacheAssetsForGame
    - @Trivver.IAssetPool.CacheAssetsForGame(System.Action,Trivver.OnInterruptedHandler,System.Action{System.Single})
    - @Trivver.IAssetPool.CacheAssetsForScene(System.String)
    - @Trivver.IAssetPool.CacheAssetsForScene(System.String,System.Action,Trivver.OnInterruptedHandler,System.Action{System.Single})
- Manually pre-load [asset](xref:branded-asset-term) for each [AdSpots](xref:unity-adspot-term) using AssetPool
    - @Trivver.IAssetPool.CacheAssetsForAdSpots(System.Collections.Generic.IEnumerable{System.String})
    - @Trivver.IAssetPool.CacheAssetsForAdSpots(System.Collections.Generic.IEnumerable{System.String},System.Action,Trivver.OnInterruptedHandler,System.Action{System.Single})
    - @Trivver.IAssetPool.CacheAssetsForAdSpots(System.Collections.Generic.IEnumerable{Trivver.SyncedAdSpotInfo},System.Action,Trivver.OnInterruptedHandler,System.Action{System.Single})

 ## Trivver settings

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

## Synchronization

After [AdSpots](xref:unity-adspot-term) and [Trivver settings](xref:unity-settings-term) are set up properly you have to make Synchronization. This process will collect data about all spots in your project validate it (check if there are any spots without categories and all guid's are unique) and send to the server. After this process you can see all your spots in the Developer Dashboard.  

> [!NOTE]
> You have to make synchronization each time you:
> * Add new/delete AdSpots.
> * Modifying categories or description of existing AdSpots.
> * Changing scenes names or moving scenes to another folder. 

Synchronization window can be accessed via Trivver menu or in the Trivver Settings by pressing Sync data button.

![Sync data window]( ../../images/sync_data-window.png "Sync data window")

> [!NOTE]
> To be able to make synchronization, you have to be logged in in Trivver Settings.

In this window you can see a list of scenes of your project. You can choose to show only scenes from build settings or from overall project. Near each scene there is a checkbox that allows to exclude/include scenes from synchronization.

| Property   | Description|
|------------|------------|
| Current version   | Current game version. Synchronization will be associated with this version. This parameter is set from Trivver Settings. For more info see [Versions and publishing section](xref:unity-versions-term) |
| Sync images       | If true AdSpot previews will be uploaded to the server. If you changed AdSpots and didn't change previews you can uncheck this toggle to save sync time. |
| Project scenes    | <ul> <li> Project - scene list will show all scenes from the project. </li> <li> Build settings - scene list will show only scenes from build settings. </li> </ul>     |
| Sync              | Start synchronization.|

While the synchronization Trivver opens all specified scenes and collects all adSpots data and then sends it to the server. So, before you start the process, make sure that you saved all changes in currently opened scene.

## Game version and publishing

When you release your Unity game on any store, it is common to freeze all Trivver configuration (AdSpot list and categories) for that release. Otherwise it is possible to break the game for existing users after new synchronization.  
For this purpose we have game versions.  You can create new versions in developer dashboard.

Here is the draft workflow for versions: 

### How To

After you created a new game, by default new version "1" is added to the game. You can see it in the bottom of the Game page:

![Game version]( ../../images/dashboard_game_version.png "Game version")  
You can edit it's title (version itself) notes and change it's status to published. Also you can add new version.

![Game version edit]( ../../images/dashboard_game_version_edit.png "Game version edit")  



In Unity sdk Trivver Settings you can select created version as current one:  
![Trivver settings]( ../../images/trivver_settings.png "Game version")

When you are ready to publish your game in any store you would like to freeze trivver configuration. Otherwise simple synchronization will lead to wrong data to be loaded to the end users.  
To prevent this you publish the version of the game. Since the version is published you can't make synchronization to this version in Unity editor.   
Instead you will create new version and make any sync with this new version till new release.  

## Viewability

Viewability is collected by Trivver SDK constantly during the game but sent periodically every few seconds. The duration which Viewability is collected by Trivver Unity SDK before sending is non-configurable by a developer and can vary.

**TODO**  
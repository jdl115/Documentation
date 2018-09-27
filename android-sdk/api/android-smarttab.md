
## Class SmartTab
Smart Tab it is an object for management Smart Tab Layout

### Classes
#### <a href="android-builder.md">Builder</a>
Holds options for creating instance Smart Tab

### Fields
| type | Name | Description |
|---|---|---|
| int | LOG_LEVEL_INFO | Log all informations, include warning and error |
| int | LOG_LEVEL_WARN | Log all warning messages |
| int | LOG_LEVEL_ERROR | Log all api errors |
| int | MINIMAL_UPDATE_INTERVAL_MILLIS | Minimal time interval update assets |
| int | DEFAULT_UPDATE_INTERVAL_MILLIS | Default time interval update assets |

### Methods
#### newBuilder()
Create instance Builder
##### Declaration

```java
public static Builder newBuilder(@NonNull Activity aActivity)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| Activity | aActivity | instance activity in which use Smart Tab |
##### Returns
| type | Description |
|---|---|
| <a href="android-builder.md">Builder</a> | SmartTab instance builder |

#### isOpened()
Check visibility of SmartTab
##### Declaration

```java
public boolean isOpened()
```
##### Returns
| type | Description |
|---|---|
| boolean | true if SmartTab is open and visible to user |

#### open()
Open Smart Tab programmatically with animation
##### Declaration

```java
public void open()
```

#### close()
Close Smart Tab programmatically with animation
##### Declaration

```java
public void close()
```

#### toggleSmartTabButton(boolean)
Change visibility of SmartTab toggleSmartTabButton
##### Declaration

```java
public SmartTab toggleSmartTabButton(boolean aShowSmartTab)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| boolean | aShowSmartTab | change visibility of toggleSmartTabButton, default value TRUE |
##### Returns
| type | Description |
|---|---|
| <a href="android-smarttab.md">SmartTab</a> | SmartTab instance |

#### setAssetsUpdateInterval(int)
Set assets update interval when Smart Tab was closed
##### Declaration

```java
public SmartTab setAssetsUpdateInterval(int aTime)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| boolean | aTime | Update interval in milliseconds, default value 180 000 |
##### Returns
| type | Description |
|---|---|
| <a href="android-smarttab.md">SmartTab</a> | SmartTab instance |

#### setGameData(@NonNull String, @NonNull String)
Set data for creating session before loading assets list
##### Declaration

```java
public SmartTab setGameData(@NonNull String aGameUid, @NonNull String aGameVersion)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| String | aGameUid | Game Uid (obtained at developer dashboard)|
| String | aGameVersion | Game version (obtained at developer dashboard)) |
##### Returns
| type | Description |
|---|---|
| <a href="android-smarttab.md">SmartTab</a> | SmartTab instance |

#### getLogLevel()
Get log level which setup when create builder
##### Declaration

```java
public int getLogLevel()
```
##### Returns
| type | Description |
|---|---|
| int | Log level which was established when create Smart Tab |

#### isLogEnabled()
Check value of current status of enable logging
##### Declaration

```java
public boolean isLogEnabled()
```
##### Returns
| type | Description |
|---|---|
| boolean | If TRUE logs Smart Tab is enabled |

#### onSaveState(Bundle)
Save state Smart Tab
##### Declaration

```java
public void onSaveState(@Nullable Bundle aBundle)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| Bundle | aBundle | bundle with data from method onSaveInstanceState|

#### onDestroy()
Free up used resources. Should be called at Activity method onDestroy()
##### Declaration

```java
public void onDestroy()
```

#### setListener(Interface)
Set SmartTab events listener
##### Declaration

```java
public SmartTab setListener(Interface SmartTab.SmartTabListener aListener)
```
##### Parameters
| type | Name | Description |
|---|---|---|
|  SmartTab.SmartTabListener | aListener | Listener for SmartTab state change events|
##### Returns
| type | Description |
|---|---|
| <a href="android-smarttab.md">SmartTab</a> | Smart Tab instance |

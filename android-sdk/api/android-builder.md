## Class Builder
Bilder is needed to create Smart Tab
### Constructors
#### Builder(@NonNull Activity, @Nullable Bundle)
##### Declaration

```java
Builder (@NonNull Activity aActivity)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| Activity | aActivity | instance activity in which use Smart Tab |

### Methods
#### setSavedInstanceState(@Nullable Bundle)
Set state to restore
##### Declaration

```java
public Builder setSavedInstanceState(@Nullable Bundle aBundle)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| String | aBundle | state|
##### Returns
| type | Description |
|---|---|
| <a href="android-builder.md">Builder</a> | Builder instance |

#### setGameData(@NonNull String, @NonNull String)
Set data for creating session before loading assets list.
##### Declaration

```java
public Builder setGameData(@NonNull String aGameUid, @NonNull String aGameVersion)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| String | aGameUid | game Uid (obtain at developer dashboard)|
| String | aGameVersion | game version (obtain at developer dashboard) |
##### Returns
| type | Description |
|---|---|
| <a href="android-builder.md">Builder</a> | Builder instance |

#### setAssetsUpdateInterval(int)
Set time interval between assets loading
##### Declaration

```java
public Builder setAssetsUpdateInterval(int aAssetsUpdateIntervalMillis)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| boolean | aAssetsUpdateIntervalMillis | update interval in milliseconds, default value 180 000 |
##### Returns
| type | Description |
|---|---|
| <a href="android-builder.md">Builder</a> | Builder instance |

#### setLogLevel(int)
Set log level
##### Declaration

```java
public Builder setLogLevel(@LogUtil.LogLevel int aLogLevel)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| int | aLogLevel | Log level, default value 0 (SmartTab.LOG_LEVEL_INFO) |
##### Returns
| type | Description |
|---|---|
| <a href="android-builder.md">Builder</a> | Builder instance |

#### setLogEnabled(boolean)
Set log is enabled
##### Declaration

```java
public Builder setLogEnabled(boolean isLogEnabled)
```
##### Parameters
| type | Name | Description |
|---|---|---|
| boolean | isLogEnabled | if TRUE logs is enable, default value TRUE |
##### Returns
| type | Description |
|---|---|
| <a href="android-builder.md">Builder</a> | Builder instance |

#### SmartTab build()
Create <a href="android-smartab.md">Smart Tab</a> instance with provided params
##### Declaration

```java
public SmartTab build()
```
##### Returns
| type | Description |
|---|---|
| <a href="android-smartab.md">Smart Tab</a> | SmartTab instance |
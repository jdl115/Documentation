---
uid: ios-smarttabconfig
---

## Class SmartTabConfig 
SmartTabConfig is needed to configure Smart Tab.

### Initialization

``` objc
SmartTabConfig *config = [SmartTabConfig defaultConfig];
```

### Methods
#### configSmartTabWithUserSessionsession:gameUID:gameVersion:enableLogging:logLevel:
Configure Smart Tab.
##### Declaration

```objc
- (void)configSmartTabWithUserSession:(SMUserSession* _Nonnull)session
                              gameUID:(NSString* _Nonnull)gameUID
                              gameVersion:(NSString* _Nonnull)version
                              enableLogging:(BOOL)enableLogging
                              logLevel:(enum TrivverLogLevel)logLevel;
```
##### Parameters
| type | Name | Description |
|---|---|---|
| <a href="ios-userSession.md">SMUserSession</a> | session | SMUserSession instance |
| NSString | gameUID | game Uid (obtain at developer dashboard) |
| NSString | version | game version (obtain at developer dashboard)|
| BOOL | enableLogging | enable logging|
| TrivverLogLevel | logLevel | log level. Enum which has three possible options:</br> _TrivverLogLevelInfo_ - Log all informations include warnings and errors;</br>_TrivverLogLevelWarning_ - Log only warnings and errors;</br>_TrivverLogLevelError_ - Log error only;|

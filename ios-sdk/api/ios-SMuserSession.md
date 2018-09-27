---
uid: ios-smusersession
---
## Class SMUserSession 
SMUserSession object is needed to establish connection with the Trivver server.

### Initialization

``` objc
SMUserSession *session = [[SMUserSession alloc] init];
```

##### Properties
| type | Name | Description |
|---|---|---|
| NSString | firstName | First name of player |
| NSString | lastName | Last name of player |
| NSString | age | Age of player |
| NSString | sex | Sex of player |
| NSString | state | Player's state |
| NSString | city | Player's city |
| NSString | country | Player's country |
| NSString | ipAddr | Player's IP address |
| NSString | deviceId | Player's device ID. Obtaine it from <a href="ios-SmartTabConfig.md">SmartTabConfig</a> class  <code>deviceUID</code> property. |

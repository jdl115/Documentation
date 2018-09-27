---
uid: ios-setup
---

## Setup SDK
The peculiarity of our SDK is that it creates Smart Tab on top of all content on the app's page. We recommend to add it to window.

#### Config Smart Tab
* Create session info

```objc
    SMUserSession *session = [[SMUserSession alloc] init];
    session.firstName = @"John";
    session.lastName = @"Doe";
    session.sex = @"m";
    session.state = @"CA";
    session.city = @"New York City";
    session.country = @"USA";
    session.ipAddr = @"127.0.0.1";
    session.deviceId = [SmartTabConfig deviceUID];
```
* Config game id, session info, game version, logging enable

```objc
    [config configSmartTabWithUserSession:self.session 
                            gameUID:@"da9b8884-38d1-42b1-9185-07e9e7c0afc0"
                            gameVersion:@"1"
                            enableLogging:true
                            logLevel:TrivverLogLevelInfo];
```

* showSmartTabButton: Boolean

	Set this property to hidden/unhidden button open
	
* initializeOnStart: Boolean

	Start Trivver when app started

#### Create smart tab
`    SmartTabView *smartTabView = [[SmartTabView alloc]] init];`
#### Add to window
`   [smartTabView showAtWindow];`
#### Toogle smart tab programmatically
* Show:

`   [smartTabView open];`

* Close

`   [smartTabView close];`

* Toggle

`[smartTabView toggleSmartTab];`


* Check Smart Tab is opened or not

`BOOL isOpen = [smartTab isOpened];`

#### Smart Tab Button

* Show smart tab button

`[smartTabView showSmartTabButton];`

* Hide smart tab button

`[smartTabView hideSmartTabButton];`

* Check visibility of smart tab button

`BOOL isVisible = [smartTab isSmartTabButtonVisible];`

* Set transparency for smart tab button

`[smartTabView setSmartTabButtonAlpha:0.5];`

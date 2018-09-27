# TRIVVER SDK INSTALLATION
## I. REQUIREMENT
* **AFNetworking**. Download from here: 
[https://github.com/AFNetworking/AFNetworking/releases/tag/3.1.0]()
* Trivver SDK Framework
* IOS 8.0 and above

## II. INSTALLATION
Add require native framework
![](images/2.png)
Add embedded binaries
![](images/3.png)
## III. GET STARTS
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
    session.deviceId = @"b539f694-279b-48c6-bef6-e50b96789c45";
```
* Config game id, session info, game version, logging enable

```objc
    [config configSmartTabWithUserSession:self.sesstion gameUID:@"da9b8884-38d1-42b1-9185-07e9e7c0afc0"
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


#### Log level
There are 3 levels:

```objc
	typedef enum : NSUInteger {
   		 TrivverLogLevelInfo,
   		 TrivverLogLevelWarning,
    		TrivverLogLevelError,
	} TrivverLogLevel;
```
* **Info**: Log all informations, include warning and error.
* **Warning**: Log all warning messages.
* **Error**: Log all api errors.

## IV. Example
Demo app is there: [https://gitblit.saritasa.com/trivver/ios-sdk.git]()

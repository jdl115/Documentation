---
uid: ios-logging
---

## Trivver Logging system
SDK supports log display of three levels:

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

To setup logs in SmartTab, change the properties in SmartTabConfig

`@property (nonatomic, assign) BOOL enableLogging;`

`@property (nonatomic, assign) TrivverLogLevel logLevel;`

Default parameters are logs is enabled and log level `TrivverLogLevelInfo `

In case you consider it unnecessary to obtain logs you can disable logging.

To view logs in console need use filter by key SmartTab

* **Info**: Log all informations, include warning and error.
* **Warning**: Log all warning messages.
* **Error**: Log all api errors.



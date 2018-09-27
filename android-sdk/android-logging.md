---
uid: android-logging
---

## Trivver Logging system
SDK supports log display of three levels:

```java
    SmartTab.LOG_LEVEL_INFO = 0;
    SmartTab.LOG_LEVEL_WARN = 1;
    SmartTab.LOG_LEVEL_ERROR = 2;
```

To setup logs in SmartTab necessary at creating builder call methods:

`setLogEnabled(boolean)`

`setLogLevel(int)`

Default parameters are logs is enabled and log level `SmartTab.LOG_LEVEL_INFO`

Or you can set the logging create properties file in your project (src/main/assets/trivver.properties) with the following content:

```java
#enableLog on Smart Tab Layout (Enable == 1) (Disable == 0)
enableLog=1

#logLevel=0 (INFO); logLevel=1 (WARN); logLevel=2 (ERROR)
#INFO (INFO + WARN + ERROR), WARN (WARN + ERROR), ERROR (ERROR only)
logLevel=0
```

In case you consider it unnecessary to obtain logs you can disable logging.

To view logs in IDE need use filter by key SmartTab

* **Info**: Log all informations, include warning and error.
* **Warning**: Log all warning messages.
* **Error**: Log all api errors.



---
uid: ios-loading
---

## Loading of Branded Assets

By default, the SDK updates assets each 3 minutes while SmartTab is closed, so the user could see new assets while using your application.  
This time period can be changed via code:  

`- (void)changeRefreshDataTime:(int)time;`
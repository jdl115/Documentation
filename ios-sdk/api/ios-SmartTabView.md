---
uid: ios-smarttabview
---

## Class SmartTabView 
SmartTabView is needed to create an instance of Smart Tab in the current controller.

### Initialization

``` objc
SmartTabView *smartTabView = [[SmartTabView alloc] init];
```

### Methods
#### showAtWindow
Show at window view
##### Declaration

```objc
- (void)showAtWindow;
```

#### open
Open smart tab programmatically
##### Declaration

```objc
- (void)open;
```

#### close
Close smart tab programmatically
##### Declaration

```objc
- (void)close;
```

#### toggleSmartTab
Toggle smart tab
##### Declaration

```objc
- (void)toggleSmartTab;
```

#### isOpened
Check smart tab is opened or not
##### Declaration

```objc
- (BOOL)isOpened;
```
##### Returns
| type | Description |
|---|---|
| BOOL | Whether Smart Tab is open or not |

#### isSmartTabButtonVisible
Check smart tab button is visible or not
##### Declaration

```objc
- (BOOL)isSmartTabButtonVisible;
```
##### Returns
| type | Description |
|---|---|
| BOOL | Whether Smart Tab is visible or not |

#### showSmartTabButton
Show smart tab toogle button
##### Declaration

```objc
- (void)showSmartTabButton;
```

#### hideSmartTabButton
Hide smart tab toogle button
##### Declaration

```objc
- (void)hideSmartTabButton;
```

#### setSmartTabButtonAlpha:
Set transparency for open button
##### Declaration

```objc
- (void)setSmartTabButtonAlpha:(CGFloat)alpha;
```

#### changeRefreshDataTime:
Set time interval between assets loading
##### Declaration

```objc
- (void)changeRefreshDataTime:(int)time;
```

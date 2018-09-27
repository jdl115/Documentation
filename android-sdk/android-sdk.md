# TRIVVER SDK INSTALLATION
## I. REQUIREMENT
* Trivver SDK Framework
* Android minSdkVersion 14 and above

## II. INSTALLATION
In order to use Trivver SDK Framework your need add the following dependence in build.gradle in your app:

```groovy
compile 'com.trivver:trivver-smarttab:1.0.23:prodRelease@aar'
```

Also our sdk requires the use of the following additional dependencies:

```groovy
compile "com.android.support:recyclerview-v7:latest_version"
compile "com.google.android.gms:play-services-ads:latest_version"
compile "com.squareup.retrofit2:retrofit:latest_version"
compile "com.squareup.retrofit2:converter-gson:latest_version"
compile "com.squareup.retrofit2:converter-scalars:latest_version"
compile "com.squareup.okhttp3:logging-interceptor:latest_version"
compile 'com.github.bumptech.glide:glide:latest_version'
```

## III. GETTING STARTED
#### initialize Smart Tab

The following code shows how to initialize Smart Tab in Activity:

```java
SmartTab mSmartTab;
@Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mSmartTab = SmartTab.newBuilder(this, savedInstanceState).
                                    setGameData(GAME_UID, GAME_VERSION).
                                    setUpdateAdvertising(true).
                                    setTimeUpdateAdvertising(30000).
                                    build();
    }

//To save the state SmartTab
@Override
protected void onSaveInstanceState(final Bundle outState){
    Bundle bundle = mSmartTab.onSaveState(outState);
    super.onSaveInstanceState(bundle);
}

//To restore the state SmartTab
@Override
protected void onRestoreInstanceState(final Bundle savedInstanceState){
    mSmartTab.onRestoreState(savedInstanceState);
    super.onRestoreInstanceState(savedInstanceState);
}

//To clear state SmartTab
@Override
  protected void onDestroy(){
      mSmartTab.onStop();
      super.onDestroy();
}
```

#### Check SmartTab is showing on screen, true if Smart Tab is showing

`isOpened();`

#### Open SmartTab programmatically with animation

`javascript`

#### Close SmartTab programmatically with animation

`close();`

#### Show SmartTab toogle button
Show toogle button of SmartTab if true. Default value true.

`toggleSmartTabButton(boolean);`

#### Auto update advertising
Auto-update advertising after close Smart Tab user. Default value true.

`setUpdateAdvertising(boolean);`

#### Time period update advertising
Set time period updating advertising after close SmartTab. Time period set in milliseconds and should not be less than 180000. Default value 180000.

`setTimeUpdateAdvertising(int);`

#### Events Smart Tab

`addEventsListener(Interface SmartTabLayout.OnSmartTabListener);`

#### Set game data

`setGameData(@NonNull String aGameUid, @NonNull String aGameVersion);`

#### Get log level which setup when create builder;

`getLogLevel()`

`isLogEnabled();`

#### Lifecycle Smart Tab
These methods necessary must be called in the appropriate methods Activity according to the example above

Call in onSaveInstanceState(Bundle)

`onSaveState(Bundle);`

Call in onRestoreInstanceState(Bundle) 

`onRestoreState(Bundle);`

Call in onDestroy() 

`onStop();`




## IV. Example
Demo app is there: [https://gitblit.saritasa.com/trivver/android-sdk.git]()

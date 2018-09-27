---
uid: android-setup
---

## Setup SDK
Our SDK creates SmartTab as a View sitting on top of activity content. 

The following code shows how to initialize SmartTab in Activity:

```java
SmartTab mSmartTab;
@Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mSmartTab = SmartTab.newBuilder(this)
                            .setSavedInstanceState(savedInstanceState)
                            .setGameData(BuildConfig.GAME_UID_WITH_ASSETS, 
                                         BuildConfig.GAME_VERSION)
                            .setAssetsUpdateInterval(SmartTab.DEFAULT_UPDATE_INTERVAL_MILLIS)
                            .build();
    }
```

In order to make SmartTab to work call these two methods:  
`onSaveState(Bundle);`  
`onDestroy();`

```java
//To save the state SmartTab
@Override
protected void onSaveInstanceState(final Bundle outState){
    super.onSaveInstanceState(aOutState);
    mSmartTab.onSaveState(aOutState);
}

//To clear state SmartTab
@Override
  protected void onDestroy(){
      mSmartTab.onDestroy();
      super.onDestroy();
}
```


To handle Trivver SmartTab life cycle there is special listener:  
```java
mSmartTab.addListener(new SmartTab.SmartTabListener(){

            @Override
            public void onSmartTabOpened(){
                Log.d(TAG, "onOpened ");
            }

            @Override
            public void onSmartTabClosed(){
                Log.d(TAG, "onClosed ");
            }

            @Override
            public void onSmartTabAssetsLoaded(){
                Log.d(TAG, "onAssetsLoaded ");
            }

        });
```


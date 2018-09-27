---
uid: unity-logging
---

# Trivver Logging system

No one likes when 3rd party plugin sends spam to developer console or game log. This makes log - useless, hides useful messages, makes developer to disable some types of messages (log, warning, error).

But in other hand - if something works unexpected, log is the only place where you can find the clue.

There is no silver bullet and we don't know how much details developer wants to know about Trivver functioning. That is why we introduced advanced logging system for Trivver. 
Every error/warning/info message which we send intentionally - we send through our Trivver.Logger class. Thus we are able to filter out any messages from our system.

We pre-configured logging settings for common usage. But main idea - developer may adjust it as he wants.

## It is possible:

- Filter out messages by type:
    ```cs
    public enum LogType
    {
        Error = 0,
        Assert = 1,
        Warning = 2,
        Log = 3,
        Exception = 4
    }
    ```

- Filter out messages by tag, default tags:
    ```cs
    public enum LogTag
    {
        Statistics,
        AssetLoading,
        SpotAssetMatching,
        Preloading,
        Misc,
        Net
    }
    ```
- Disable logging.
- Change settings separately for PlayMode / EditorMode.

>[!NOTE]
>It is not possible to disable messages with type `LogType.Error` and `LogType.Exception`. The only way to disable them - disable Trivver logging entirely.

>[!NOTE]
>Some message tags are filtered out by default. If you want to see full log, use:
>```cs
>// Disable LogType filtering
>Trivver.TrivverSDK.LoggingSettingsPlayMode.FilterLogType = LogType.Log;
>Trivver.TrivverSDK.LoggingSettingsEditMode.FilterLogType = LogType.Log;
>
>// Clear LogTags filter
>Trivver.TrivverSDK.LoggingSettingsPlayMode.FilterLogTags.Clear();
>Trivver.TrivverSDK.LoggingSettingsEditMode.FilterLogTags.Clear();
>```


## Example 1:

```cs
// Lines from below make filter hide messages with tags: LogTag.Statistics, LogTag.SpotAssetMatching.
// And does not show messages with LogType.Log.
// Since we use LoggingSettingsPlayMode these changes will affect messages come to log when Application.isPlaying = true.
LoggingSettingsPlayMode.ResetTagFilter(new [] { LogTag.Statistics, LogTag.SpotAssetMatching });
LoggingSettingsPlayMode.FilterLogType = LogType.Warning;
```

>[!NOTE]
>LoggingSettingsPlayMode.FilterLogType works like Unity  [Logger.filterLogType](https://docs.unity3d.com/ScriptReference/Logger-filterLogType.html):


## Example 2:
```cs
// Line from below make filter hide messages with tags: LogTag.Net
// Since we use LoggingSettingsPlayMode these changes will affect messages comes to log when Application.isPlaying = false.
LoggingSettingsEditMode.ResetTagFilter(new [] { LogTag.Net });
```
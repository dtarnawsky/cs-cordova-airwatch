# Cordova Airwatch
This cordova app is an example of using `airwatch-sdk-plugin` plugin.

On Android 12 it is failing:
```
2022-12-02 12:50:28.364 28188-28232/io.ionic.airwatch E/AndroidRuntime: FATAL EXCEPTION: pool-4-thread-1
    Process: io.ionic.airwatch, PID: 28188
    java.lang.IllegalArgumentException: io.ionic.airwatch: Targeting S+ (version 31 and above) requires that one of FLAG_IMMUTABLE or FLAG_MUTABLE be specified when creating a PendingIntent.
    Strongly consider using FLAG_IMMUTABLE, only use FLAG_MUTABLE if some functionality depends on the PendingIntent being mutable, e.g. if it needs to be used with inline replies or bubbles.
        at android.app.PendingIntent.checkFlags(PendingIntent.java:382)
        at android.app.PendingIntent.getBroadcastAsUser(PendingIntent.java:673)
        at android.app.PendingIntent.getBroadcast(PendingIntent.java:660)
        at androidx.work.impl.utils.ForceStopRunnable.getPendingIntent(ForceStopRunnable.java:196)
        at androidx.work.impl.utils.ForceStopRunnable.isForceStopped(ForceStopRunnable.java:128)
        at androidx.work.impl.utils.ForceStopRunnable.run(ForceStopRunnable.java:93)
        at androidx.work.impl.utils.SerialExecutor$Task.run(SerialExecutor.java:91)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1167)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:641)
        at java.lang.Thread.run(Thread.java:920)
2022-12-02 12:50:28.920 28188-28188/io.ionic.airwatch E/AW_Native: JNI_OnLoad: Failed to initialise the crypto library
2022-12-02 12:50:28.956 28188-28188/io.ionic.airwatch E/AirWatch: Unauthorized App Access. Add app to console and install via Anchor app. Error code:-71
```

### Capacitor App
An equivalent Capacitor app is available with the same issue:
https://github.com/dtarnawsky/cs-capacitor-airwatch
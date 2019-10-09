# Interceptd SDK
[![alt text](https://app.interceptd.com/static/media/logo.37dfc8d6.svg "Interceptd")](https://interceptd.com/)

## Getting Started
The Interceptd SDK is available via:

**JCenter AAR**
    [ ![Download](https://api.bintray.com/packages/appsamurai/maven/analytics/images/download.svg) ](https://bintray.com/appsamurai/maven/analytics/_latestVersion)
    Interceptd SDK is available as an AAR via JCenter; to use it, add the following to your `build.gradle`.

   ``` java
   repositories {
       jcenter() // includes Interceptd SDK
   }

   dependencies {
       // Be sure that you are using latest version
       implementation 'com.ntrcptd.sdk:analytics:0.0.2'
   }
   ```

## Supported SDK Versions
Minimum supported SDK version is 14. Be sure that minSdkVersion in your gradle file isn't lower than 14.

## Usage
### SDK Import
**Kotlin Users**
```kotlin
import com.ntrcptd.ntrcptdsdk.InterceptdAnalytics
```

**Java Users**
```java
import com.ntrcptd.ntrcptdsdk.InterceptdAnalytics;
```

### SDK Initialization
Interceptd SDK is required for tracking. Application cannot track any information before SDK initialization is complete.
In application’s `onCreate` function of the initial activity, call  `InterceptdAnalytics.initialize` function with `applicationId` parameter. This parameter should be your application id from [Interceptd User Dashboard](https://interceptd.com/), you can use your application id for integration purposes. Check the following codes for sample:

**Kotlin Users**
```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    InterceptdAnalytics.initialize("your-user-id")
}
```

**Java Users**
```java
@Override
protected void onCreate (Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    InterceptdAnalytics.Instance.initialize("your-user-id");
}
```

### Custom Event Tracking
Using Interceptd SDK, you are able to track the frequency of custom events by placing the following code piece into your own application code. You can also attach data to your events. Only JSONObject is accepted as data. If you are planning to put an object as a value in JSONObject, make sure the object is JSON serializable.

**Kotlin Users**
```kotlin
InterceptdAnalytics.track(eventName: String)
InterceptdAnalytics.track(eventName: String, data: JSONObject)
```

**Java Users**
```java
InterceptdAnalytics.Instance.track(String eventName);
InterceptdAnalytics.Instance.track(String eventName, JSONObject data);
```

### Log Level
Interceptd SDK logging level can be changed with `setLogLevel` after  `InterceptdAnalytics.initialize` call. Default is <ASLog.Level.DEBUG>.

**Kotlin Users**
```kotlin
InterceptdAnalytics.setLogLevel(<ASLog.Level>)
```

**Java Users**
```java
InterceptdAnalytics.Instance.setLogLevel(<ASLog.Level>);
```

## Author
Interceptd Mobile Team
## License
Interceptd. All Rights Reserved, 2019
[![alt text](https://app.interceptd.com/static/media/logo.37dfc8d6.svg "Interceptd")](https://interceptd.com/)

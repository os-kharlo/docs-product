---
tags: runtime-mobileandreactiveweb
summary: Provides information about the status of the application's lifecycle. Used to protect the app during upgrades, when local model access shouldn't be allowed, and to customize the application loading process.
locale: en-us
guid: 90d5caaf-3d6a-4ddc-b2de-012bbec4c2f3
app_type: mobile apps, reactive web apps
platform-version: o11
---

# ApplicationLifecycle

<div class="info" markdown="1">

Applies to Mobile Apps and Reactive Web Apps only

</div>

Provides information about the status of the application's lifecycle. Used to protect the app during upgrades, when local model access shouldn't be allowed, and to customize the application loading process.

Example:

```javascript
// Check if the app is currently being upgraded
var isUpgrading = $public.ApplicationLifecycle.isUpgradingVersion();

var progressCallback = function(loaded, total) {
  // do something on upgrade progress
};

var loadCompleteCallback = function() {
  // do something on finish
};

$public.ApplicationLifecycle.listen({
  onUpgradeProgress: isUpgrading ? progressCallback : null,
  onLoadComplete: loadCompleteCallback
});
```

## Summary

|Functions|Description|
|---|---|
|[isUpgradingVersion](applicationlifecycle.md#isupgradingversion)|Returns `true` if the application version is currently being upgraded. Used to determine the kind of feedback to provide when the application is initialized (e.g. splash screen).|
|[listen](applicationlifecycle.md#listen)|Registers listeners for application load events.|

## Functions

### isUpgradingVersion

**isUpgradingVersion(): boolean**

Returns `true` if the application version is currently being upgraded. Used to determine the kind of feedback to provide when the application is initialized (e.g. splash screen).

Returns: boolean

### listen

**listen(eventHandlers: [ApplicationLoadEventHandlers](../intro.md#applicationloadeventhandlers)): void**

Registers listeners for application load events.

Parameters:

* **eventHandlers**: [ApplicationLoadEventHandlers](../intro.md#applicationloadeventhandlers)<br/> Object containing callbacks for the application loading events you want to listen to.

Returns: void


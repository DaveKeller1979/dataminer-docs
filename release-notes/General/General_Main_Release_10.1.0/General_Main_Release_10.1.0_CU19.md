---
uid: General_Main_Release_10.1.0_CU19
---

# General Main Release 10.1.0 CU19 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

### Enhancements

#### DataMiner Taskbar Utility: Enhanced installation of app packages [ID_33969]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

Using the DataMiner Taskbar Utility, it is now possible to install all possible types of app packages. To install an app, you can either double-click the .dmapp file or right-click the Taskbar Utility icon, click *Update* and select the app from the list.

Also, the *SLAppPackageInstaller.txt* log file will now keep track of all actions performed and issues encountered during the installation of an app.

#### Enhanced performance when an SNMP element using multi-threaded timers is polling multiple sources simultaneously [ID_34143]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

Because of a number of enhancements, overall performance has increased when an SNMP element using multi-threaded timers is polling multiple sources simultaneously.

#### Cassandra: Alarms indicating that the cluster is down will no longer be repeated as long as the status of the cluster remains the same [ID_34209]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

When the Cassandra database was down, up to now, the alarms indicating that the cluster is not in a healthy state would be repeated every 40 seconds. From now on, those alarms will no longer be repeated as long as the status of the cluster remains the same.

#### Enhanced logging of issues occurring when parsing a compliance cache file entry [ID_34212]

<!-- MR 10.0.0 [CU22]/10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

When an issue occurred when parsing a compliance cache file entry, up to now, a log entry of type "error" would be added to the SLDataMiner.txt log file.

From now on, when an issue occurs when parsing a compliance cache file entry, the following log entry of type "info" will be added to the SLDataMiner.txt log file instead:

```txt
Warning: <function> is unable to parse compliance cache file entry at line <line number>. <line content>
```

#### DataMiner Upgrade: Obsolete 'SNMP Simulation Generator' files removed from upgrade packages [ID_34250]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

All files related to the obsolete *SNMP Simulation Generator* tool have been removed from the DataMiner upgrade packages. This tool was replaced by the *QA Device Simulator* tool.

> [!NOTE]
> When you run an upgrade package on a system that contains this obsolete tool, it will automatically be removed.

### Fixes

#### Problem with SLAnalytics [ID_33850]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.9 -->

In some cases, a problem could occur with the SLAnalytics process, causing the process to restart. This happened when the alarm repository was retrieved while the connection was being dropped.

#### Service & Resource Management: Files in C:\Skyline DataMiner\ResourceManager would not be locked properly when being read or updated during a midnight synchronization [ID_34104]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

Up to now, the files stored in the `C:\Skyline DataMiner\ResourceManager` folder would not be locked properly when being read or updated during a midnight synchronization. File locking has now been improved.

#### Visual Overview: SurveyorSearchText variable continued to show cleared search input [ID_34114]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.9 -->

When the text in the Cube advanced search box was selected with Ctrl+A and then deleted, it could occur that the advanced search input was not cleared correctly, so that it continued to be shown by the *SurveyorSearchText* variable in Visual Overview.

#### SLNet could throw an OutOfMemoryException due to a memory leak [ID_34126]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

In some cases, SLNet could throw an OutOfMemoryException due to a memory leak.

#### Visual Overview: Connection highlight based on connection property not updated automatically [ID_34139]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.9 -->

When a connection in Visual Overview was highlighted based on a connection property, and the connection property changed, it could occur that the highlight style was not automatically applied to the connection line, but only after the user triggered a redraw, for example by clicking the highlight.

#### DataMiner Cube - Alarm Console: Alarms would incorrectly be grouped when the 'Automatically group according to arrangement' was not selected [ID_34153]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

When, in the hamburger button in the top-left corner of the Alarm Console, the *Automatically group according to arrangement* setting was not selected, upon reconnecting DataMiner Cube, the alarms would incorrectly be grouped anyway.

#### Scheduled alarm templates would incorrectly not be updated when the system time changed [ID_34154]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

When the system time changed because of e.g. a clock resynchronization or a switch to or from daylight-saving time, up to now, the start time and end time of scheduled alarm templates would incorrectly not get updated.

#### DataMiner Cube - Services app: No services would be loaded the first time you opened the Services app [ID_34211]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

When you opened the *Services* app for the first time after opening DataMiner Cube, in some cases, no services would be loaded. The services would only be loaded when you closed the *Services* app and opened it again.

#### Web apps: App would incorrectly log in again after the user had logged out [ID_34227]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

After a user had logged out of a web app, in some cases, that app would incorrectly continue to send out network requests and try to automatically log itself in again.

#### Run-time error in SLProtocol when a group was launched while a poll group with option 'PartialSNMP' was waiting for incoming SNMP data [ID_34233]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

When, on one thread, a group other than a poll group was launched while, on another thread, a poll group with option "partialSNMP" was waiting for incoming SNMP data, in some cases, a run-time error could occur in SLProtocol.

#### Dashboards app - Time range feed: Delete icons of custom quick pick buttons would incorrectly be displayed on top of the time range feed overlay [ID_34278]

<!-- MR 10.1.0 [CU19]/10.2.0 [CU7] - FR 10.2.10 -->

In some cases, the delete icons of custom quick pick buttons would incorrectly be displayed on top of the time range feed overlay.
# Permission

## 保护级别

### 普通权限

普通权限涵盖应用程序需要访问应用程序沙箱外部数据或资源，但涉及用户隐私或影响其他应用程序操作的风险很小。例如，设置时区的权限是正常权限。

* ACCESS_LOCATION_EXTRA_COMMANDS 允许应用程序访问额外的位置提供程序命令。
* ACCESS_NETWORK_STATE 允许应用程序访问有关网络的信息。
* ACCESS_NOTIFICATION_POLICY 对希望访问通知政策的应用程序的标记权限。托管配置文件不支持此权限。
* ACCESS_WIFI_STATE 允许应用程序访问有关Wi-Fi网络的信息。
* BLUETOOTH 允许应用程序连接到配对的蓝牙设备。
* BLUETOOTH_ADMIN 允许应用程序发现并配对蓝牙设备。
* BROADCAST_STICKY 允许应用程序广播粘性意图。这些广播的数据在完成后由系统保存，因此客户端可以快速检索该数据而无需等待下一次广播。
* CHANGE_NETWORK_STATE 允许应用程序更改网络连接状态。
* CHANGE_WIFI_MULTICAST_STATE 允许应用程序进入Wi-Fi多播模式。
* CHANGE_WIFI_STATE 允许应用程序更改Wi-Fi连接状态。
* DISABLE_KEYGUARD 允许应用程序在密钥保护不安全时禁用它。
* EXPAND_STATUS_BAR 允许应用程序展开或折叠状态栏。
* FOREGROUND_SERVICE 允许常规应用程序使用Service.startForeground。
* GET_PACKAGE_SIZE 允许应用程序查找任何包使用的空间。
* INSTALL_SHORTCUT 允许应用程序在Launcher中安装快捷方式。
* INTERNET 允许应用程序打开网络套接字。
* KILL_BACKGROUND_PROCESSES 允许应用程序调用 ActivityManager.killBackgroundProcesses(String)。
* MANAGE_OWN_CALLS 允许通过自我管理的ConnectionServiceAPI 管理自己调用的应用程序 。有关PhoneAccount.CAPABILITY_SELF_MANAGED自我管理的ConnectionService API的更多信息，请参阅 。
* MODIFY_AUDIO_SETTINGS 允许应用程序修改全局音频设置。
* NFC 允许应用程序通过NFC执行I / O操作。
* READ_SYNC_SETTINGS 允许应用程序读取同步设置。
* READ_SYNC_STATS 允许应用程序读取同步统计信息。
* RECEIVE_BOOT_COMPLETED 允许应用程序Intent.ACTION_BOOT_COMPLETED在系统完成引导后接收 广播。如果您未请求此权限，则您当时不会收到广播。虽然持有此权限不会产生任何安全隐患，但它会增加系统启动所需的时间并允许应用程序在用户不知道的情况下自行运行，从而对用户体验产生负面影响。因此，您必须明确声明您对此工具的使用，以使其对用户可见。
* REORDER_TASKS 允许应用程序更改任务的顺序。
* REQUEST_COMPANION_RUN_IN_BACKGROUND 允许随播应用在后台运行。
* REQUEST_COMPANION_USE_DATA_IN_BACKGROUND 允许配套应用在后台使用数据。
* REQUEST_DELETE_PACKAGES 允许应用程序请求删除包。定位API Build.VERSION_CODES.P或更高版本的应用必须拥有此权限才能使用Intent.ACTION_UNINSTALL_PACKAGE或 PackageInstaller.uninstall(VersionedPackage, IntentSender)。
* REQUEST_IGNORE_BATTERY_OPTIMIZATIONS 必须持有申请才能使用 Settings.ACTION_REQUEST_IGNORE_BATTERY_OPTIMIZATIONS。这是一个正常的权限：请求它的应用程序将始终被授予权限，而无需用户批准或查看它。
* SET_ALARM 允许应用程序广播Intent以为用户设置警报。
* SET_WALLPAPER 允许应用程序设置壁纸。
* SET_WALLPAPER_HINTS 允许应用程序设置壁纸提示。
* TRANSMIT_IR 允许使用设备的红外发射器（如果有）。
* USE_FINGERPRINT 允许应用使用指纹硬件。
* VIBRATE 允许访问振动器。
* WAKE_LOCK 允许使用PowerManager WakeLocks防止处理器休眠或屏幕变暗。
* WRITE_SYNC_SETTINGS 允许应用程序写入同步设置。

### 签名权限

系统会在安装时授予这些应用程序权限，但仅限于尝试使用权限的应用程序使用与定义权限的应用程序的签名证书相同的时候。

* BIND_ACCESSIBILITY_SERVICE 必须要求AccessibilityService，以确保只有系统可以绑定它。
* BIND_AUTOFILL_SERVICE 必须要求AutofillService，以确保只有系统可以绑定它。
* BIND_CARRIER_SERVICES 允许绑定到运营商应用程序中的服务的系统进程将具有此权限。运营商应用程序应使用此权限来保护仅允许系统绑定到的服务。
* BIND_CHOOSER_TARGET_SERVICE 必须要求ChooserTargetService，以确保只有系统可以绑定它。
* BIND_CONDITION_PROVIDER_SERVICE 必须要求ConditionProviderService，以确保只有系统可以绑定它。
* BIND_DEVICE_ADMIN 必须要求设备管理接收器，以确保只有系统可以与之交互。
* BIND_DREAM_SERVICE 必须要求DreamService来，以确保只有系统可以绑定它。
* BIND_INCALL_SERVICE 必须要求InCallService，以确保只有系统可以绑定它。
* BIND_INPUT_METHOD 必须要求InputMethodService，以确保只有系统可以绑定它。
* BIND_MIDI_DEVICE_SERVICE 必须要求必须要求MidiDeviceService，以确保只有系统可以绑定它。
* BIND_NFC_SERVICE 必须要求HostApduService或OffHostApduService，以确保只有系统可以绑定它。
* BIND_NOTIFICATION_LISTENER_SERVICE 必须要求NotificationListenerService来确保，以确保只有系统可以绑定它。
* BIND_PRINT_SERVICE  必须要求PrintService，以确保只有系统可以绑定它。
* BIND_SCREENING_SERVICE 必须要求CallScreeningService，以确保只有系统可以绑定它。
* BIND_TELECOM_CONNECTION_SERVICE 必须要求ConnectionService，以确保只有系统可以绑定它。
* BIND_TEXT_SERVICE 必须要求TextService（例如SpellCheckerService），以确保只有系统可以绑定它。
* BIND_TV_INPUT 必须要求TvInputService 来确保只有系统可以绑定它。
* BIND_VISUAL_VOICEMAIL_SERVICE 必须要求VisualVoicemailService，以确保只有系统可以绑定它。
* BIND_VOICE_INTERACTION 必须要求VoiceInteractionService，以确保只有系统可以绑定它。
* BIND_VPN_SERVICE 必须要求VpnService，以确保只有系统可以绑定它。
* BIND_VR_LISTENER_SERVICE 必须要求VrListenerService来确保，以确保只有系统可以绑定它。
* BIND_WALLPAPER 必须要求WallpaperService来确保，以确保只有系统可以绑定它。
* CLEAR_APP_CACHE 允许应用程序清除设备上所有已安装应用程序的缓存。
* MANAGE_DOCUMENTS 允许应用程序管理对文档的访问，通常作为文档选择器的一部分。此权限仅应由平台文档管理应用程序请求。此权限无法授予第三方应用。
* READ_VOICEMAIL 允许应用程序读取系统中的语音邮件。
* REQUEST_INSTALL_PACKAGES 允许应用程序请求安装包。定位API大于25的应用必须拥有此权限才能使用Intent.ACTION_INSTALL_PACKAGE。
* SYSTEM_ALERT_WINDOW 允许应用使用类型创建窗口 WindowManager.LayoutParams.TYPE_APPLICATION_OVERLAY，显示在所有其他应用之上。很少有应用程序应该使用此权限; 这些窗口用于与用户进行系统级交互。
* WRITE_SETTINGS 允许应用程序读取或写入系统设置。
* WRITE_VOICEMAIL 允许应用程序修改和删除系统中的现有语音邮件。

### 危险权限

危险权限涵盖应用程序需要涉及用户私人信息的数据或资源的区域，或者可能会影响用户存储的数据或其他应用程序的操作。例如，读取用户联系人的权限是一种危险的权限。如果应用要使用危险权限，必须提示用户在运行时授予权限。

| 权限组     | 解释                                                                                   | 权限                   | 解释                                                                                                                              |
| ---------- | -------------------------------------------------------------------------------------- | ---------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| CALENDAR   | 用于与用户日历相关的运行时权限。                                                       | READ_CALENDAR          | 允许应用程序读取用户的日历数据。                                                                                                  |
|            |                                                                                        | WRITE_CALENDAR         | 允许应用程序写入用户的日历数据。                                                                                                  |
| CALL_LOG   | 用于与电话功能相关联的权限。                                                           | READ_CALL_LOG          | 允许应用程序读取用户的通话记录。                                                                                                  |
|            |                                                                                        | WRITE_CALL_LOG         | 允许应用程序写入（但不读取）用户的呼叫日志数据。                                                                                  |
|            |                                                                                        | PROCESS_OUTGOING_CALLS | 允许应用程序查看拨出呼叫期间拨打的号码，并选择将呼叫重定向到其他号码或完全中止呼叫。                                              |
| CAMERA     | 用于与访问摄像头或从设备捕获图像/视频相关联的权限                                      | CAMERA                 | 必须能够访问相机设备。                                                                                                            |
| CONTACTS   | 用于与此设备上的联系人和配置文件相关的运行时权限。                                     | READ_CONTACTS          | 允许应用程序读取用户的通话记录。                                                                                                  |
|            |                                                                                        | WRITE_CONTACTS         | 允许应用程序写入（但不读取）用户的呼叫日志数据。                                                                                  |
|            |                                                                                        | GET_ACCOUNTS           | 允许访问“帐户服务”中的帐户列表。                                                                                                |
| LOCATION   | 用于允许访问设备位置的权限。                                                           | ACCESS_FINE_LOCATION   | 允许应用访问精确位置。                                                                                                            |
|            |                                                                                        | ACCESS_COARSE_LOCATION | 允许应用访问精确位置。                                                                                                            |
| MICROPHONE | 用于与从设备访问麦克风音频相关联的权限。                                               | RECORD_AUDIO           | 允许应用程序录制音频。                                                                                                            |
| PHONE      | 用于与电话功能相关联的权限。                                                           | READ_PHONE_STATE       | 允许只读访问电话状态，包括设备的电话号码，当前的蜂窝网络信息，任何正在进行的呼叫的状态以及PhoneAccount在设备上注册的任何的列表 。 |
|            |                                                                                        | READ_PHONE_NUMBERS     | 允许读取设备的电话号码。                                                                                                          |
|            |                                                                                        | CALL_PHONE             | 允许应用程序在不通过拨号器用户界面的情况下发起电话呼叫，以便用户确认呼叫。                                                        |
|            |                                                                                        | ANSWER_PHONE_CALLS     | 允许该应用接听来电。                                                                                                              |
|            |                                                                                        | ADD_VOICEMAIL          | 允许应用程序将语音邮件添加到系统中。                                                                                              |
|            |                                                                                        | USE_SIP                | 允许应用程序使用SIP服务。                                                                                                         |
| SENSORS    | 用于与访问正文或环境传感器相关联的权限。                                               | BODY_SENSORS           | 允许应用程序访问用户用来测量身体内部情况的传感器数据，例如心率。                                                                  |
| SMS        | 用于与用户的SMS消息相关的运行时权限。                                                  | SEND_SMS               | 允许应用程序发送SMS消息。                                                                                                         |
|            |                                                                                        | RECEIVE_SMS            | 允许应用程序接收SMS消息。                                                                                                         |
|            |                                                                                        | READ_SMS               | 允许应用程序读取SMS消息。                                                                                                         |
|            |                                                                                        | RECEIVE_WAP_PUSH       | 允许应用程序接收WAP推送消息。                                                                                                     |
|            |                                                                                        | RECEIVE_MMS            | 允许应用程序监控传入的MMS消息。                                                                                                   |
| STORAGE    | 用于与存储相关的运行时权限   （此常量在API级别Q中已弃用。由Q中新的强类型权限组替换。） | READ_EXTERNAL_STORAGE  | 允许应用程序读取手机存储。                                                                                                        |
|            |                                                                                        | WRITE_EXTERNAL_STORAGE | 允许应用程序写入手机存储。                                                                                                        |

### 特殊权限

有一些权限不像正常和危险的权限，它们特别敏感，所以大多数应用程序不应该使用它们。如果应用程序需要其中一个权限，则必须在清单中声明权限，并发送请求用户授权的意图。系统通过向用户显示详细的管理屏幕来响应意图。

* SYSTEM_ALERT_WINDOW 如果应用面向API级别23或更高级别，则应用用户必须通过权限管理屏幕向应用明确授予此权限。该应用程序通过发送具有操作的意图来请求用户的批准 Settings.ACTION_MANAGE_OVERLAY_PERMISSION。该应用程序可以通过调用来检查它是否具有此授权 Settings.canDrawOverlays()。
* WRITE_SETTINGS 如果应用面向API级别23或更高级别，则应用用户必须通过权限管理屏幕向应用明确授予此权限。该应用程序通过发送具有操作的意图来请求用户的批准 Settings.ACTION_MANAGE_WRITE_SETTINGS。该应用程序可以通过调用来检查它是否具有此授权Settings.System.canWrite()。

## 权限执行

权限不仅适用于请求系统功能。应用程序提供的服务可以强制执行自定义权限，以限制谁可以使用它们。

### Activity权限执行

使用android:permission属性对清单中的标记应用的权限限制了谁可以启动它。

### Service权限执行

使用android:permission属性对清单中的标记应用的权限限制谁可以启动或绑定到关联的。

### Broadcast权限执行

使用该android:permission属性对标记应用的权限限制了谁可以向关联的广播发送广播。

### Content Provider权限执行

使用该android:permission属性对标记应用的权限限制了谁可以访问数据 。

### URI权限执行

当与Content Provider一起使用时，到目前为止描述的标准许可系统通常是不够的。内容提供商可能希望使用读取和写入权限来保护自己，而其直接客户端还需要将特定URI交给其他应用程序以供其操作。
一个典型的例子是电子邮件应用程序中的附件。应该通过权限来保护对电子邮件的访问，因为这是敏感的用户数据。但是，如果向图像查看器提供图像附件的URI，则该图像查看器不再具有打开附件的权限，因为它没有理由拥有访问所有电子邮件的权限。
要构建最安全的实现，使其他应用程序对您的应用程序内的操作负责，应该以这种方式使用细粒度权限，并使用属性或标记声明您的应用程序对它的支持。

```android:grantUriPermissions
android:grantUriPermissions<grant-uri-permissions>
```

### 其他权限执行

任何对服务的调用都可以强制执行任意细粒度的权限。
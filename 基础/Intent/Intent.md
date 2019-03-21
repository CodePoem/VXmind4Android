# Intent

## 用途

Intent 是一个消息传递对象，可以通过多种方式促进组件之间的通信。

### 启动Activity

* startActivity()
* startActivityForResult()
* onActivityResult()

### 启动服务

* startService()
* bindService()

### 传递广播

* sendBroadcast()
* sendOrderedBroadcast()
* sendStickyBroadcast()

## 类型

### 显式Intent

按名称（完全限定类名）指定要启动的组件。 通常，您会在自己的应用中使用显式 Intent 来启动组件，这是因为您知道要启动的 Activity 或服务的类名。例如，启动新 Activity 以响应用户操作，或者启动服务以在后台下载文件。

### 隐式Intent

不会指定特定的组件，而是声明要执行的常规操作，从而允许其他应用中的组件来处理它。 例如，如需在地图上向用户显示位置，则可以使用隐式 Intent，请求另一具有此功能的应用在地图上显示指定的位置。

## Intent 过滤器

### \<intent-filter\>

#### \<action\>

```<action>
<intent-filter>
    <action android:name="android.intent.action.EDIT" />
    <action android:name="android.intent.action.VIEW" />
    ...
</intent-filter>
```

* Intent 中指定的操作必须与过滤器中列出的某一操作匹配才能通过行为匹配。
* 如果过滤器未列出任何行为，则 Intent 没有任何匹配项，因此所有 Intent 均无法通过行为测试。
* 如果 Intent 未指定操作，则会通过行为测试（只要过滤器至少包含一个行为）。

#### \<category\>

```<category>
<intent-filter>
    <category android:name="android.intent.category.DEFAULT" />
    <category android:name="android.intent.category.BROWSABLE" />
    ...
</intent-filter>
```

* Intent中 的每个类别均必须在过滤器中的类别中存在才能通过类别匹配。
* 无需完全一对一匹配，Intent 过滤器声明的类别可以超出 Intent 中指定的数量。
* 不含类别的 Intent 无论过滤器中声明何种类别始终会通过匹配。
* Android 会自动将 CATEGORY_DEFAULT 类别应用于传递给 startActivity() 和 startActivityForResult() 的所有隐式 Intent。因此，如需 Activity 接收隐式 Intent，则必须将 "android.intent.category.DEFAULT" 的类别包括在其 Intent 过滤器中。

#### \<data\>

```<data>
<intent-filter>
    <data android:mimeType="video/mpeg" android:scheme="http" ... />
    <data android:mimeType="audio/mpeg" android:scheme="http" ... />
    ...
</intent-filter>
```

每个 \<data\> 元素均可指定 URI 结构和数据类型（MIME 媒体类型）。

1. 仅当过滤器未指定任何 URI 或 MIME 类型时，不含 URI 和 MIME 类型的 Intent 才会通过测试。
2. 对于包含 URI 但不含 MIME 类型（既未显式声明，也无法通过 URI 推断得出）的 Intent，仅当其 URI 与过滤器的 URI 格式匹配、且过滤器同样未指定 MIME 类型时，才会通过测试。
3. 仅当过滤器列出相同的 MIME 类型且未指定 URI 格式时，包含 MIME 类型、但不含 URI 的 Intent 才会通过测试。
4. 仅当 MIME 类型与过滤器中列出的类型匹配时，同时包含 URI 类型和 MIME 类型（通过显式声明，或可以通过 URI 推断得出）的 Intent 才会通过测试的 MIME 类型部分。 如果 Intent 的 URI 与过滤器中的 URI 匹配，或者如果 Intent 具有 content: 或 file: URI 且过滤器未指定 URI，则 Intent 会通过测试的 URI 部分。 换言之，如果过滤器只是列出 MIME 类型，则假定组件支持 content: 和 file: 数据。

##### URI

```URI结构
<scheme>://<host>:<port>/<path>
```

URI 的每个部分均包含单独的 scheme、host、port 和 path 属性。例如：

```URI例子
content://com.example.project:200/folder/subfolder/etc
```

scheme是content，host是com.example.project，port是200，path是folder/subfolder/etc。
上述每个属性均为可选，但存在线性依赖关系：

* 如果未指定scheme，则会忽略host。
* 如果未指定host，则会忽略port。
* 如果未指定scheme和host，则会忽略path。

注：path规范可以包含星号通配符 (*)

##### MIME 媒体类型

MIME type的全称为"Multipurpose Internet Mail Extensions"代表互联网媒体类型(Internet media type)，MIME使用一个简单的字符串组成，最初是为了标识邮件Email附件的类型，在html文件中可以使用content-type属性表示，描述了文件类型的互联网标准。

标准的MIME Type格式：

``` 标准的MIME Type格式
type/subtype
```

例如image/jpeg、text/html等。

## Intent匹配

通过 Intent 过滤器匹配 Intent，这不仅有助于发现要激活的目标组件，还有助于发现设备上组件集的相关信息。 例如，主页应用通过使用指定 ACTION_MAIN 操作和 CATEGORY_LAUNCHER 类别的 Intent 过滤器查找所有 Activity，以此填充应用启动器。

可以采用类似的方式使用 Intent 匹配。PackageManager 提供了一整套 query...() 方法来返回所有能够接受特定 Intent 的组件。此外，它还提供了一系列类似的 resolve...() 方法来确定响应 Intent 的最佳组件。 例如，queryIntentActivities() 将返回能够执行那些作为参数传递的 Intent 的所有 Activity 列表，而 queryIntentServices() 则可返回类似的服务列表。这两种方法均不会激活组件，而只是列出能够响应的组件。 对于广播接收器，有一种类似的方法： queryBroadcastReceivers()。
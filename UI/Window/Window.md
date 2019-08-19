# Window

## WindowManager

### WindowManager.LayoutParams

#### flag

https://blog.csdn.net/zyjzyj2/article/details/53819964

#### type

http://www.cnblogs.com/olvo/archive/2012/05/17/2505776.html

##### System windows：

取值[2000,2999] 在 FIRST_SYSTEM_WINDOW 和 LAST_SYSTEM_WINDOW 之间。
用于特定的系统功能。它不能用于应用程序，使用时需要特殊权限。

##### Application Windows

取值在[1,99] FIRST_APPLICATION_WINDOW 和 LAST_APPLICATION_WINDOW 之间。
是通常的、顶层的应用程序窗口。必须将 token 设置成 activity 的 token 。

##### Sub_windows

取值[1000,1999]在 FIRST_SUB_WINDOW 和 LAST_SUB_WINDOW 之间。
与顶层窗口相关联，token 必须设置为它所附着的宿主窗口的 token。

## 系统内置应用实现

### PopupWindow

### Activity

### Dialog

### Toast

### Notification

## 其他应用实现

### 悬浮窗

#### 系统全局悬浮窗

#### 应用内悬浮窗
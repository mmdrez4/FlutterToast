
# [fluttertoast](https://pub.dartlang.org/packages/fluttertoast)  
  
Toast Library for Flutter

Now this toast library supports two kinds of toast messages one which requires `BuildContext` other with No `BuildContext`

## Toast with no context

> Supported Platforms
>
> - Android
> - IOS
> - Web (Uses [Toastify-JS](https://github.com/apvarun/toastify-js))

This one has limited features and no control over UI


## Toast Which requires BuildContext

> Supported Platforms  
>  
> - ALL

1. Full Control of the Toast
2. Toasts will be queued
3. Remove a toast
4. Clear the queue


## How to Use

```yaml
# add this line to your dependencies
fluttertoast: ^7.0.1
```

```dart
import 'package:fluttertoast/fluttertoast.dart';
```

## Toast with No Build Context

```dart
Fluttertoast.showToast(
        msg: "This is Center Short Toast",
        toastLength: Toast.LENGTH_SHORT,
        gravity: ToastGravity.CENTER,
        timeInSecForIosWeb: 1,
        backgroundColor: Colors.red,
        textColor: Colors.white,
        fontSize: 16.0
    );
```

| property        | description                                                        | default    |
| --------------- | ------------------------------------------------------------------ |------------|
| msg             | String (Not Null)(required)                                        |required    |
| toastLength     | Toast.LENGTH_SHORT or Toast.LENGTH_LONG (optional)                 |Toast.LENGTH_SHORT  |
| gravity         | ToastGravity.TOP (or) ToastGravity.CENTER (or) ToastGravity.BOTTOM (Web Only supports top, bottom) | ToastGravity.BOTTOM    |
| timeInSecForIosWeb | int (only for ios)                                                 | 1       |
| backgroundColor         | Colors.red                                                         |Colors.black    |
| textcolor       | Colors.white                                                       |Colors.white    |
| fontSize        | 16.0 (float)                                                       | 16.0       |
| webShowClose    | false (bool)                                                       | false      |
| webBgColor      | String (hex Color)                                                 | linear-gradient(to right, #00b09b, #96c93d) |
| webPosition     | String (`left`, `center` or `right`)                                | right     |

### To cancel all the toasts call

```dart
Fluttertoast.cancel()
```

### Custom Toast For Android

Create a file named `toast_custom.xml` in your project `app/res/layout` folder and do custom styling

```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="center_horizontal"
    android:layout_marginStart="50dp"
    android:background="@drawable/corner"
    android:layout_marginEnd="50dp">

    <TextView
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:background="#CC000000"
        android:paddingStart="16dp"
        android:paddingTop="10dp"
        android:paddingEnd="16dp"
        android:paddingBottom="10dp"
        android:textStyle="bold"
        android:textColor="#FFFFFF"
        tools:text="Toast should be short." />
</FrameLayout>
```

## Toast with BuildContext
  
```dart 
FToast fToast;

@override
void initState() {
    super.initState();
    fToast = FToast(context);
}

_showToast() {
    Widget toast = Container(
        padding: const EdgeInsets.symmetric(horizontal: 24.0, vertical: 12.0),
        decoration: BoxDecoration(
        borderRadius: BorderRadius.circular(25.0),
        color: Colors.greenAccent,
        ),
        child: Row(
        mainAxisSize: MainAxisSize.min,
        children: [
            Icon(Icons.check),
            SizedBox(
            width: 12.0,
            ),
            Text("This is a Custom Toast"),
        ],
        ),
    );


    fToast.showToast(
        child: toast,
        gravity: ToastGravity.BOTTOM,
        toastDuration: Duration(seconds: 2),
    );
}

```  

Now Call `_showToast()`

For more details check `example` project
  
| property        | description                                                        | default    |  
| --------------- | ------------------------------------------------------------------ |------------|  
| child             | Widget (Not Null)(required)                                        |required    |  
| toastDuration     | Duration (optional)                                                 |  |
| gravity         | ToastGravity.*    |  |
### To cancel all the toasts call  
  
```dart  
// To remove present shwoing toast
fToast.removeCustomToast()

// To clear the queue
fToast.removeQueuedCustomToasts();
```  

## Preview Images (No BuildContext)

<img src="https://raw.githubusercontent.com/ponnamkarthik/FlutterToast/master/screenshot/1.png" width="320px" />
<img src="https://raw.githubusercontent.com/ponnamkarthik/FlutterToast/master/screenshot/2.png" width="320px" />
<img src="https://raw.githubusercontent.com/ponnamkarthik/FlutterToast/master/screenshot/3.png" width="320px" />
<img src="https://raw.githubusercontent.com/ponnamkarthik/FlutterToast/master/screenshot/4.png" width="320px" />

## Preview Images (BuildContext)
  
<img src="https://raw.githubusercontent.com/ponnamkarthik/FlutterToast/master/screenshot/11.jpg" width="320px" />


## If you need any features suggest

...


## Buy Me a Coffee

<a href="https://www.buymeacoffee.com/karthikponnam" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>

# QRCode & Barcode Scanner

### Gradle


dependencies {
	implementation 'com.github.markusfisch:BarcodeScannerView:1.4.1'
}



## How to use

Add it to a layout:

```xml
<de.markusfisch.android.barcodescanerview.widget.BarcodeScannerView
	xmlns:android="http://schemas.android.com/apk/res/android"
	android:id="@+id/barcode_scanner"
	android:layout_width="match_parent"
	android:layout_height="match_parent"/>
```

Or create it programmatically:

```java
import de.markusfisch.android.barcodescanerview.widget.BarcodeScannerView;

BarcodeScannerView scannerView = new BarcodeScannerView(context);
```

Run `BarcodeScannerView.openAsync()`/`.close()` in `onResume()`/`onPause()`
of your activity or fragment:

```java
	@Override
	public void onResume() {
		super.onResume();
		scannerView.openAsync(BarcodeScannerView.findCameraId(
				Camera.CameraInfo.CAMERA_FACING_BACK));
	}

	@Override
	public void onPause() {
		super.onPause();
		scannerView.close();
	}
```




android.hardware.sensors@2.0 </br>
android.hardware.sensors@2.1

there are two path, one is the generic impl. of no multihal support, the another is multihal support, these two are tradd-off.


```shell
# source tree of ISensors 2.0/2.1

hardware/interfaces/sensors/2.0$ tree
	.
	├── default						// "android.hardware.sensors@2.0-service.mock"： executable 2.0 HIDL service (no multihal)
	│   ├── Android.bp
	│   ├── android.hardware.sensors@2.0-service-mock.rc
	│   ├── android.hardware.sensors@2.0.xml
	│   ├── OWNERS
	│   ├── SensorsV2_0.h
	│   └── service.cpp
	├── multihal						// "android.hardware.sensors@2.0-service.multihal"： executable 2.0 HIDL service (multihal)
	│   ├── Android.bp
	│   ├── android.hardware.sensors@2.0-multihal.xml
	│   ├── android.hardware.sensors@2.0-service-multihal.rc
	│   ├── OWNERS
	│   └── service.cpp
	└── vts
		└── ...
	├── Android.bp
	├── ISensorsCallback.hal
	├── ISensors.hal					//  "android.hardware.sensors@2.0"： 2.0 interface definition
	├── types.hal



hardware/interfaces/sensors/common/default/2.X$ tree

	├── multihal						// "android.hardware.sensors@2.X-multihal"： 2.X interface impl. static lib (multihal)
	│   ├── Android.bp
	│   ├── HalProxyCallback.cpp
	│   ├── HalProxy.cpp
	│   ├── include
	│   │   ├── HalProxyCallback.h
	│   │   ├── HalProxy.h
	│   │   ├── SubHalWrapper.h
	│   │   ├── V2_0
	│   │   │   ├── ScopedWakelock.h
	│   │   │   └── SubHal.h
	│   │   └── V2_1
	│   │       └── SubHal.h
	│   ├── ScopedWakelock.cpp
	│   └── tests
	│       ├── ...

	├── Android.bp						// "android.hardware.sensors@2.X-shared-impl"： 2.X interface impl. static lib (no multihal)
	├── OWNERS
	├── Sensor.cpp
	├── Sensor.h
	└── Sensors.h

```





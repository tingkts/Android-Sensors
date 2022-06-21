### Some porting notes

<br/>
<br/>

Common sensor driver implementation method ( Linux Kernel API )：
- input device
- hw monitor
- iio

<br/>
<br/>

NXP Sensors HAL (legacy HAL) :
- vendor/nxp-opensource/imx/libsensors
- vendor/nxp-opensource/imx/libsensors_sensorhub
- vendor/nxp-opensource/imx/iio_sensor


<br/>
<br/>

Android android.hardware.sensors@1.0 multihal

Source code :&emsp;[➚](./draw.io/android.hardware.sensors%401.0%20multihal.drawio.png)

|  module name   | source path  |
|  ----  | ----  |
| android.hardware.sensors@1.0-service <br/> android.hardware.sensors@1.0-impl.so  | [hardware/interfaces/sensors/1.0](https://cs.android.com/android/platform/superproject/+/android-11.0.0_r40:hardware/interfaces/sensors/1.0/) |
| multihal (static library)  | [hardware/libhardware/modules/sensors/multihal.cpp](https://cs.android.com/android/platform/superproject/+/android-11.0.0_r40:hardware/libhardware/modules/sensors/multihal.cpp) |


<br/>

To enable multihal :
- write the pure text file, [`hals.conf`](./hals.conf)
- build it into device path, `vendor/etc/sensors/hals.conf`



<br/>
<br/>

Misc.


Sensors type no. : [hardware/libhardware/include/hardware/sensors-base.](https://cs.android.com/android/platform/superproject/+/android-11.0.0_r40:hardware/libhardware/include/hardware/sensors-base.h)


<br/>
<br/>

Ref.

- [Sensors Multi-HAL | Android Open Source Project](https://www.google.com/url?client=internal-element-cse&cx=016258643462168859875:qqpm8fiwgc0&q=https://source.android.com/devices/sensors/sensors-multihal&sa=U&ved=2ahUKEwi1w7DWjb74AhUXCKYKHRuEBUQQFnoECAEQAQ&usg=AOvVaw1VJt8cmlNSLMPf6rb2aWMI)

<br/>
<br/>

<p align="right">base on imx8mp android 11 bsp</p>
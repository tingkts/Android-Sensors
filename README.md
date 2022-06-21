AOSP Documents ：

＃ AOSP :　https://source.android.com/docs/core/interaction/sensors

＃ Android Developers ：　https://developer.android.com/develop/sensors-and-location/sensors/sensors_overview

```
Key points:

Sensors can only report data from bottom to top,

From top to bottom, they can only:
• activate
• de-activate
• set sample rate
• set max report delay time

Moreover, Sensors operate independently, without interaction, and should not and cannot influence each other.
```

</br>
</br>


AOSP Stack ：

<img src="./AOSP%20Sensors%20SW%20stack.png" style="zoom:50%" />

</br>
</br>






[android.hardware.sensors@1.0](./android.hardware.sensors@1.0/README.md)

[android.hardware.sensors@2.0 / 2.1](./android.hardware.sensors@2.0%20@2.1/README.md)

[android.hardware.sensors / AIDL](./android.hardware.sensors%EF%BC%8FAIDL)


</br>
</br>

〈notes〉

SensorService has the only one instance of versioned Sensors HIDL service (1.0, else 2.0, else 2.1), so if multihal enabled, the vendor's specific sensors HAl should be implemented as the same version of Sensors HIDL Interface (1.0, else 2.0, else 2.1).


</br>



```
HIDL / AIDL services :


✨　Trade-off : Choose one of three, HIDL 1.0 / HIDL 2.0 2.1 / AIDL 1 2

     ------------------------------------------------------------------------------------------------------------------------------------------

       HIDL  1.0                                       is legacy : is passthrough : is the wrapper of libhardware/*/sensors

     ------------------------------------------------------------------------------------------------------------------------------------------

       HIDL  2.0                                       is new : is decouple of ibhardware/*/sensors : No longer relevant to ibhardware/*/sensors
             2.1       2.1 inherit 2.0

     ------------------------------------------------------------------------------------------------------------------------------------------

       AIDL  1                                         is new of Android 11 : the all new one
             2         2 almost the same as 1

     ------------------------------------------------------------------------------------------------------------------------------------------


✨　Trade-off : MultiHal v.s normal (single hal service)

```

</br>
</br>



<p align="right">Based on :　android 9　android 11　android 14</p>
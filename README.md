Overview

<img src="./AOSP%20Sensors%20SW%20stack.png" style="zoom:50%" />

</br>

[android.hardware.sensors@1.0](./android.hardware.sensors@1.0/README.md)

[android.hardware.sensors@2.0 / 2.1](./android.hardware.sensors@2.0%20@2.1/README.md)


</br>

〈notes〉
- SensorService has the only one instance of versioned Sensors HIDL service (1.0, else 2.0, else 2.1), so if multihal enabled, the vendor's specific sensors HAl should be implemented as the same version of Sensors HIDL Interface (1.0, else 2.0, else 2.1).
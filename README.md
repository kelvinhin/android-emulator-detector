#Android emulator detector

[![](https://jitpack.io/v/daiwei92/android-emulator-detector.svg)](https://jitpack.io/#framgia/android-emulator-detector) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Android%20emulator%20detector-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/3635)

Easy to detect android emulator

#### Last check: 22/02/2018
    - Checked on real devices in Device Farm (https://aws.amazon.com/device-farm/)
    - BlueStacks
    - Genymotion
    - Android Emulator 
    - Andy 46.2.207.0
    - MEmu play
    - Nox App Player
    - Koplayer
    - .....

#### Change logs
    - 1.4.0 : Update database & With Telephony function auto detect Telephony Support
    - 1.4.1 : Fixed Nox App Player not being detected
How to use
-------
Example:

```java
EmulatorDetector.with(this)
                .setCheckTelephony(true)
                .addPackageName("com.bluestacks")
                .setDebug(true)
                .detect(new EmulatorDetector.OnEmulatorDetectorListener() {
                    @Override
                    public void onResult(boolean isEmulator) {
                        
                    }
                });
```

- `setCheckTelephony` Check Imei, Operator network, Device ID...

	If `true` we need permission `android.permission.READ_PHONE_STATE`
- `setDebug` Show log

- `addPackageName` To add the package but only on VMs
- Add permission `android.permission.INTERNET` to detect Virtual Networking
- (New) Add permission `android.permission.READ_EXTERNAL_STORAGE` to detect some Nox files

Description
-------

To update the virtual machine device detection with highest accuracy, 
We are going to check periodically the virtual machine latest version and combine with the statistics that we experienced from our actual project.
 
Project have refered the idea of some other projects.

If there are problems, please notify us. Create issue [here] (https://github.com/framgia/android-emulator-detector/issues/new)

License
-------

    Copyright 2016 Framgia, Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

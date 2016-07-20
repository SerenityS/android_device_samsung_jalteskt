Device configuration for the Samsung S4 OCTA (Korean Varients Only)

Copyright (C) 2014-2016 The CyanogenMod Project

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

------------------------------------------------------------------

* Description

  This repository is for CM-13.0 on Samsung Galaxy S4 (jalte)

    THIS IS WORK IN PROGRESS.


* How To Build CM-13.0 for Samsung Galaxy S4

  - Make a workspace

  $ mkdir -p ~/cyanogenmod/system
  $ cd ~/cyanogenmod/system


  - Do repo init & sync

  $ repo init -u git://github.com/CyanogenMod/android.git -b cm-13.0


  - Create .repo/local_manifests/roomservice.xml with the following content:

  <?xml version="1.0" encoding="UTF-8"?>
  <manifest>
      <project name="CyanogenMod/android_packages_apps_SamsungServiceMode" path="packages/apps/SamsungServiceMode" remote="github" />
      <project name="CyanogenMod/android_hardware_samsung" path="hardware/samsung" remote="github" />

      <project name="CyanogenMod/android_hardware_samsung_slsi-cm_exynos" path="hardware/samsung_slsi-cm/exynos" />
      <project name="CyanogenMod/android_hardware_samsung_slsi-cm_exynos5" path="hardware/samsung_slsi-cm/exynos5" />
      <project name="CyanogenMod/android_hardware_samsung_slsi-cm_openmax" path="hardware/samsung_slsi-cm/openmax" />
      <project name="SerenityS/android_hardware_samsung_slsi_exynos5410" path="hardware/samsung_slsi-cm/exynos5410" remote="github" />

      <project name="SerenityS/android_kernel_samsung_exynos5410.git" path="kernel/samsung/exynos5410" remote="github" />
      <project name="SerenityS/android_device_samsung_jalteskt.git" path="device/samsung/jalteskt" remote="github" />
      <project name="SerenityS/android_vendor_samsung_jalteskt.git" path="vendor/samsung/jalteskt" remote="github" />
  </manifest>

  $ repo sync

  - Setup environment

  $ source build/envsetup.sh
  $ lunch cm_jalteskt-userdebug


  - Build CM

  $ export USE_CCACHE=1
  $ make -j10 bacon

----
EOF

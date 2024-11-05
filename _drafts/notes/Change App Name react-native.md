---
title: Change App Name react-native
Description: Change App Name react-native
author: admin
date: 2024-10-24 18:26:13 +0700
categories: [Notes]
tags: [react-native]
---

> Halaman ini akan di update seiring ada perubahan pada catatan yang saya buat
{: .prompt-info }

# Change App Name react-native

1. `App.json`
   
   ```json
   {
    "name": "SomethingSomething",
    "displayName": "My New App Name"
   }
   ```

2. `Strings.xml` <Android>
   
   ```xml
   <string name="app_name">My New App Name</string>
   ```

3. `info.plist` <Ios>
   
   ```xml
   <key>CFBundleDisplayName</key>
   <string>My New App Name</string>
   ```

4. <Mark>Clean & Rebuild</Mark>
   
   ```bash
   cd android
   ./gradlew clean
   cd ..
   react-native run-android
   ```

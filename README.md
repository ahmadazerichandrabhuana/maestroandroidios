# Test Automation for Android Apps and iOS Apps using Maestro by mobile.dev

This is a sample of Test Automation for Android Apps (Real Device and Emulator) and iOS Apps (ony iOS Simulator) using [Maestro by mobile.dev](https://maestro.mobile.dev/).

## Requirements

1. Install [VS Code](https://code.visualstudio.com/) or any Code Editor you're comfort with.
5. Install [JDK](https://www.oracle.com/java/technologies/downloads/).
6. Install [Android Studio](https://developer.android.com/studio/install), and install Android SDK using Android Studio.
7. Update JAVA_HOME and ANDROID_HOME to your PATH file. There is no easy way to explain this. You can refer [here](https://medium.com/@zorozeri/setting-up-java-home-5abae0118bfe) or Google it.
4. Install [Allure Report](https://allurereport.org/docs/install/).
7. Install [XCode](https://apps.apple.com/us/app/xcode/id497799835?mt=12), and XCode Command Line Tools (`xcode-select --install`).
11. Download and install this [Demo Apps](https://github.com/saucelabs/my-demo-app-rn/releases), `.apk` file for Android Device / Android Emulator, or extract the `.zip` file and put the extracted `.app` file into iOS Simulator. Credit to [Wim Selles](https://github.com/wswebcreation).

## Run Tests
There are 2 types of Report for Test Execution using Maestro : html and junit.

* Run Android Tests with Html Report : 
   ```
   maestro test android/tests --format html
   ```

* Run Android Test with junit Report : 
   ```
   maestro test android/tests --format junit --output allure-results/report.xml
   ```
   
* Run iOS Tests with Html Report : 
   ```
   maestro test ios/tests --format html
   ```

* Run iOS Test with junit Report : 
   ```
   maestro test ios/tests --format junit --output allure-results/report.xml
   ```

Make sure to disconnect the unused device and then connect the desired device to run the targeted test types. Or, if you want to run it on specific device, add extra param `--device {udid}` after the keyword `maestro`. For example : 
   ```
   maestro --device your_android_udid test ios/tests --format html
   ```

## Open HTML Report
    open report.html
   Or just drag and drop file `report.html` into your Browser.

## Open Allure Report
*  Generate report file and open it :

   ```
   allure generate --clean && allure open
   ```
*  Open report without generating report file :

   ```
   allure serve
   ```
*  Troubleshoot Allure not recognized on PowerShell Windows :
   - Use Command Prompt instead of PowerShell, or
   - Run this command on PowerShell : 
     ```
     npm install -g allure-commandline --save-dev
     ```

## Short Repository Explanation

This sample Test Automation consists of 2 main folders : `android` and `ios`. Each of them have same folder structure :

* pages
   ```
   Contains web element for each specific web pages, aka implementing Page Object Pattern
   ```
* tests
   ```
   Contains test cases
   ```


## Maestro Keywords Commands Documentation

https://maestro.mobile.dev/api-reference/commands

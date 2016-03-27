# Appium

## Xcode
Download the latest version of Xcode from the App Store.

After installing Xcode download all its simulators:

* Open Xcode program
* Click on “Xcode” button at top left side of the screen
* Click the “Preferences…” button
* Download all simulators from “Downloads” window that will appear
* Also download “Command Line Tools”, otherwise Appium will not work.

## Android SDK

### Installation

Make sure you have [Homebrew](http://brew.sh/) installed.

#### Install Android SDK using brew

Install android-studio

```
brew install android-sdk
```

### Configuration

Add `ANDROID_HOME` to your `.bash_profile`
```
export ANDROID_HOME=/usr/local/opt/android-sdk      # Set it to the Android SDK path on your machine.
```

Open SDK Manager
```
android
```

Install all the defaults and in addition install the following:

* Extras -> Google Web Driver
* Extras -> Intel x86 Emulator Accelerator (HAXM Installer)
* Create Android Virtual Device (AVD)

### Creation of Virtual Device

These instructions are specifically for the Samsung Galaxy Tab. Add other device specific instructions similarly.

Open AVD

```
android avd
```

* Click on Device Definitions tab and add a new device SM-T900.
* Now click on "Android Virtual Devices" and create a new virtual device "GalaxyTab".

Once the avd "GalaxyTab" is ready it can be used by the test scripts.

* Install Chrome App
* Download the Chrome APK from APK mirror.
* Start the AVD and install the APK
* Install appium commandline tools

```
emulator -avd GalaxyTab                                                 # Start the GalaxyTab emulator
# cd to the directory where you have downloaded the apk
adb install com.android.chrome-44.0.2403.133-240313311-minAPI21.apk     # Install the Chrome APK built for x86 and not arm.
```
In the emulator check that Chrome is installed and working properly.

## Appium

Download Appium from http://appium.io/

### Install appium commandline tools

```
brew install node      # get node.js

npm install -g appium  # get appium

npm install wd         # get webdriver

appium &               # start appium
```
Open the Appium app and click the Doctor button. It will perform a bunch of diagnostic steps and confirm your installation is good.

### Run emulator and appium

Use the following commands to run the emulator, if it hasn't been started already.

#### Run emulator

```
emulator -avd GalaxyTab     # Start the GalaxyTab emulator.
```

If you want to scale the emulator to fit your screen, pass the scale parameter. Change .5 to something that suits your screen better.

```
emulator -avd GalaxyTab -scale .5 # Start the GalaxyTab emulator.
```


#### Start appium from the commandline.

```
appium
```



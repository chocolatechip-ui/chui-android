# chui-android

This is a node command-line tool that enables you to create a hybrid app container for your ChocolateChip-UI app that you can import into Android Studio to compile as an Android app. This module works on both Mac and Windows, creating the correct paths for each platform.

##Installation

To install on Mac OS X, open your terminal and type:

```
sudo npm install -g chui-android
```

You will be asked for you password before it proceeds.

For Windows, just run this in the command prompt:

```
npm install -g chui-android
```


After that, this command-line tool will be available globally.


##Usage

It expects the following parameters:

- proj (the name of your project)
- user (your username on your computer)
- app (path to an existing ChUI Web app, otherwise it will create a default html page)
- icons (path of icons for the hybrid path)

Both `--app` and `--icons` are optional arguments. If you do not provide a path to a ChocolateChip-UI Web app for the `--app` argument, the Xcode project will be created with a default Web page. You can always drag and drop your ChococolateChip-UI app's resources to the project's Website folder later. Just make sure you app's file name is `index.html`. You will be replacing the default index.html file in the project.

The command is used as follows:

    chui-android --proj "Hamburger" --user "BongoBaby" --app /Users/bongobaby/Documents/hamburger --icons /Users/bongobaby/Desktop/hambuger-icons


By default it outputs the resulting files project to your desktop. If there is already a folder with the same name, the script will abort with a warning asking you to either delete the existing folder on the desktop, or change the name of the project you are trying to create. 

You can add the path for the ChocolateChip-UI Web app you wish to convert into a hybrid app by dragging its folder onto the terminal with a space after the argument `--app`. This will put its contents into the `Website` folder of the hybrid app. Similarly, if you have icons and launch screens ready, you can drag the folder with them after the argument with a space: `--icons`. If you do not provide a path for app icons, the command will create the files withdefaults. Xcode will alert you with warning messages about the missing icons, however this will not impede the ability to build the app and deloy to an iOS capable device for testing. 

After creating your project, you can import it into Android Studio and run it in the Android emulator or deploy directly to a tethered device. Just follow these steps:

First, to develop Android apps on the Mac or Windows, you will need to have [Java](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed. After than, you will need to install Google's [Android Studio](https://developer.android.com/sdk/index.html).

***Mac***

On the Mac do this: Open Android Studio. When the "Welcome to Android Studio" window opens, from the Quick Start menu choose: "Import project (Eclipse ADT, Gradle, etc.)". This will open a file browser which you can use to navigate to the folder created by the command-line tool. After selecting that folder, click "OK". Android Studio will then alert you that the Gradle settings are not configured for this project and if you would like to use the Gradle wrapper. Click "OK". Android Studio will then add in the Gradle resources. When it is done, you will see one more popup: "Language level changes will take effect on project reload. Would you like to reload the project now?". Click "Yes". To will reload your project. You are now ready to run your app. You have two choices: in the Android emulator or deploying to a tethered Android device. Please consult the [Android Studio documentation](https://developer.android.com/tools/help/index.html) if you are unfamiliar with doing this.

***Windows***

On Windows, open Android Studio. From the "File" menu choose "Import Project...". This will open the file browser. Navigate to you the project you created on your Desktop. Then click "OK". If you get a popup alert "Sync Android SDKS" regarding your paths, click "OK". This will adjust that problem. Afterwards you will get another dialog informing you that the Gradpe settings for this project are not configured yet. Click "OK". It will proceed to add the Gradles files to your project. When done, you will get a dialog alert informing you "Language level changes changes will take effect on project reload. Would you like to reload the project now?". Click "OK". You are now ready to run your project in either the emulator or deploy to a tethered device. Please consult the [Android Studio documentation](https://developer.android.com/tools/help/index.html) if you are unfamiliar with doing this.

**Icon Sizes**

When supplying icons for your project, make sure you have then in the following folders (note, all icons have the same name):

- drawable-hdpi/ic_launcher.png
- drawable-mdpi/ic_launcher.png
- drawable-xhdpi/ic_launcher.png
- drawable-xxhdpi/ic_launcher.png

Their dimensions should be as follows:


- drawable-hdpi 72x72
- drawable-mdpi 48x48
- drawable-xhdpi 96x96
- drawable-xxhdpi 144x144

With your icons with these sizes and each in their individual folder, drag the parent folder to the terminal window to add its path to the chui-android flag: `--icons `.
download flutter copy it to directory you want  

go to control panel environmental variables edit path to add a new location paste the path bin directory for flutter then press ok and open terminal and use flutter command then just install android studio and avd manager and plugins  

run flutter doctor environmental variables name it ANDROID_HOME add path of android sdk which is some where in app data now add a new path by editing path again create two new path %ANDROID_HOME%\tools than %ANDROID_HOME%\platform-tools  

Android adb tools 

When your downgrading use fastboot mode and make sure boot-loader unlock 

download android studio file and extract and copy to home directory the same process for pycharm and flutter and run sh file 

```bash
cd to home directory in terminal 

tar xf ~/Downloads/flutter_linux_v1.5.4-hotfix.2-stable.tar.xz 

do this for all tar file programs like pycharm, netbeans, etc ... 

set dev path 

sudo nano .bashrc 

Paste at end of file:              export PATH="$PATH:/home/jac/flutter/bin" 

cd flutter\bin\ then  ./flutter 

run command: flutter doctor --android-licenses 
```

install android studio and install plugins   

Command line tools installation 

https://developer.android.com/studio#downloads 

click on download options and scroll down and download tools 

extract to home directory open terminal and edit dev path 

edit dev path 

sudo nano .bashrc 

paste at end :   export PATH="$PATH:/home/jac/tools/bin" 

reopen terminal and type sdkmanager 

Setting up the emulator 

sdkmanager "system-images;android-28;google_apis_playstore;x86_64" 

sdkmanager "platform-tools" 

sdkmanager "build-tools;28.0.3" 

sdkmanager "platforms;android-28" 

sdkmanager "emulator" 

Accept licenses 

sdkmanager –licenses 

Creating Android Emulator 

avdmanager create avd -n pixel -k "system-images;android-28;google_apis_playstore;x86_64" -d 19 

Running emulator from Terminal with Audio 

emulator @pixel 

Running emulator from Terminal without Audio 

emulator -noaudio -avd pixel 

Install kvm (If necessary) 

sudo apt install qemu-kvm 

sudo adduser username kvm 

sudo chown username /dev/kvm


# Extension for Vscode 
aksharpatel47.vscode-flutter-helper  
Nash.awesome-flutter-snippets  
oscarcs.dart-syntax-highlighting-only  
Dart-Code.dart-code  
Dart-Code.flutter  
alexisvt.flutter-snippets  
localizely.flutter-int  
gmlewis-vscode.flutter-stylizer  
gornivv.vscode-flutter-files
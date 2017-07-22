---
title: ionic 2 개발 환경설정
category: ionic-2
order: 1
comments: true
# other options
---
###ionic 2 설치하기

일단 공식 document로 가보자
http://ionicframework.com/docs/intro/installation/

설치합시다!!
npm install -g ionic cordova

*node는 필수로 설치되어 있어야함

*mac에서 permission denied 메시지가 나와서 sudo로 설치

적당한 위치에 app 기본폴더 만들고 실행하기
#프로젝트만들기
#https://ionicframework.com/getting-started/
ionic start myFirstApp template_name
##template type
#tabs(default) : a simple 3 tab layout
#sidemenu: a layout with a swipable menu on the side
#blank: a bare starter with a single page
#super: starter project with over 14 ready to use page designs
#tutorial: a guided starter project


#생성한 프로젝트로 이동
cd myFirstApp

#실행하기(run on browser)
ionic serve
-에러[Error: Cannot find module 'reflect-metadata’]발행하는 경우
https://github.com/driftyco/ionic/issues/9689
node 버전 6.xx로 버전업하기!

플랫폼별 개발환경 만들기
플랫폼 관련 command
#프로젝트에 설치된 플랫폼 리스트 확인하기
cordova platform ls

#플랫폼별 요구사항 체크
cordova requirements

#프로젝트에 플랫폼 추가하기
 cordova platform add ios --save
cordova platform add android --save

iOS 개발환경 만들기
- app store에서 xcode 검색해서 설치하기
- iOS기기로 런치할 수 있는 개발 툴 설치
npm install -g ios-sim
npm install -g ios-deploy
-에러[xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance]나는 경우
http://frontend.diffthink.kr/2016/04/ios.html

xcode에서 preference->Locations command line tools 선택해주기!
- 참고하기
https://cordova.apache.org/docs/en/latest/guide/platforms/ios/

Android 개발환경 만들기
-android studio 설치하기
https://developer.android.com/studio/install.html
-ANDROID_HOME path설정하기
#mac에서 설정 
#~.bash_profile 파일에 설정하기
export ANDROID_HOME="/Users/username/Library/Android/sdk"
export ANDROID_TOOLS="/Users/username/Library/Android/sdk/tools"
export ANDROID_PLATFORM_TOOLS="/Users/username/Library/Android/sdk/platform-tools"
PATH=$PATH:$ANDROID_HOME:$ANDROID_TOOLS:$ANDROID_PLATFORM_TOOLS
-에러[Error: Could not find gradle wrapper within Android SDK. Might need to update your Android SDK.
Looked here: /Users/jiseob/Library/Android/sdk/tools/templates/gradle/wrapper]나는경우
https://forum.ionicframework.com/t/error-could-not-find-gradle-wrapper-within-android-sdk-might-need-to-update-yo-ur-android-sdk/22056/15
위 링크 참고해서 다운로드 받은 파일은 tools에 덮기
-에러[Error: android: Command failed with exit code 2]
에뮬레이터 실행해 놓고, 빌드하기
-참고하기
https://cordova.apache.org/docs/en/latest/guide/platforms/android/

cordova & ionic command
#특정 플랫폼으로 실행하기
cordova run ios
ionic run ios

#실제 디바이스에 설치하기 (debugging & developer mode 켜고 usb로 연결한 후 사용)
#https://developer.android.com/studio/run/device.html#developer-device-options
ionic run android --device

파일 
https://www.android.com/filetransfer/

borowser에서 실행하기
ionic serve 
ionic run browser

##위의 두 커맨드는 브라우저에서 실행되지만 네이티브 기능을 사용하려면 밑의 커맨드를 이용해야 함
#(plaform에 browser 추가 필요)
#https://github.com/driftyco/ionic-native/issues/403

#ionic serve runs your app as a website (meaning it doesn't have any Cordova capabilities)
#ionic run browser runs your app in the Cordova browser platform, which will inject cordova.jsand any plugins that have browser capabilities

iOS 시뮬레이션 디바이스에서 실행보기
#지원 시뮬레이션 디바이스 보기
ios-sim showdevicetypes

##결과목록
#iPhone-4s, 8.4
#iPhone-5, 8.4
#iPhone-5s, 8.4
#iPhone-6-Plus, 8.4
#iPhone-6, 8.4
#iPad-2, 8.4
#iPad-Retina, 8.4
#iPad-Air, 8.4
#Resizable-iPhone, 8.4
#Resizable-iPad, 8.4

#특정 타겟에서 실행하기
ionic run ios --target=iPhone-6

android 가상 디바이스에서 실행하기
#가상 디바이스 목록보기
adb devices

##결과목록
#emulator-5554   device

#특정 타겟에서 실행하기
ionic run android --target=emulator-5554


If you are using following devices:
Samsung S3 GT-I9305 (Android 4.1.2)
Mac OS 10.6.8
Do following:

# echo "0x04e8" >> ~/.android/adb_usb.ini
# adb kill-server
# adb devices
(if you are not using Samsung device, change the Vendor ID "0x04e8" to the correct value of your Vendor) 

If still not working, you may want to try following:

(1) On your Samsung device, disable "USB Debugging" and re-enable it again
(and try the adb commands again)
(2) Disconnect the USB cable, and re-connect it again

(3) Uninstall Samsung Kies

(4) Install Android File Transfer

(5) Reboot your Mac and the Samsung device

(6) Use hardware device to test your Android app 

After getting the devices connected but you suddenly unplug the USB cable, and suppose now "adb devices" cannot see your device any more, even after "adb kill-server", in this case, you may want to try the following:

(1) power off your Mac
(2) disable "USB debuggine" on your Samsung device
(3) power off your Samsung device
(4) power on your Mac
(5) power on your Samsung device
(6) enable "USB debuggine" on your Samsung device
(7) connect the USB cable
(8) Run "adb devices"
(9) You should see the attached device now
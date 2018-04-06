---
title: ionic 2 개발 환경설정
category: framework / library
kind : ionic 2
order: 1
comments: true
# other options
---

## 공식 document
http://ionicframework.com/docs/intro/installation/

## 설치
```sbtshell
# permission deny되는 경우 sudo로 설치해주세요
npm install -g ionic cordova
```

***node는 필수로 설치되어 있어야 합니다.*** 

## 프로젝트 생성 / 실행

```sbtshell
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
```

> 에러[Error: Cannot find module 'reflect-metadata’]발생하는 경우 node 버전 6.xx로 올려주세요.
> https://github.com/driftyco/ionic/issues/9689 

## 플랫폼별 개발환경 만들기

```sbtshell
#프로젝트에 설치된 플랫폼 리스트 확인하기
cordova platform ls

#플랫폼별 요구사항 체크
cordova requirements

#프로젝트에 플랫폼 추가하기
cordova platform add ios --save
cordova platform add android --save
```

### ios 개발환경 만들기

- app store에서 xcode 검색해서 설치하기
- iOS기기로 런치할 수 있는 개발 툴 설치
```sbtshell
npm install -g ios-sim
npm install -g ios-deploy
```

> 에러[xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance]나는 경우
> http://frontend.diffthink.kr/2016/04/ios.html

![ios_setting](/assets/ionic/ios_setting.png "ios 설정")

- xcode에서 preference -> Locations command line tools 선택
  - 참고 : https://cordova.apache.org/docs/en/latest/guide/platforms/ios/

### android 개발환경 만들기

1. android studio 설치하기 : https://developer.android.com/studio/install.html
2. ANDROID_HOME path 설정
```
#mac에서 설정 
#~.bash_profile 파일에 설정하기
export ANDROID_HOME="/Users/username/Library/Android/sdk"
export ANDROID_TOOLS="/Users/username/Library/Android/sdk/tools"
export ANDROID_PLATFORM_TOOLS="/Users/username/Library/Android/sdk/platform-tools"
PATH=$PATH:$ANDROID_HOME:$ANDROID_TOOLS:$ANDROID_PLATFORM_TOOLS
```
3. android 가상 디바이스에서 실행하기
```
# 가상 디바이스 목록보기
adb devices

# 결과목록
# emulator-5554   device

# 특정 타겟에서 실행하기
ionic run android --target=emulator-5554
```
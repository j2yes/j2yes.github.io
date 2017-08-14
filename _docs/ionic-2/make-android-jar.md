---
title: 안드로이드 apk 만들기
category: ionic-2
order: 2
comments: true
# other options
---

#### 릴리즈 버전 apk 파일 생성하기
> ionic cordova build android --release 

command를 입력하여 아래처럼 빌드결과가 출력됩니다.

```
.
.
.
:transformNative_libsWithMergeJniLibsForRelease
:processReleaseJavaRes UP-TO-DATE
:transformResourcesWithMergeJavaResForRelease
:packageRelease
:assembleRelease
:cdvBuildRelease

BUILD SUCCESSFUL

Total time: 22.868 secs
Built the following apk(s): 
        /workspace_path/platforms/android/build/outputs/apk/android-release-unsigned.apk

```

#### keystore 파일만들기
keystore를 만들 때 password를 물어보는데, 잘 저장해 두세요.
> keytool -genkey -v -keystore stroke-key.keystore -alias **its_my_sign_key** -keyalg RSA -keysize 2048 -validity 10000

#### 위에서 만든 릴리즈버전 apk를 sign하기
위에서 만든 릴리즈버전 apk에 아래 command로 sign을 해주자 (keystore 만들 때 지정한 password를 물어봅니다)
> jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore stroke-key.keystore android-release-unsigned.apk **its_my_sign_key**


#### jar align 하기
> ~/Library/Android/sdk/build-tools/25.0.2/zipalign -v 4 /Users/jiseob/Desktop/cordova/auction/android-release-unsigned.apk android-release-aligned.apk

최종 아웃풋 파일인 `android-release-aligned.apk`를 마켓에 업로드할 수 있어요.
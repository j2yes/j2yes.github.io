---
title: 안드로이드 apk 만들기
category: ionic-2
order: 2
comments: true
# other options
---

#### 릴리즈 버전 jar 파일 생성하기
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
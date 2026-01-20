f4b26b6a77e084ecbb5933b9fe8d1c5f

https://www.notion.so/teamsparta/Firebase-Authentication-Kakao-JWT-2e62dc3ef51480f6b57dd6f3492e7723

```sh
# 아래의 메시지가 콘솔에 뜬다면
# The operation couldn’t be completed. Unable to locate a Java Runtime.
# Please visit http://www.java.com for information on installing Java.
# 이 명령어 사용
# Mac
/Applications/Android\ Studio.app/Contents/jbr/Contents/Home/bin/keytool -exportcert -alias androiddebugkey -keystore ~/.android/debug.keystore -storepass android -keypass android | openssl sha1 -binary | openssl base64
# Windows CMD
"C:\Program Files\Android\Android Studio\jbr\bin\keytool.exe" -exportcert -alias androiddebugkey -keystore "%USERPROFILE%\.android\debug.keystore" -storepass android -keypass android | openssl sha1 -binary | openssl base64
# Windows CMD 에서 openssl 찾을 수 없다고 에러 뜨면
# Git Bash 에서 아래 명령어 입력
"/c/Program Files/Android/Android Studio/jbr/bin/keytool" -exportcert -alias androiddebugkey -keystore ~/.android/debug.keystore -storepass android -keypass android | openssl sha1 -binary | openssl base64

```

## Firestore 빌드 속도 빠르게 하기!

### 원인
- cloud_firestore 패키지를 설치 후 실행하면 iOS 네이티브 패키지가 설치됨
- iOS 네이티브 패키지는 C++이란 언어로 500,000줄 이상으로 작성됨
- 이 코드들을 기계어로 번역하는 과정이 매우 오래 걸렸었음!

### 해결방법
- https://github.com/invertase/firestore-ios-sdk-frameworks
- 위 레포지토리에서 이미 번역된 네이티브 패키지를 제공함
- 아래의 내용을 `Podfile` 에 `target 'RunnerTests' do` 위에 붙여넣기
    `pod 'FirebaseFirestore', :git => 'https://github.com/invertase/firestore-ios-sdk-frameworks.git', :tag => '10.19.0'`
- 실행하면 에러가 나는데 Firebase Core와 버전 맞춰주기
- 터미널에서 ios 폴더로 이동 후 `pod install --repo-update` 실행해서 패키지 업데이트하면서 받아오기!
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
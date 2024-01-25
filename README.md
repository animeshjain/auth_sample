# auth_sample

This is a sample app showing integration for sign in with google and apple id on android, ios and web.

The android debug build is using a debug keystore located in ~/.android/debug.keystore. The password for the keystore is `android`. 
The keystore is configured to have a single key with alias `androiddebugkey` and password `android`.

We can obtain the SHA1 fingerprint of the debug keystore using the following command:
```bash
keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android
```

Note: Adding this SHA1 fingerprint to the firebase project will allow the android app to make API calls to the
oauth apis using the firebase managed API Keys in cloud console.

Question: Can we just manually create OAuth credentials in cloud console without going through the firebase console?

I am worried that entering this in Firebase console might get firebase to start billing this as a user!

This blog post covers doing Google sign in setup without firebase:
https://medium.com/codebrew/flutter-google-sign-in-without-firebase-3680713966fb

In cloud console, consent screen has been setup.

Android setup:
- Create an oauth 2.0 client id for android (with the respective SHA1 fingerprint) in cloud console.
- `flutter pub add google_sign_in`
- and that's it! nothing needs to be changed in build.gradle

iOS setup:
- create an oauth 2.0 client id for iOS in cloud console
  - 174301737822-72tu3tjddb2t4681ittgrm5sro5a07vh.apps.googleusercontent.com


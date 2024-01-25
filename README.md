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


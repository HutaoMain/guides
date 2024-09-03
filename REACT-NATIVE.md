**how to create expo typescript**

```
npx create-expo-app -t expo-template-blank-typescript
```

**install this after you created expo app**

```
npm i react-native-gesture-handler react-native-screens react-native-safe-area-context
```

**main package of react-navigation**

```
npm install @react-navigation/native
```

**use to have bottom tabs**

```
@react-navigation/bottom-tabs
```

**use for stacking screen**

```
@react-navigation/native-stack
```

**use for drawer like draw navbar in the side of the screen**

```
@react-navigation/drawer
```

**use for top navbar**

```
@react-navigation/material-top-tabs react-native-tab-view
```

**Expo error: Could not determine the dependencies of task ‘:app:buildReleasePreBundle’.**

```
npx expo prebuild --clean
```

**Expo APK**

```
eas build -p android --profile preview
```

**REACT NATIVE CLI APK**

```
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res
```

```
cd android
```

```
./gradlew assembleDebug

```

**You will find your aab here**

```
yourProject/android/app/build/outputs/apk/debug/app-debug.apk
```

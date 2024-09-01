# React Native and Expo Setup Guide

## Expo TypeScript Setup

To create an Expo TypeScript project:

```bash
npx create-expo-app -t expo-template-blank-typescript
```

After creating the Expo app, install these additional packages:

```bash
npm i react-native-gesture-handler react-native-screens react-native-safe-area-context
```

## React Navigation Setup

Install the main package of react-navigation:

```bash
npm install @react-navigation/native
```

Additional navigation packages:

- For bottom tabs: `@react-navigation/bottom-tabs`
- For stacking screens: `@react-navigation/native-stack`
- For drawer navigation: `@react-navigation/drawer`
- For top navbar: `@react-navigation/material-top-tabs react-native-tab-view`

## Troubleshooting

If you encounter the Expo error: "Could not determine the dependencies of task ':app:buildReleasePreBundle'", run:

```bash
npx expo prebuild --clean
```

## Building APKs

### Expo APK

To build an APK with Expo:

```bash
eas build -p android --profile preview
```

### React Native CLI APK

To build an APK with React Native CLI:

```bash
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res
cd android
./gradlew assembleDebug
```

You will find your APK here:

```
yourProject/android/app/build/outputs/apk/debug/app-debug.apk
```

## REACT NATIVE CLI (WITHOUT FRAMEWORK)

To create a new React Native project without using Expo:

```bash
npx @react-native-community/cli@latest init AwesomeProject
```

### Important packages to install:

```bash
npm install react-native-screens react-native-safe-area-context
```

These two packages should be installed upon creation to avoid errors. They are crucial for navigation and layout management in React Native apps.

### Adding icons:

To add icons to your project, install:

```bash
npm install react-native-vector-icons
```

After installation, add this line to your `android/app/build.gradle` file:

```gradle
apply from: file("../../node_modules/react-native-vector-icons/fonts.gradle")
```

### Additional setup steps:

1. In your `index.js` or `App.js`, import and use the necessary components:

```javascript
import { SafeAreaProvider } from "react-native-safe-area-context";
import { enableScreens } from "react-native-screens";

enableScreens();

// Wrap your app's root component with SafeAreaProvider
function App() {
  return <SafeAreaProvider>{/* Your app content */}</SafeAreaProvider>;
}
```

2. For iOS, you need to install pods. Navigate to the iOS folder and run:

```bash
cd ios
pod install
```

3. If you're using TypeScript, you might need to install type definitions:

```bash
npm install --save-dev @types/react-native-vector-icons
```

4. To use the icons in your components:

```javascript
import Icon from "react-native-vector-icons/FontAwesome";

// In your component
<Icon name="rocket" size={30} color="#900" />;
```

Remember to link the assets when building for production. For Android, the step we added to `build.gradle` takes care of this. For iOS, you might need to manually add the fonts to your project's Info.plist file.

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

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

If you're using TypeScript, you might need to install type definitions:

```bash
npm install --save-dev @types/react-native-vector-icons
```

### Building an APK with React Native CLI:

1. Open Android Studio.
2. Clean and rebuild the project.
3. Run the following command in your terminal:

```bash
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res
```

4. In Android Studio, go to Build -> Build Bundle(s) / APK(s) -> Build APK(s).

You will find your APK here:

```
yourProject/android/app/build/outputs/apk/debug/app-debug.apk
```

### Building an AAB (Android App Bundle):

1. Follow steps 1-3 from the APK building process.
2. In Android Studio, go to Build -> Build Bundle(s) / APK(s) -> Build Bundle(s).

You will find your AAB here:

```
yourProject/android/app/build/outputs/bundle/debug/app-debug.aab
```

### Converting AAB to APK using Bundletool:

1. Download `bundletool.jar` from the official Google repository.
2. Place `bundletool.jar` and your `app-debug.aab` in the same directory.
3. Open PowerShell in that directory and run:

```powershell
java -jar bundletool.jar build-apks --bundle=app-debug.aab --output=android_app.apks --mode=universal
```

This command will create a universal APK from your AAB file.

### Additional Notes:

- Make sure you have Java Development Kit (JDK) installed on your system.
- The `bundletool` command creates a `.apks` file, which is actually a ZIP archive containing your APK. You can rename it to `.zip` and extract the APK from it.
- For production releases, you should sign your APK or AAB with your release key.
- Always test your APK on multiple devices or emulators before distribution.

# Camera Application

This is a simple Android application that opens the camera, allows the user to take a photo, and saves the photo to the device's storage. The photo is then added to the device's gallery and displayed in the application.

## Features

- Open the camera to take a photo.
- Save the photo to the device's external storage.
- Add the photo to the device's gallery.
- Display the captured photo in the application.

## Requirements

- Android Studio
- Android SDK
- Minimum SDK version: 21 (Android 5.0 Lollipop)

## Permissions

The application requires the following permissions:

- Camera
- Read External Storage
- Write External Storage

## Setup

1. **Clone the repository:**
    ```bash
    git clone https://github.com/your-repo/camera-application.git
    cd camera-application
    ```

2. **Open the project in Android Studio.**

3. **Update package name:**
   Ensure the package name in your project matches `com.example.cameraapplication`. If your package name is different, update it accordingly in the `file_paths.xml` and `MainActivity.java`.

4. **Add permissions:**
   Ensure the following permissions are added to your `AndroidManifest.xml`:
   ```xml
   <uses-permission android:name="android.permission.CAMERA" />
   <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
   <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
   ```

5. **Configure file provider:**
   Add the following provider configuration to your `AndroidManifest.xml`:
   ```xml
   <provider
       android:name="androidx.core.content.FileProvider"
       android:authorities="com.example.cameraapplication.provider"
       android:exported="false"
       android:grantUriPermissions="true">
       <meta-data
           android:name="android.support.FILE_PROVIDER_PATHS"
           android:resource="@xml/file_paths" />
   </provider>
   ```

6. **Create `file_paths.xml`:**
   Create a directory named `xml` under the `res` directory if it doesn't exist and add a file named `file_paths.xml` with the following content:
   ```xml
   <paths xmlns:android="http://schemas.android.com/apk/res/android">
       <external-path name="my_images" path="Android/data/com.example.cameraapplication/files/Pictures" />
   </paths>
   ```

## Usage

1. **Run the application:**
   Click on the "Run" button in Android Studio or use the following command:
   ```bash
   ./gradlew installDebug
   ```

2. **Take a photo:**
   - Click the "Take Photo" button to open the camera.
   - Capture the photo. The photo will be saved to the device's storage and added to the gallery.
   - The captured photo will be displayed in the application.

## Troubleshooting

- Ensure you have granted the necessary permissions when prompted.
- If the application crashes, check the logcat for error messages and ensure all file paths and permissions are correctly configured.




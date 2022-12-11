# Jetpack-compose

## Khái niệm
Jetpack Compose theo như Google định nghĩa thì nó là một bộ công cụ để xây dựng giao diện người dùng Android gốc. Jetpack Compose đơn giản hóa và tăng tốc phát triển giao diện người dùng trên Android với ít mã hơn, công cụ mạnh mẽ và API Kotlin trực quan. Đối với ai từng lập trình Flutter hoặc React Native thì sẽ dễ dàng hơn rất nhiều vì ý tưởng của compose cũng dựa trên việc thiết kế UI theo dạng cây.

## Cài đặt môi trường
Để dùng được tool kit này thì cài Android Studio Canary và Kotlin version là 1.4.0 trở lên.

Cấu hình trong file build.gradle:

Bạn cần đặt cấp API tối thiểu của ứng dụng thành 21 trở lên và bật Jetpack Compose trong tệp build.gradle

android {

    defaultConfig {
        ...
        minSdkVersion 21
    }

    buildFeatures {
        // Enables Jetpack Compose for this module
        compose true
    }
    ...

    // Set both the Java and Kotlin compilers to target Java 8.

    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }

    kotlinOptions {
        jvmTarget = "1.8"
        useIR = true
    }

    composeOptions {
        kotlinCompilerVersion '1.4.0'
        kotlinCompilerExtensionVersion '1.0.0-alpha05'
    }
}

và thêm Jetpack Compose phụ thuộc vào bộ công cụ trong build.gradle :

dependencies {

    implementation 'androidx.compose.ui:ui:1.0.0-alpha05'
    // Tooling support (Previews, etc.)
    implementation 'androidx.ui:ui-tooling:1.0.0-alpha05'
    // Foundation (Border, Background, Box, Image, Scroll, shapes, animations, etc.)
    implementation 'androidx.compose.foundation:foundation:1.0.0-alpha05'
    // Material Design
    implementation 'androidx.compose.material:material:1.0.0-alpha05'
    // Material design icons
    implementation 'androidx.compose.material:material-icons-core:1.0.0-alpha05'
    implementation 'androidx.compose.material:material-icons-extended:1.0.0-alpha05'
    // Integration with observables
    implementation 'androidx.compose.runtime:runtime-livedata:1.0.0-alpha05'
    implementation 'androidx.compose.runtime:runtime-rxjava2:1.0.0-alpha05'

    // UI Tests
    androidTestImplementation 'androidx.ui:ui-test:1.0.0-alpha05'
}

## Tạo project compose
Vào File > New > New Project và chọn Empty Compose Activity

https://images.viblo.asia/f8e79705-e6bc-4e03-8732-d024fd45e2f4.png

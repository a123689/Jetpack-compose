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

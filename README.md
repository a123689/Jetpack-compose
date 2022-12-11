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

![hihi](https://images.viblo.asia/f8e79705-e6bc-4e03-8732-d024fd45e2f4.png)

Trong MainActivity.kt sẽ hiển thị như sau:

![image2](https://images.viblo.asia/c9b06ffd-56f7-4162-a7b0-b17112348a0b.png)

## Các thành phần của jetpack compose

### @Composable

Jetpack compose được xây dựng xung quanh hàm composable. Đó là những function sẽ là nơi ta xác định UI và data của nó cũng tức là nơi ta thực hiện việc thêm các TextView hoặc các Button...

Thêm một phần tử Text.
setContent sẽ đóng vai trò như setContentView như trrong android gốc. Chỉ cần thêm một class Text và khai báo trong constructor của nó là xong 

 setContent {
 
    Text("Hello")
    
 }

![image3](https://images.viblo.asia/298bec56-4a85-46b7-aecd-e4da33e88d95.png)

# Khai báo hàm 
Thì nó cũng giống với việc khai báo như Android gốc nhưng nếu có chứa các phần tử UI thì phải khai báo thêm @Composable trước tên hàm.

Hàm bình thường.

fun Greetings(name: String) {

    return
}

Hàm có chứa UI.

@Composable
fun Greeting(name: String) {

    Text(text = "Hello $name!")
}


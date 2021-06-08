# last_prj

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

A: GIAO DIỆN

1: Đây là màn hình đăng nhập:

![7af9075bc713334d6a02](https://user-images.githubusercontent.com/62504531/121232545-ec126480-c8bb-11eb-820c-06d0b19df127.jpg)

2: Màn hình chính: Home

![home](https://user-images.githubusercontent.com/62504531/121235285-e36f5d80-c8be-11eb-8341-137c0dde57f8.jpg)

3: Màn hình tìm kiếm 'flower'

![d4e24903894b7d15245a](https://user-images.githubusercontent.com/62504531/121235324-eec28900-c8be-11eb-9cef-9012bb8908e9.jpg)




1. Gọi `WidgetsFlutterBinding.ensureInitialized();` trong main() trước khi gọi `runApp()`:

```dart
void main() {
  WidgetsFlutterBinding.ensureInitialized();
  runApp(MyApp());
}
```

2:Tạo hàm kết nối đến Firebase: Trước tiên cần import 2 package sau:
`import 'package:firebase_auth/firebase_auth.dart';`
`import 'package:firebase_core/firebase_core.dart';`

```dart
Future main() async{
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp();
  runApp(MyApp());
}
```

3: Tạo biến lưu user người dùng vào Firebase:
```dart
final user = FirebaseAuth.instance.currentUser;
```

4:Các màn hình: 

// đăng nhập hệ thống
```dart
visible: _status == EmailCardStatus.login,
```
// lấy mật khẩu:
```dart
visible: _status == EmailCardStatus.reset,
```

5: Lấy thông tin người dùng từ Firebase
```dart
final auth = FirebaseAuth.instance;
```

6: Tạo tài khoản mật khẩu nếu chưa có
```dart
  final _emailKey = GlobalKey<FormFieldState>();
  final _passwordKey = GlobalKey<FormFieldState>();
```

7: Api từ Flickr để lấy ảnh
```dart
final url = Uri.https(
      'www.flickr.com',
      'services/rest',
      {
        'api_key': '5a9d130758d8c0c27a501e3179ad02f4',
        'photo_id': widget.id,
        'method': 'flickr.photos.getInfo',
        'format': 'json',
        'nojsoncallback': '1',
      },
    );
```




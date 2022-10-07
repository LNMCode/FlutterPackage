- Lỗi null placeholder animation.
Flow: Khi ở list -> clicked vào một item -> back về lại => bắn ra exception.
- Cách fix hiện tại: 
+ Bước 1: Copy file fade_in_image.dart trong folder và bỏ vào project.
+ Bước 2: import class đó và nơi cần sử dụng như sau:
```
import 'package:namepackage/common/fade_in_image.dart' as FI;
```
=> sử dụng:
```
FI.FadeInImage.memoryNetwork(
      placeholder: placeholder.toBase64(),
      image: image,
      width: width,
      height: height,
      fit: BoxFit.cover,
    );
    ```

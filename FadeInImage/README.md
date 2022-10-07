- Lỗi null placeholder animation.
Flow: Khi ở list có sử dụng FadeInImage -> clicked vào một item -> back về lại => bắn ra exception.
- Nguyên nhân: lỗi này xuất hiện ở bản stable, flutter đã fix 28 ngày trước, nhưng chỉ merge và fix trên master chứ chưa fix trên stable.
- Cách fix hiện tại: 
+ Bước 1: Copy file fade_in_image.dart trong folder ở trên và bỏ vào project.
+ Bước 2: import class đó vào nơi cần sử dụng như sau:
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

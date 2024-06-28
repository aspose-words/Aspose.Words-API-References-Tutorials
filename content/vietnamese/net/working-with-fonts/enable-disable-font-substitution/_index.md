---
title: Bật Tắt thay thế phông chữ
linktitle: Bật Tắt thay thế phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, hãy tìm hiểu cách bật hoặc tắt tính năng thay thế phông chữ trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/enable-disable-font-substitution/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách bật hoặc tắt tính năng thay thế phông chữ trong tài liệu Word khi hiển thị nó bằng thư viện Aspose.Words cho .NET. Việc bật hoặc tắt tính năng thay thế phông chữ cho phép bạn kiểm soát xem các phông chữ bị thiếu có được tự động thay thế bằng phông chữ mặc định hay không. Chúng tôi sẽ hướng dẫn bạn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của mình.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn
- Tài liệu Word mà bạn muốn kết xuất có hoặc không có thay thế phông chữ

## Bước 1: Xác định thư mục tài liệu
 Trước tiên, bạn cần đặt đường dẫn thư mục đến vị trí tài liệu Word của mình. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu lên và định cấu hình cài đặt phông chữ
 Tiếp theo, chúng tôi sẽ tải tài liệu Word mà bạn muốn kết xuất và tạo một phiên bản của`FontSettings` class để xử lý các cài đặt phông chữ. Chúng tôi sẽ đặt ghi đè phông chữ mặc định bằng cách chỉ định tên phông chữ trong`DefaultFontName` và vô hiệu hóa ghi đè thông tin phông chữ bằng`Enabled` đặt thành`false`.

```csharp
// Tải tài liệu
Document doc = new Document(dataDir + "Rendering.docx");

// Định cấu hình cài đặt phông chữ
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Áp dụng cài đặt phông chữ cho tài liệu
doc.FontSettings = fontSettings;
```

## Bước 3: Lưu tài liệu được kết xuất
Cuối cùng, chúng ta sẽ lưu tài liệu được kết xuất, tài liệu này sẽ tuân theo các cài đặt ghi đè phông chữ đã xác định.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Mã nguồn mẫu cho Bật Tắt thay thế phông chữ bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã biết cách bật hoặc tắt tính năng thay thế phông chữ trong tài liệu Word khi hiển thị nó bằng Aspose.Words cho .NET. Bằng cách kiểm soát việc thay thế phông chữ, bạn có thể tác động đến cách xử lý phông chữ bị thiếu trong tài liệu được hiển thị của mình. Đừng ngần ngại sử dụng tính năng này để tùy chỉnh việc quản lý phông chữ trong tài liệu Word của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể bật tính năng thay thế phông chữ trong tài liệu Word bằng Aspose.Words?

Trả lời: Để bật tính năng thay thế phông chữ trong tài liệu Word bằng Aspose.Words, bạn có thể sử dụng API để chỉ định phông chữ thay thế sẽ sử dụng khi không có phông chữ được yêu cầu. Điều này sẽ đảm bảo hiển thị văn bản nhất quán, ngay cả khi không có phông chữ gốc.

#### Câu hỏi: Có thể tắt tính năng thay thế phông chữ trong tài liệu Word bằng Aspose.Words không?

Trả lời: Có, với Aspose.Words, bạn có thể tắt tính năng thay thế phông chữ trong tài liệu Word. Bằng cách sử dụng API, bạn có thể ngăn Word thay thế các phông chữ bắt buộc bằng các phông chữ khác, giúp duy trì hình thức ban đầu của văn bản.

#### Hỏi: Điều gì xảy ra khi thiếu phông chữ bắt buộc trong quá trình thay thế trong tài liệu Word?

Trả lời: Khi thiếu phông chữ bắt buộc trong quá trình thay thế trong tài liệu Word, Aspose.Words có thể phát hiện sự cố này và cung cấp cho bạn các tùy chọn để khắc phục. Bạn có thể chọn thay thế phông chữ bị thiếu bằng phông chữ thay thế hoặc đưa phông chữ bị thiếu vào tài liệu, đảm bảo xem chính xác.

#### Câu hỏi: Làm cách nào tôi có thể xử lý các phông chữ bị thiếu khi thay thế trong tài liệu Word bằng Aspose.Words?

Trả lời: Để xử lý các phông chữ bị thiếu khi thay thế trong tài liệu Word bằng Aspose.Words, bạn có thể sử dụng API để phát hiện các phông chữ bị thiếu và cung cấp các tùy chọn độ phân giải. Bạn có thể chọn thay thế phông chữ bị thiếu bằng phông chữ thay thế hoặc đưa phông chữ bị thiếu vào tài liệu, tùy theo nhu cầu của bạn.

#### Hỏi: Việc kiểm soát việc thay thế phông chữ trong tài liệu Word có quan trọng không?

Đáp: Có, điều quan trọng là phải kiểm soát việc thay thế phông chữ trong tài liệu Word để duy trì tính toàn vẹn hình ảnh của văn bản. Bằng cách sử dụng Aspose.Words để bật hoặc tắt tính năng thay thế phông chữ, bạn có thể đảm bảo rằng các phông chữ cần thiết được sử dụng và tránh các vấn đề về phông chữ bị thiếu hoặc bị thay thế.
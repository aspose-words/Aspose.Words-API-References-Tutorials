---
title: Đặt thư mục phông chữ đúng loại
linktitle: Đặt thư mục phông chữ đúng loại
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để đặt thư mục phông chữ đúng loại khi hiển thị tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-true-type-fonts-folder/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để đặt thư mục phông chữ đúng loại khi hiển thị tài liệu bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách chỉ định thư mục tùy chỉnh chứa phông chữ True Type để sử dụng khi hiển thị tài liệu của mình bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí bạn muốn lưu tài liệu được hiển thị đã chỉnh sửa của mình. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Load tài liệu cần render
 Tiếp theo, bạn cần tải tài liệu để kết xuất bằng cách sử dụng`Document` lớp học. Đảm bảo chỉ định đường dẫn tài liệu chính xác.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Đặt thư mục phông chữ True Type
Bây giờ bạn có thể chỉ định thư mục chứa các phông chữ đúng loại để sử dụng khi kết xuất bằng cách tạo một phiên bản của`FontSettings` lớp và sử dụng`SetFontsFolder()` phương pháp để thiết lập thư mục phông chữ. Bạn có thể chỉ định một thư mục tùy chỉnh chứa phông chữ True Type của mình. Tham số thứ hai để`SetFontsFolder()` cho biết bạn có muốn tìm kiếm các thư mục con của thư mục đã chỉ định hay không.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Bước 4: Lưu tài liệu được kết xuất
 Cuối cùng, bạn có thể lưu tài liệu được kết xuất vào một tệp bằng cách sử dụng`Save()` phương pháp của`Document` lớp học. Đảm bảo chỉ định đúng đường dẫn và tên tệp.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Mã nguồn mẫu cho Đặt thư mục phông chữ loại đúng bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Lưu ý rằng cài đặt này sẽ ghi đè mọi nguồn phông chữ mặc định đang được tìm kiếm theo mặc định. Bây giờ chỉ những thư mục này sẽ được tìm kiếm
// Phông chữ khi hiển thị hoặc nhúng phông chữ. Để thêm nguồn phông chữ bổ sung trong khi vẫn giữ nguồn phông chữ hệ thống, hãy sử dụng cả FontSettings.GetFontSources và
// Thay vào đó, FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Đặt cài đặt phông chữ
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt thư mục phông chữ đúng loại khi hiển thị tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng chỉ định thư mục tùy chỉnh chứa phông chữ True Type để sử dụng khi hiển thị tài liệu của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản với phông chữ trong tài liệu của bạn. Với kiến thức này, bạn có thể kiểm soát và tùy chỉnh các phông chữ được sử dụng khi hiển thị tài liệu theo nhu cầu cụ thể của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể định cấu hình thư mục phông chữ TrueType trong Aspose.Words?

 Trả lời: Để định cấu hình thư mục phông chữ TrueType trong Aspose.Words, bạn có thể sử dụng`SetTrueTypeFontsFolder` phương pháp của`Fonts` lớp chỉ định vị trí của thư mục chứa phông chữ TrueType.

#### Hỏi: Những loại phông chữ nào được coi là phông chữ TrueType?

Đáp: Phông chữ TrueType là định dạng phông chữ phổ biến. Chúng thường được sử dụng trong các tài liệu Word và có phần mở rộng tệp .ttf hoặc .ttc.

#### Câu hỏi: Tôi có thể chỉ định nhiều thư mục phông chữ TrueType trong Aspose.Words không?

Trả lời: Có, bạn có thể chỉ định nhiều thư mục phông chữ TrueType trong Aspose.Words bằng cách sử dụng`SetTrueTypeFontsFolder` phương pháp của`Fonts` class với danh sách các vị trí thư mục.

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra thư mục phông chữ TrueType được định cấu hình trong Aspose.Words?

 Trả lời: Để kiểm tra thư mục Phông chữ TrueType đã định cấu hình trong Aspose.Words, bạn có thể sử dụng`GetTrueTypeFontsFolder` phương pháp của`Fonts` class để lấy vị trí của thư mục Phông chữ TrueType được định cấu hình.

#### Hỏi: Tại sao việc định cấu hình thư mục phông chữ TrueType trong Aspose.Words lại quan trọng?

Trả lời: Việc thiết lập thư mục phông chữ TrueType trong Aspose.Words rất quan trọng vì nó giúp Aspose.Words xác định vị trí các phông chữ cần thiết khi xử lý tài liệu Word. Điều này đảm bảo tính nhất quán trong định dạng và hình thức tài liệu, thậm chí trên các hệ thống khác nhau.
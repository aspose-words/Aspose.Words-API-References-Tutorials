---
title: Đặt phông chữ thư mục Nhiều thư mục
linktitle: Đặt phông chữ thư mục Nhiều thư mục
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để đặt nhiều thư mục phông chữ khi hiển thị tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để đặt nhiều thư mục phông chữ khi hiển thị tài liệu bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Đến cuối hướng dẫn này, bạn sẽ biết cách chỉ định nhiều thư mục phông chữ để sử dụng khi hiển thị tài liệu của mình bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí bạn muốn lưu tài liệu được hiển thị đã chỉnh sửa của mình. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Load tài liệu cần render
 Sau đó, bạn có thể tải tài liệu để kết xuất bằng cách sử dụng`Document` lớp học. Đảm bảo chỉ định đường dẫn tài liệu chính xác.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Đặt thư mục phông chữ
 Bây giờ bạn có thể đặt nhiều thư mục phông chữ bằng cách sử dụng`FontSettings` lớp học và`SetFontsFolders()` phương pháp. Bạn có thể chỉ định đường dẫn đến thư mục phông chữ mà bạn muốn sử dụng trong một mảng. Trong ví dụ này, chúng tôi đã chỉ định hai thư mục phông chữ: "C:\MyFonts\" và "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Bước 4: Áp dụng cài đặt phông chữ
 Tiếp theo, bạn cần áp dụng cài đặt phông chữ cho tài liệu của mình bằng cách sử dụng`FontSettings` tài sản của`Document` lớp học.

```csharp
doc.FontSettings = fontSettings;
```

## Bước 5: Lưu tài liệu được kết xuất
 Cuối cùng, bạn có thể lưu tài liệu được kết xuất vào một tệp bằng cách sử dụng`Save()` phương pháp của`Document` lớp học. Đảm bảo chỉ định đúng đường dẫn và tên tệp.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Mã nguồn mẫu cho Đặt phông chữ thư mục nhiều thư mục bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Lưu ý rằng cài đặt này sẽ ghi đè mọi nguồn phông chữ mặc định đang được tìm kiếm theo mặc định. Bây giờ chỉ những thư mục này sẽ được tìm kiếm
// phông chữ khi hiển thị hoặc nhúng phông chữ. Để thêm nguồn phông chữ bổ sung trong khi vẫn giữ nguồn phông chữ hệ thống, hãy sử dụng cả FontSettings.GetFontSources và
// Thay vào đó, FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt nhiều thư mục phông chữ khi hiển thị tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng chỉ định nhiều thư mục phông chữ để sử dụng khi hiển thị tài liệu của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản với phông chữ trong tài liệu của bạn. Với kiến thức này, bạn có thể kiểm soát và tùy chỉnh các nguồn phông chữ được sử dụng khi hiển thị tài liệu theo nhu cầu cụ thể của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể đặt nhiều thư mục phông chữ trong Aspose.Words?

 Trả lời: Để đặt nhiều thư mục phông chữ trong Aspose.Words, bạn có thể sử dụng`SetFontsFolders` phương pháp của`Fonts` lớp cung cấp danh sách các vị trí thư mục phông chữ tùy chỉnh.

#### Câu hỏi: Việc đặt nhiều thư mục phông chữ có ảnh hưởng đến tất cả tài liệu được xử lý bằng Aspose.Words không?

Trả lời: Có, việc đặt nhiều thư mục phông chữ sẽ ảnh hưởng đến tất cả tài liệu được xử lý bằng Aspose.Words. Khi bạn đã xác định các thư mục phông chữ, Aspose.Words sẽ sử dụng các vị trí này để tìm kiếm phông chữ trong tất cả tài liệu.

#### Câu hỏi: Tôi có thể xác định bao nhiêu thư mục phông chữ trong Aspose.Words?

Trả lời: Bạn có thể xác định số lượng thư mục phông chữ nếu cần trong Aspose.Words. Không có giới hạn cụ thể về số lượng thư mục phông chữ bạn có thể xác định.

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra các thư mục phông chữ được xác định trong Aspose.Words?

 Trả lời: Để kiểm tra các thư mục phông chữ được xác định trong Aspose.Words, bạn có thể sử dụng`GetFolders` phương pháp của`Fonts` class để lấy vị trí của các thư mục phông chữ được cấu hình.

#### Câu hỏi: Các thư mục phông chữ có cần chứa các phông chữ cụ thể không?

Đáp: Có, thư mục phông chữ phải chứa phông chữ bạn muốn sử dụng trong tài liệu Word của mình. Aspose.Words sẽ tìm kiếm phông chữ trong các thư mục được chỉ định khi xử lý tài liệu.
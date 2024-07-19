---
title: Chỉ định phông chữ mặc định khi kết xuất
linktitle: Chỉ định phông chữ mặc định khi kết xuất
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để chỉ định phông chữ mặc định khi hiển thị tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/specify-default-font-when-rendering/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để chỉ định phông chữ mặc định khi hiển thị tài liệu bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Đến cuối hướng dẫn này, bạn sẽ biết cách chỉ định phông chữ mặc định để sử dụng khi hiển thị tài liệu của mình bằng Aspose.Words cho .NET.

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

## Bước 3: Đặt phông chữ mặc định
 Bây giờ bạn có thể chỉ định phông chữ mặc định để sử dụng khi hiển thị bằng cách tạo một phiên bản của`FontSettings` lớp và thiết lập`DefaultFontName` tài sản của`DefaultFontSubstitution` phản đối`DefaultFontSubstitution` sự vật`SubstitutionSettings` của`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Bước 4: Lưu tài liệu được kết xuất
 Cuối cùng, bạn có thể lưu tài liệu được kết xuất vào một tệp bằng cách sử dụng`Save()` phương pháp của`Document` lớp học. Đảm bảo chỉ định đúng đường dẫn và tên tệp.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Mã nguồn mẫu cho Chỉ định phông chữ mặc định khi kết xuất bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Nếu không thể tìm thấy phông chữ mặc định được xác định ở đây trong quá trình kết xuất thì
// thay vào đó, phông chữ gần nhất trên máy sẽ được sử dụng.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách chỉ định phông chữ mặc định khi hiển thị tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng đặt phông chữ mặc định để sử dụng khi hiển thị tài liệu của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản với phông chữ trong tài liệu của bạn. Với kiến thức này, bạn có thể kiểm soát và tùy chỉnh việc hiển thị tài liệu theo nhu cầu cụ thể của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể chỉ định phông chữ mặc định khi chuyển đổi sang PDF trong Aspose.Words?

 Trả lời: Để chỉ định phông chữ mặc định khi chuyển đổi sang PDF trong Aspose.Words, bạn có thể sử dụng`PdfOptions` lớp và thiết lập`DefaultFontName` thuộc tính thành tên của phông chữ mong muốn.

#### Hỏi: Điều gì sẽ xảy ra nếu phông chữ mặc định không có sẵn khi chuyển đổi sang PDF?

Trả lời: Nếu phông chữ mặc định được chỉ định không có sẵn khi chuyển đổi sang PDF, Aspose.Words sẽ sử dụng phông chữ thay thế để hiển thị văn bản trong tài liệu được chuyển đổi. Điều này có thể gây ra một chút khác biệt về hình thức so với phông chữ gốc.

#### Hỏi: Tôi có thể chỉ định phông chữ mặc định cho các định dạng đầu ra khác, chẳng hạn như DOCX hoặc HTML không?

Trả lời: Có, bạn có thể chỉ định phông chữ mặc định cho các định dạng đầu ra khác như DOCX hoặc HTML bằng cách sử dụng các tùy chọn chuyển đổi thích hợp và đặt thuộc tính tương ứng cho từng định dạng.

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra phông chữ mặc định được chỉ định trong Aspose.Words?

 Trả lời: Để kiểm tra phông chữ mặc định được chỉ định trong Aspose.Words, bạn có thể sử dụng`DefaultFontName` tài sản của`PdfOptions` class và lấy tên của phông chữ được cấu hình.

#### Hỏi: Có thể chỉ định phông chữ mặc định khác nhau cho từng phần của tài liệu không?

Đáp: Có, có thể chỉ định phông chữ mặc định khác nhau cho từng phần của tài liệu bằng cách sử dụng các tùy chọn định dạng dành riêng cho từng phần. Tuy nhiên, điều này sẽ yêu cầu thao tác tài liệu nâng cao hơn bằng cách sử dụng các tính năng Aspose.Words.
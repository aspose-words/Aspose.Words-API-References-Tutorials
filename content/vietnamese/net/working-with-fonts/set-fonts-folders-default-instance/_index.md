---
title: Đặt phiên bản mặc định của thư mục phông chữ
linktitle: Đặt phiên bản mặc định của thư mục phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để đặt thư mục phông chữ mặc định khi hiển thị tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folders-default-instance/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để đặt thư mục phông chữ mặc định khi hiển thị tài liệu bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách đặt thư mục phông chữ mặc định để sử dụng khi hiển thị tài liệu của mình bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí bạn muốn lưu tài liệu được hiển thị đã chỉnh sửa của mình. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Đặt thư mục phông chữ mặc định
 Sau đó, bạn có thể đặt thư mục phông chữ mặc định bằng cách sử dụng`FontSettings.DefaultInstance` lớp học và`SetFontsFolder()`phương pháp. Chỉ định đường dẫn đến thư mục phông chữ bạn muốn sử dụng làm thư mục mặc định.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Bước 3: Load tài liệu cần render
 Bây giờ bạn có thể tải tài liệu để kết xuất bằng cách sử dụng`Document` lớp học. Đảm bảo chỉ định đường dẫn tài liệu chính xác.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 4: Lưu tài liệu được kết xuất
 Cuối cùng, bạn có thể lưu tài liệu được kết xuất vào một tệp bằng cách sử dụng`Save()` phương pháp của`Document` lớp học. Đảm bảo chỉ định đúng đường dẫn và tên tệp.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Mã nguồn mẫu cho Đặt phiên bản mặc định của thư mục phông chữ bằng cách sử dụng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt thư mục phông chữ mặc định khi hiển thị tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng chỉ định thư mục phông chữ nào sẽ sử dụng làm thư mục mặc định khi hiển thị tài liệu của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản với phông chữ trong tài liệu của bạn. Với kiến thức này, bạn có thể kiểm soát và tùy chỉnh các nguồn phông chữ được sử dụng khi hiển thị tài liệu theo nhu cầu cụ thể của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể đặt thư mục phông chữ mặc định trong Aspose.Words?

 Trả lời: Để đặt thư mục phông chữ mặc định trong Aspose.Words, bạn phải sử dụng`Fonts` lớp học và`SetFontsFolders` phương pháp chỉ định vị trí thư mục phông chữ tùy chỉnh.

#### Câu hỏi: Việc đặt thư mục phông chữ mặc định có ảnh hưởng đến tất cả tài liệu Word được xử lý bằng Aspose.Words không?

Trả lời: Có, việc đặt thư mục phông chữ mặc định sẽ ảnh hưởng đến tất cả tài liệu Word được xử lý bằng Aspose.Words. Khi bạn đã đặt các thư mục phông chữ mặc định, Aspose.Words sẽ sử dụng các vị trí này để tìm kiếm phông chữ trong tất cả tài liệu.

#### Câu hỏi: Tôi có thể đặt nhiều thư mục phông chữ mặc định trong Aspose.Words không?

 Trả lời: Có, bạn có thể đặt nhiều thư mục phông chữ mặc định trong Aspose.Words. Bạn chỉ cần chỉ định vị trí của các thư mục phông chữ tùy chỉnh bằng cách sử dụng`SetFontsFolders` phương pháp của`Fonts` lớp học.

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra các thư mục phông chữ mặc định hiện được đặt trong Aspose.Words?

 Trả lời: Để kiểm tra các thư mục phông chữ mặc định hiện được xác định trong Aspose.Words, bạn có thể sử dụng`GetFolders` phương pháp của`Fonts` class để lấy vị trí của các thư mục phông chữ được cấu hình.

#### Hỏi: Việc đặt thư mục phông chữ mặc định có cho phép tôi sử dụng phông chữ tùy chỉnh trong tài liệu Word của mình không?

Trả lời: Có, bằng cách đặt thư mục phông chữ mặc định, bạn có thể sử dụng phông chữ tùy chỉnh trong tài liệu Word của mình. Bạn chỉ cần đặt phông chữ vào các thư mục được chỉ định và Aspose.Words sẽ sử dụng chúng khi tạo hoặc thao tác với tài liệu.
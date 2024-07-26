---
title: Đặt mức độ ưu tiên của thư mục phông chữ
linktitle: Đặt mức độ ưu tiên của thư mục phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để đặt mức độ ưu tiên của các thư mục phông chữ khi hiển thị tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folders-with-priority/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để đặt mức độ ưu tiên của các thư mục phông chữ khi hiển thị tài liệu bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách chỉ định nhiều thư mục phông chữ với mức độ ưu tiên tìm kiếm tùy chỉnh khi hiển thị tài liệu của mình bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí bạn muốn lưu tài liệu được hiển thị đã chỉnh sửa của mình. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Đặt mức độ ưu tiên của thư mục phông chữ
 Sau đó, bạn có thể đặt mức độ ưu tiên của các thư mục phông chữ bằng cách sử dụng`FontSettings` lớp học và`SetFontsSources()`phương pháp. Bạn có thể chỉ định nhiều nguồn phông chữ bằng cách sử dụng các phiên bản của`SystemFontSource`Và`FolderFontSource`. Trong ví dụ này, chúng tôi đã xác định hai nguồn phông chữ: nguồn phông chữ hệ thống mặc định và thư mục phông chữ tùy chỉnh có mức độ ưu tiên là 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Bước 3: Load tài liệu cần render
 Bây giờ bạn có thể tải tài liệu để kết xuất bằng cách sử dụng`Document` lớp học. Đảm bảo chỉ định đường dẫn tài liệu chính xác.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 4: Lưu tài liệu được kết xuất
 Cuối cùng, bạn có thể lưu tài liệu được kết xuất vào một tệp bằng cách sử dụng`Save()` phương pháp của`Document` lớp học. Đảm bảo chỉ định đúng đường dẫn và tên tệp.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Mã nguồn mẫu cho Đặt ưu tiên thư mục phông chữ bằng Aspose.Words cho .NET 
```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt mức độ ưu tiên của các thư mục phông chữ khi hiển thị tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng chỉ định nhiều thư mục phông chữ với mức độ ưu tiên tìm kiếm tùy chỉnh khi hiển thị tài liệu của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản với phông chữ trong tài liệu của bạn. Với kiến thức này, bạn có thể kiểm soát và tùy chỉnh các nguồn phông chữ được sử dụng khi hiển thị tài liệu theo nhu cầu cụ thể của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể đặt mức độ ưu tiên của các thư mục phông chữ trong Aspose.Words?

 Trả lời: Để đặt mức độ ưu tiên của các thư mục phông chữ trong Aspose.Words, bạn có thể sử dụng`SetFontsFoldersWithPriority` phương pháp của`Fonts` lớp bằng cách chỉ định vị trí thư mục phông chữ và thứ tự ưu tiên của chúng.

#### Hỏi: Điều gì sẽ xảy ra nếu một phông chữ xuất hiện trong một số thư mục có mức độ ưu tiên khác nhau?

Trả lời: Nếu một phông chữ xuất hiện trong nhiều thư mục có mức độ ưu tiên khác nhau, Aspose.Words sẽ sử dụng phiên bản từ thư mục có mức độ ưu tiên cao nhất khi xử lý tài liệu.

#### Câu hỏi: Tôi có thể chỉ định nhiều thư mục phông chữ có cùng mức độ ưu tiên trong Aspose.Words không?

Trả lời: Có, bạn có thể chỉ định nhiều thư mục phông chữ có cùng mức độ ưu tiên trong Aspose.Words. Aspose.Words sẽ xem xét tất cả chúng với mức độ ưu tiên như nhau khi tìm kiếm phông chữ trong tài liệu của bạn.

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra các thư mục phông chữ được xác định mức độ ưu tiên trong Aspose.Words?

 Trả lời: Để kiểm tra các thư mục phông chữ được xác định mức độ ưu tiên trong Aspose.Words, bạn có thể sử dụng`GetFolders` phương pháp của`Fonts` class để lấy danh sách các thư mục phông chữ được định cấu hình bao gồm thứ tự ưu tiên của chúng.

#### Câu hỏi: Việc đặt mức độ ưu tiên của thư mục phông chữ trong Aspose.Words có tác dụng gì?

Trả lời: Đặt mức độ ưu tiên của các thư mục phông chữ trong Aspose.Words cho phép bạn kiểm soát thứ tự tìm kiếm phông chữ trong tài liệu Word của mình. Điều này giúp bạn đảm bảo rằng phông chữ bạn muốn được sử dụng và tránh các sự cố thay thế phông chữ không mong muốn.
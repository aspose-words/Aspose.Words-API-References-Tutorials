---
title: Phiên bản mặc định của cài đặt phông chữ
linktitle: Phiên bản mặc định của cài đặt phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, hãy tìm hiểu cách định cấu hình cài đặt phông chữ mặc định trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/font-settings-default-instance/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách định cấu hình cài đặt phông chữ mặc định trong tài liệu Word bằng thư viện Aspose.Words cho .NET. Cài đặt phông chữ mặc định cho phép bạn chỉ định nguồn phông chữ được sử dụng khi tải và hiển thị tài liệu. Chúng tôi sẽ hướng dẫn bạn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của mình.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn

## Bước 1: Xác định thư mục tài liệu
 Trước tiên, bạn cần đặt đường dẫn thư mục đến vị trí tài liệu Word của mình. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Định cấu hình cài đặt phông chữ mặc định
 Tiếp theo, chúng ta sẽ tạo một thể hiện của`FontSettings` sử dụng`FontSettings.DefaultInstance`, sau đó chúng tôi sẽ chỉ định nguồn phông chữ được sử dụng khi tải và hiển thị tài liệu. Trong ví dụ này, chúng tôi đang sử dụng nguồn phông chữ hệ thống và nguồn phông chữ thư mục.

```csharp
// Định cấu hình cài đặt phông chữ mặc định
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Bước 3: Tải tài liệu lên với cài đặt phông chữ
 Bây giờ chúng ta sẽ tải tài liệu bằng cách sử dụng`LoadOptions` và chỉ định cài đặt phông chữ sẽ sử dụng.

```csharp
// Tải tài liệu với cài đặt phông chữ
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Mã nguồn mẫu cho Phiên bản mặc định của cài đặt phông chữ sử dụng Aspose.Words cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã biết cách định cấu hình cài đặt phông chữ mặc định trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách chỉ định nguồn phông chữ được sử dụng khi tải và hiển thị tài liệu, bạn có thể kiểm soát sự xuất hiện của phông chữ trong tài liệu của mình. Vui lòng sử dụng tính năng này để tùy chỉnh cài đặt phông chữ trong dự án của bạn.

### Câu hỏi thường gặp

#### Hỏi: Làm cách nào tôi có thể đặt phông chữ mặc định trong Aspose.Words?

 Trả lời: Để đặt phông chữ mặc định trong Aspose.Words, bạn có thể sử dụng`FontSettings` lớp học và`DefaultFontName` thuộc tính chỉ định tên của phông chữ mong muốn.

#### Câu hỏi: Tôi có thể chỉ định kích thước phông chữ mặc định trong Aspose.Words không?

 Trả lời: Có, bạn có thể chỉ định kích thước phông chữ mặc định trong Aspose.Words bằng cách sử dụng`DefaultFontSize` tài sản của`FontSettings` lớp học. Bạn có thể đặt kích thước điểm mong muốn.

#### Câu hỏi: Có thể đặt màu phông chữ mặc định trong Aspose.Words không?

 Trả lời: Có, bạn có thể đặt màu phông chữ mặc định trong Aspose.Words bằng cách sử dụng`DefaultColor` tài sản của`FontSettings` lớp học. Bạn có thể chỉ định màu bằng cách sử dụng giá trị RGB hoặc tên được xác định trước.

#### Hỏi: Cài đặt phông chữ mặc định có áp dụng cho tất cả tài liệu không?

Trả lời: Có, cài đặt phông chữ mặc định áp dụng cho tất cả tài liệu được tạo hoặc chỉnh sửa trong Aspose.Words, trừ khi cài đặt cụ thể được đặt cho từng tài liệu.
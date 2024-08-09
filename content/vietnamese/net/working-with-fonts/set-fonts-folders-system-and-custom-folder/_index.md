---
title: Đặt hệ thống thư mục phông chữ và thư mục tùy chỉnh
linktitle: Đặt hệ thống thư mục phông chữ và thư mục tùy chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt thư mục phông chữ hệ thống và tùy chỉnh trong tài liệu Word bằng Aspose.Words cho .NET, đảm bảo tài liệu của bạn hiển thị chính xác trên các môi trường khác nhau.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Giới thiệu

Hãy tưởng tượng bạn đang tạo một tài liệu với kiểu phông chữ độc đáo, nhưng rồi phát hiện ra rằng phông chữ không hiển thị chính xác trên một máy khác. Thật khó chịu phải không? Đây là lúc việc cấu hình các thư mục phông chữ phát huy tác dụng. Với Aspose.Words cho .NET, bạn có thể xác định các thư mục phông chữ hệ thống và tùy chỉnh để đảm bảo tài liệu của bạn luôn trông như dự định. Hãy đi sâu vào cách bạn có thể đạt được điều này.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET Library: Nếu bạn chưa có, hãy tải xuống[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Một IDE như Visual Studio.
- Kiến thức cơ bản về C#: Làm quen với C# sẽ giúp bạn theo dõi các ví dụ về mã.

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cần thiết trong dự án của bạn:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Bây giờ, hãy chia quy trình thành các bước đơn giản.

## Bước 1: Tải tài liệu

 Để bắt đầu, hãy tải tài liệu Word của bạn vào Aspose.Words`Document` sự vật. Tài liệu này sẽ là nơi bạn muốn đặt các thư mục phông chữ.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 2: Khởi tạo cài đặt phông chữ

 Tạo một phiên bản mới của`FontSettings`. Đối tượng này sẽ cho phép bạn quản lý nguồn phông chữ.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Bước 3: Truy xuất nguồn phông chữ hệ thống

Truy xuất các nguồn phông chữ hệ thống mặc định. Trên máy Windows, phần này thường bao gồm "Windows\Fonts\" thư mục.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Bước 4: Thêm thư mục phông chữ tùy chỉnh

Thêm một thư mục tùy chỉnh chứa các phông chữ bổ sung của bạn. Điều này rất hữu ích nếu bạn có các phông chữ cụ thể chưa được cài đặt trong thư mục phông chữ hệ thống.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Bước 5: Cập nhật nguồn phông chữ

 Chuyển đổi danh sách các nguồn phông chữ trở lại thành một mảng và đặt nó thành`FontSettings` sự vật.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Bước 6: Áp dụng cài đặt phông chữ cho tài liệu

 Cuối cùng, áp dụng cấu hình`FontSettings` vào tài liệu của bạn và lưu nó ở định dạng bạn muốn, chẳng hạn như PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn có thể đảm bảo rằng tài liệu Word của mình sử dụng đúng phông chữ, cho dù đó là phông chữ hệ thống hay phông chữ tùy chỉnh được lưu trữ trong một thư mục cụ thể. Thiết lập này giúp duy trì tính toàn vẹn về diện mạo tài liệu của bạn trên các môi trường khác nhau.

## Câu hỏi thường gặp

### Điều gì xảy ra nếu thiếu phông chữ trong cả thư mục hệ thống và thư mục tùy chỉnh?

Aspose.Words sẽ sử dụng phông chữ mặc định để thay thế phông chữ bị thiếu, đảm bảo tài liệu vẫn có thể đọc được.

### Tôi có thể thêm nhiều thư mục phông chữ tùy chỉnh không?

 Có, bạn có thể thêm nhiều thư mục phông chữ tùy chỉnh bằng cách lặp lại quá trình tạo`FolderFontSource` các đối tượng và thêm chúng vào danh sách nguồn phông chữ.

### Có thể sử dụng đường dẫn mạng cho các thư mục phông chữ tùy chỉnh không?

 Có, bạn có thể chỉ định đường dẫn mạng trong`FolderFontSource` người xây dựng.

### Aspose.Words hỗ trợ những định dạng tệp nào để lưu tài liệu?

Aspose.Words hỗ trợ nhiều định dạng khác nhau, bao gồm DOCX, PDF, HTML, v.v.

### Làm cách nào để xử lý thông báo thay thế phông chữ?

 Bạn có thể xử lý thông báo thay thế phông chữ bằng cách sử dụng`FontSettings` lớp học`FontSubstitutionWarning`sự kiện.
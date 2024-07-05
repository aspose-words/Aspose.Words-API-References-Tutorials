---
title: Đặt cài đặt dự phòng phông chữ
linktitle: Đặt cài đặt dự phòng phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thiết lập Cài đặt dự phòng phông chữ trong Aspose.Words cho .NET. Hướng dẫn toàn diện này đảm bảo tất cả các ký tự trong tài liệu của bạn được hiển thị chính xác.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-font-fallback-settings/
---

Khi làm việc với các tài liệu chứa các thành phần văn bản đa dạng, chẳng hạn như các ngôn ngữ khác nhau hoặc các ký tự đặc biệt, điều quan trọng là phải đảm bảo rằng các thành phần này được hiển thị chính xác. Aspose.Words for .NET cung cấp một tính năng mạnh mẽ được gọi là Cài đặt dự phòng phông chữ, giúp xác định quy tắc thay thế phông chữ khi phông chữ gốc không hỗ trợ một số ký tự nhất định. Trong hướng dẫn này, chúng ta sẽ khám phá cách thiết lập Cài đặt dự phòng phông chữ bằng Aspose.Words cho .NET theo hướng dẫn từng bước.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# và .NET framework.
-  Aspose.Words for .NET: Tải xuống và cài đặt từ[Liên kết tải xuống](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Thiết lập như Visual Studio để viết và chạy mã của bạn.
-  Tài liệu mẫu: Có tài liệu mẫu (ví dụ:`Rendering.docx`) sẵn sàng để thử nghiệm.
- Quy tắc dự phòng phông chữ XML: Chuẩn bị tệp XML xác định quy tắc dự phòng phông chữ.

## Nhập không gian tên

Để sử dụng Aspose.Words, bạn cần nhập các không gian tên cần thiết. Điều này cho phép truy cập vào các lớp và phương thức khác nhau cần thiết để xử lý tài liệu.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Bước 1: Xác định thư mục tài liệu

Đầu tiên, xác định thư mục nơi tài liệu của bạn được lưu trữ. Điều này rất cần thiết cho việc định vị và xử lý tài liệu của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu

 Tải tài liệu của bạn vào Aspose.Words`Document` sự vật. Bước này cho phép bạn làm việc với tài liệu theo chương trình.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình cài đặt phông chữ

 Tạo một cái mới`FontSettings` đối tượng và tải cài đặt dự phòng phông chữ từ tệp XML. Tệp XML này chứa các quy tắc dự phòng phông chữ.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Bước 4: Áp dụng cài đặt phông chữ cho tài liệu

 Chỉ định cấu hình`FontSettings` vào tài liệu. Điều này đảm bảo rằng các quy tắc dự phòng phông chữ được áp dụng khi hiển thị tài liệu.

```csharp
doc.FontSettings = fontSettings;
```

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu. Cài đặt dự phòng phông chữ sẽ được sử dụng trong quá trình lưu để đảm bảo thay thế phông chữ phù hợp.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Tệp XML: Quy tắc dự phòng phông chữ

Dưới đây là ví dụ về cách tệp XML xác định quy tắc dự phòng phông chữ của bạn sẽ trông như thế nào:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Phần kết luận

Bằng cách làm theo các bước này, bạn có thể thiết lập và sử dụng Cài đặt dự phòng phông chữ trong Aspose.Words cho .NET một cách hiệu quả. Điều này đảm bảo rằng tài liệu của bạn hiển thị chính xác tất cả các ký tự, ngay cả khi phông chữ gốc không hỗ trợ một số ký tự nhất định. Việc triển khai các cài đặt này sẽ nâng cao đáng kể chất lượng và khả năng đọc tài liệu của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Dự phòng phông chữ là gì?

Font Fallback là tính năng cho phép thay thế font chữ khi font gốc không hỗ trợ một số ký tự nhất định, đảm bảo hiển thị đúng tất cả các thành phần văn bản.

### Câu hỏi 2: Tôi có thể chỉ định nhiều phông chữ dự phòng không?

Có, bạn có thể chỉ định nhiều phông chữ dự phòng trong quy tắc XML. Aspose.Words sẽ kiểm tra từng phông chữ theo thứ tự được chỉ định cho đến khi tìm thấy phông chữ hỗ trợ ký tự.

### Câu hỏi 3: Tôi có thể tải xuống Aspose.Words cho .NET ở đâu?

 Bạn có thể tải nó xuống từ[Trang tải xuống](https://releases.aspose.com/words/net/).

### Câu hỏi 4: Làm cách nào để tạo tệp XML cho quy tắc dự phòng phông chữ?

Tệp XML có thể được tạo bằng bất kỳ trình soạn thảo văn bản nào. Nó phải tuân theo cấu trúc được hiển thị trong ví dụ được cung cấp trong hướng dẫn này.

### Câu hỏi 5: Aspose.Words có hỗ trợ không?

 Có, bạn có thể tìm thấy sự hỗ trợ trên[Diễn đàn hỗ trợ Aspose.Words](https://forum.aspose.com/c/words/8).
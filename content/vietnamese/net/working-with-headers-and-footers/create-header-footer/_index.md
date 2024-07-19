---
title: Tạo đầu trang chân trang
linktitle: Tạo đầu trang chân trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm và tùy chỉnh đầu trang và chân trang trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước này đảm bảo định dạng tài liệu chuyên nghiệp.
type: docs
weight: 10
url: /vi/net/working-with-headers-and-footers/create-header-footer/
---

Việc thêm đầu trang và chân trang vào tài liệu của bạn có thể nâng cao tính chuyên nghiệp và khả năng đọc của chúng. Với Aspose.Words for .NET, bạn có thể dễ dàng tạo và tùy chỉnh đầu trang và chân trang cho tài liệu Word của mình. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước trong quy trình, đảm bảo bạn có thể triển khai các tính năng này một cách liền mạch.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET: Tải xuống và cài đặt từ[Liên kết tải xuống](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Chẳng hạn như Visual Studio, để viết và chạy mã của bạn.
- Kiến thức cơ bản về C#: Hiểu biết về C# và .NET framework.
- Tài liệu mẫu: Một tài liệu mẫu để áp dụng đầu trang và chân trang hoặc tạo một tài liệu mới như được hiển thị trong hướng dẫn.

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết để truy cập các lớp và phương thức Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## Bước 1: Xác định thư mục tài liệu

Xác định thư mục nơi tài liệu của bạn sẽ được lưu. Điều này giúp quản lý đường dẫn một cách hiệu quả.

```csharp
// Đường dẫn tới thư mục tài liệu
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## Bước 2: Tạo một tài liệu mới

 Tạo một tài liệu mới và một`DocumentBuilder` để thuận tiện cho việc bổ sung nội dung.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Định cấu hình thiết lập trang

Thiết lập cài đặt trang, bao gồm cả việc trang đầu tiên có đầu trang/chân trang khác hay không.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## Bước 4: Thêm tiêu đề vào trang đầu tiên

Di chuyển đến phần tiêu đề cho trang đầu tiên và định cấu hình văn bản tiêu đề.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## Bước 5: Thêm tiêu đề chính

Di chuyển đến phần tiêu đề chính và chèn hình ảnh và văn bản.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Chèn hình ảnh vào tiêu đề
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## Bước 6: Thêm chân trang chính

Di chuyển đến phần chân trang chính và tạo bảng để định dạng nội dung chân trang.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Thêm đánh số trang
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();
```

## Bước 7: Thêm nội dung và ngắt trang

Di chuyển đến cuối tài liệu, thêm ngắt trang và tạo phần mới với các cài đặt trang khác nhau.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## Bước 8: Sao chép Đầu trang và Chân trang từ Phần trước

Nếu bạn muốn sử dụng lại đầu trang và chân trang từ phần trước, hãy sao chép chúng và áp dụng các sửa đổi cần thiết.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## Phần kết luận

Bằng cách làm theo các bước này, bạn có thể thêm và tùy chỉnh đầu trang và chân trang trong tài liệu Word một cách hiệu quả bằng cách sử dụng Aspose.Words for .NET. Điều này nâng cao hình thức và tính chuyên nghiệp của tài liệu của bạn, làm cho nó dễ đọc và hấp dẫn hơn.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Words dành cho .NET là gì?

Aspose.Words for .NET là thư viện cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi tài liệu Word theo chương trình trong các ứng dụng .NET.

### Q2: Tôi có thể thêm hình ảnh vào đầu trang hoặc chân trang không?

 Có, bạn có thể dễ dàng thêm hình ảnh vào đầu trang hoặc chân trang bằng cách sử dụng`DocumentBuilder.InsertImage` phương pháp.

### Câu hỏi 3: Làm cách nào để đặt đầu trang và chân trang khác nhau cho trang đầu tiên?

 Bạn có thể đặt đầu trang và chân trang khác nhau cho trang đầu tiên bằng cách sử dụng`DifferentFirstPageHeaderFooter` tài sản của`PageSetup` lớp học.

### Câu hỏi 4: Tôi có thể tìm thêm tài liệu về Aspose.Words ở đâu?

 Bạn có thể tìm thấy tài liệu đầy đủ về[Trang tài liệu API Aspose.Words](https://reference.aspose.com/words/net/).

### Câu hỏi 5: Aspose.Words có hỗ trợ không?

 Có, Aspose cung cấp hỗ trợ thông qua[diễn đàn hỗ trợ](https://forum.aspose.com/c/words/8).

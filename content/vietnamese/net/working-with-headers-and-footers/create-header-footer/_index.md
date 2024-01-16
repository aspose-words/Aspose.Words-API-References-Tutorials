---
title: Tạo đầu trang chân trang
linktitle: Tạo đầu trang chân trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo đầu trang và chân trang trong tài liệu Word của bạn bằng Aspose.Words cho .NET. Tùy chỉnh đầu trang và chân trang cho mỗi trang.
type: docs
weight: 10
url: /vi/net/working-with-headers-and-footers/create-header-footer/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# sau đây nhằm tạo đầu trang và chân trang bằng chức năng Aspose.Words for .NET. Đảm bảo bạn đã đưa thư viện Aspose.Words vào dự án của mình trước khi sử dụng mã này.

## Bước 1: Đặt đường dẫn thư mục tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu của bạn nơi tài liệu đã chỉnh sửa sẽ được lưu.

## Bước 2: Tạo tài liệu và trình tạo tài liệu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ở đây chúng ta tạo một thể hiện của`Document` lớp và một thể hiện của`DocumentBuilder` class sẽ cho phép chúng ta thao tác với tài liệu và thêm các phần tử.

## Bước 3: Đặt thông số trang và tiêu đề đầu tiên

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Chỉ định xem chúng ta có muốn đầu trang/chân trang của trang đầu tiên khác với các trang khác hay không.
// Bạn cũng có thể sử dụng thuộc tính PageSetup.OddAndEvenPagesHeaderFooter để chỉ định
// đầu trang/chân trang khác nhau cho các trang chẵn và lẻ.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Chúng tôi đặt các tham số trang, bao gồm khoảng cách tiêu đề, sau đó chuyển đến tiêu đề chính (`HeaderPrimary`). Chúng tôi sử dụng trình tạo tài liệu để thêm văn bản và định dạng tiêu đề.

## Bước 4: Chèn hình ảnh và văn bản vào tiêu đề chính

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Chúng tôi sử dụng trình tạo tài liệu để chèn hình ảnh vào góc trên bên trái của tiêu đề chính, sau đó chúng tôi thêm một số văn bản căn phải.

## Bước 5: Chèn bảng vào footer chính

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

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

builder.MoveToDocumentEnd();
```

## Bước 6: Thêm trang mới và đặt đầu trang/chân trang

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Phần này không cần đầu trang/chân trang khác cho trang đầu tiên, chúng ta chỉ cần một trang tiêu đề trong tài liệu,
//và đầu trang/chân trang cho trang này đã được xác định ở phần trước.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Phần này mặc định hiển thị đầu trang/chân trang của phần trước, gọi currentSection.HeadersFooters.LinkToPrevious(false) để ngắt liên kết này,
// chiều rộng trang khác nhau đối với phần mới, vì vậy chúng ta cần đặt độ rộng ô khác nhau cho bảng chân trang.
currentSection.HeadersFooters.LinkToPrevious(false);

// Nếu chúng tôi muốn sử dụng đầu trang/chân trang đã có sẵn cho phần này,
//nhưng với một vài thay đổi nhỏ, việc sao chép đầu trang/chân trang có thể hợp lý
// từ phần trước và áp dụng những thay đổi cần thiết ở nơi chúng tôi muốn.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Lưu tài liệu
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Chúng tôi thêm ngắt trang và ngắt phần để tạo một trang mới nơi hiển thị đầu trang/chân trang chính. Chúng tôi đặt tham số cho phần mới, sau đó chúng tôi sử dụng`CopyHeadersFootersFromPreviousSection` phương pháp sao chép đầu trang/chân trang từ phần trước. Cuối cùng, chúng ta đặt độ rộng ô thích hợp cho bảng chân trang chính và lưu tài liệu.

### Mã nguồn ví dụ để tạo đầu trang và chân trang với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Chỉ định xem chúng tôi có muốn đầu trang/chân trang của trang đầu tiên khác với các trang khác hay không.
// Bạn cũng có thể sử dụng thuộc tính PageSetup.OddAndEvenPagesHeaderFooter để chỉ định
// đầu trang/chân trang khác nhau cho các trang chẵn và lẻ.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Chèn hình ảnh được định vị vào góc trên/trái của tiêu đề.
// Khoảng cách từ cạnh trên/trái của trang được đặt thành 10 điểm.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Chúng ta sử dụng bảng có hai ô để tạo thành một phần văn bản trên dòng (có đánh số trang).
// Để được căn trái và phần còn lại của văn bản (có bản quyền) được căn phải.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Nó sử dụng các trường TRANG và SỐ để tự động tính toán số trang hiện tại và nhiều trang.
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

builder.MoveToDocumentEnd();

// Thực hiện ngắt trang để tạo trang thứ hai trên đó sẽ nhìn thấy đầu trang/chân trang chính.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Phần này không cần đầu trang/chân trang khác của trang đầu tiên, chúng tôi chỉ cần một trang tiêu đề trong tài liệu,
//và đầu trang/chân trang cho trang này đã được xác định ở phần trước.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Phần này hiển thị đầu trang/chân trang từ phần trước
// theo mặc định, hãy gọi currentSection.HeadersFooters.LinkToPrevious(false) để hủy độ rộng trang này
// khác với phần mới và do đó chúng ta cần đặt độ rộng ô khác nhau cho bảng chân trang.
currentSection.HeadersFooters.LinkToPrevious(false);

// Nếu chúng ta muốn sử dụng bộ đầu trang/chân trang đã có sẵn cho phần này.
// Nhưng với một số sửa đổi nhỏ, việc sao chép đầu trang/chân trang có thể sẽ hữu ích hơn
// từ phần trước và áp dụng các sửa đổi cần thiết ở nơi chúng tôi muốn.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể thêm tiêu đề vào tài liệu của mình trong Aspose.Words?

 Đáp: Để thêm tiêu đề vào tài liệu của bạn trong Aspose.Words, bạn có thể sử dụng`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` phương pháp. Phương pháp này thêm tiêu đề chính vào phần đầu tiên của tài liệu của bạn.

#### Câu hỏi: Làm cách nào tôi có thể thêm chân trang vào tài liệu của mình trong Aspose.Words?

 Trả lời: Để thêm chân trang vào tài liệu của bạn trong Aspose.Words, bạn có thể sử dụng`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`phương pháp. Phương pháp này thêm chân trang chính vào phần đầu tiên của tài liệu của bạn.

#### Câu hỏi: Làm cách nào tôi có thể thêm văn bản vào đầu trang hoặc chân trang của mình trong Aspose.Words?

 Trả lời: Để thêm văn bản vào đầu trang hoặc chân trang trong Aspose.Words, bạn có thể sử dụng`HeaderFooter.Paragraphs` để lấy bộ sưu tập đoạn văn của đầu trang hoặc chân trang, sau đó thêm đoạn chứa văn bản của bạn vào bộ sưu tập này bằng cách sử dụng thuộc tính`ParagraphCollection.Add` phương pháp.

#### Câu hỏi: Tôi có thể tùy chỉnh nội dung đầu trang hoặc chân trang bằng hình ảnh và số trang trong Aspose.Words không?

 Trả lời: Có, bạn có thể tùy chỉnh nội dung đầu trang hoặc chân trang bằng hình ảnh và số trang trong Aspose.Words. Bạn có thể sử dụng các đối tượng như`Shape` để thêm hình ảnh và các đối tượng như`Field` để thêm số trang vào đầu trang hoặc chân trang của bạn.

#### Câu hỏi: Tôi có thể thay đổi phông chữ, kích thước và màu sắc của văn bản trong đầu trang hoặc chân trang trong Aspose.Words không?

 Trả lời: Có, bạn có thể thay đổi phông chữ, kích thước và màu sắc của văn bản trong đầu trang hoặc chân trang trong Aspose.Words. Bạn có thể truy cập các thuộc tính định dạng văn bản như`Font` để thay đổi phông chữ,`Size` để điều chỉnh kích thước và`Color`để đặt màu văn bản.
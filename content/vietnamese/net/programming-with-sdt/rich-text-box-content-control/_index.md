---
title: Kiểm soát nội dung hộp văn bản có định dạng
linktitle: Kiểm soát nội dung hộp văn bản có định dạng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo điều khiển nội dung hộp văn bản có định dạng trong tài liệu Word bằng cách sử dụng Aspose.Words for .NET cho phép định dạng và tạo kiểu văn bản.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/rich-text-box-content-control/
---

Hướng dẫn này trình bày cách tạo điều khiển nội dung hộp văn bản có định dạng trong tài liệu Word bằng Aspose.Words cho .NET. Điều khiển nội dung hộp văn bản đa dạng thức cho phép người dùng nhập và định dạng văn bản với nhiều kiểu và tùy chọn định dạng khác nhau.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu và Thẻ Tài liệu có Cấu trúc
 Tạo một phiên bản mới của`Document` lớp học và một`StructuredDocumentTag` để thể hiện việc kiểm soát nội dung hộp văn bản có định dạng. Chỉ định`SdtType.RichText` như loại và`MarkupLevel.Block` làm cấp độ đánh dấu để tạo hộp văn bản có định dạng cấp khối.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Bước 3: Tạo và định dạng nội dung văn bản đa dạng thức
Tạo một đoạn văn và chạy để thể hiện nội dung văn bản đa dạng thức. Đặt các tùy chọn văn bản và định dạng như màu sắc, phông chữ, v.v.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Bước 4: Thêm nội dung văn bản đa dạng thức vào Kiểm soát nội dung
 Thêm đoạn văn có nội dung văn bản đa dạng thức vào`ChildNodes` bộ sưu tập kiểm soát nội dung hộp văn bản có định dạng.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Bước 5: Nối điều khiển nội dung vào tài liệu
 Nối điều khiển nội dung hộp văn bản có định dạng vào nội dung tài liệu bằng cách sử dụng`AppendChild` phương pháp của phần thân đầu tiên của tài liệu.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Bước 6: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save`phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Mã nguồn mẫu cho Kiểm soát nội dung hộp văn bản đa dạng thức bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Đó là nó! Bạn đã tạo thành công điều khiển nội dung hộp văn bản có định dạng trong tài liệu Word của mình bằng Aspose.Words for .NET.
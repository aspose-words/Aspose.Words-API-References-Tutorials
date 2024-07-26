---
title: Kiểm soát nội dung hộp tổ hợp
linktitle: Kiểm soát nội dung hộp tổ hợp
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo Kiểm soát nội dung hộp tổ hợp trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/combo-box-content-control/
---

Hướng dẫn này giải thích cách tạo Điều khiển nội dung Hộp tổ hợp trong tài liệu Word bằng Aspose.Words cho .NET. Kiểm soát nội dung hộp tổ hợp cho phép người dùng chọn một mục từ danh sách thả xuống.

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
 Tạo một phiên bản mới của`Document` lớp học và một`StructuredDocumentTag` để thể hiện việc kiểm soát nội dung hộp tổ hợp. Chỉ định`SdtType.ComboBox` như loại và`MarkupLevel.Block` làm mức đánh dấu để tạo hộp tổ hợp cấp khối.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Bước 3: Thêm vật phẩm vào Combo Box
 Thêm các mục vào hộp tổ hợp bằng cách sử dụng`ListItems` tài sản của`StructuredDocumentTag` . Mỗi mục được thể hiện bằng một`SdtListItem` đối tượng, lấy một văn bản hiển thị và một giá trị. Trong ví dụ này, chúng tôi thêm ba mục vào hộp tổ hợp.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Bước 4: Nối Thẻ tài liệu có cấu trúc vào tài liệu
 Nối điều khiển nội dung hộp tổ hợp vào phần nội dung của tài liệu bằng cách sử dụng`AppendChild` phương pháp của phần thân đầu tiên của tài liệu.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Bước 5: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Mã nguồn ví dụ cho Kiểm soát nội dung Hộp tổ hợp bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Đó là nó! Bạn đã tạo thành công Điều khiển nội dung Hộp tổ hợp trong tài liệu Word của mình bằng Aspose.Words cho .NET.
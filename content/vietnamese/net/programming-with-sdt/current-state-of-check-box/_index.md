---
title: Hộp kiểm trạng thái hiện tại
linktitle: Hộp kiểm trạng thái hiện tại
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách truy xuất và đặt trạng thái hiện tại của điều khiển nội dung hộp kiểm trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/current-state-of-check-box/
---

Hướng dẫn này giải thích cách truy xuất và đặt trạng thái hiện tại của điều khiển nội dung hộp kiểm trong tài liệu Word bằng Aspose.Words cho .NET. Bạn có thể chọn hoặc bỏ chọn hộp kiểm dựa trên trạng thái hiện tại của nó.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu và truy xuất Kiểm soát nội dung hộp kiểm
 Tải tài liệu Word bằng cách sử dụng`Document` hàm tạo, chuyển đường dẫn đến tài liệu dưới dạng tham số. Sau đó, truy xuất điều khiển nội dung hộp kiểm mong muốn từ tài liệu. Trong ví dụ này, chúng tôi giả định rằng hộp kiểm là thẻ tài liệu có cấu trúc đầu tiên trong tài liệu.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Bước 3: Chọn hoặc bỏ chọn hộp kiểm dựa trên trạng thái hiện tại của nó
 Kiểm tra xem thẻ tài liệu có cấu trúc được truy xuất có thuộc loại không`SdtType.Checkbox` . Nếu có, hãy đặt`Checked` thuộc tính của kiểm soát nội dung để`true` để kiểm tra hộp. Nếu không, bạn có thể bỏ chọn nó.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Bước 4: Lưu tài liệu
 Lưu tài liệu đã sửa đổi vào thư mục được chỉ định bằng cách sử dụng`Save`phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Mã nguồn ví dụ cho Hộp kiểm trạng thái hiện tại bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Nhận quyền kiểm soát nội dung đầu tiên từ tài liệu.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Đó là nó! Bạn đã truy xuất và đặt thành công trạng thái hiện tại của điều khiển nội dung hộp kiểm trong tài liệu Word của mình bằng Aspose.Words for .NET.
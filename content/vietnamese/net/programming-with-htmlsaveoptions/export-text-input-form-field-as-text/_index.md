---
title: Xuất trường biểu mẫu nhập văn bản dưới dạng văn bản
linktitle: Xuất trường biểu mẫu nhập văn bản dưới dạng văn bản
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xuất các trường biểu mẫu nhập văn bản dưới dạng văn bản thuần túy với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để xuất các trường biểu mẫu nhập văn bản dưới dạng văn bản thuần túy với Aspose.Words cho .NET. Tính năng này cho phép bạn xuất các trường biểu mẫu nhập văn bản dưới dạng văn bản có thể đọc được, thay vì xuất chúng dưới dạng phần tử nhập HTML.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Ở bước này, chúng ta sẽ tải tài liệu để xuất. Sử dụng đoạn mã sau để tải tài liệu từ một thư mục được chỉ định:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Mã này tạo ra một thể hiện của`Document` bằng cách tải tài liệu từ thư mục được chỉ định.

## Bước 3: Định cấu hình tùy chọn sao lưu HTML

Bây giờ chúng tôi sẽ định cấu hình các tùy chọn lưu HTML để xuất các trường biểu mẫu nhập văn bản dưới dạng văn bản thuần túy. Sử dụng mã sau đây:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Thư mục được chỉ định phải tồn tại và trống.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions`và thiết lập`ExportTextInputFormFieldAsText` tùy chọn để`true` để xuất các trường biểu mẫu nhập văn bản dưới dạng văn bản thuần túy. Hơn nữa, nó chỉ định thư mục nơi hình ảnh được trích xuất sẽ được lưu.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng tôi sẽ chuyển đổi tài liệu sang HTML bằng các tùy chọn lưu HTML được định cấu hình trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Mã này chuyển đổi tài liệu sang HTML bằng cách xuất các trường biểu mẫu nhập văn bản dưới dạng văn bản thuần túy và lưu tệp HTML đã xuất vào thư mục được chỉ định.

### Mã nguồn ví dụ cho Trường biểu mẫu nhập văn bản xuất dưới dạng văn bản bằng Aspose.Words cho .NET


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Thư mục được chỉ định cần tồn tại và phải trống.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Đặt tùy chọn để xuất các trường biểu mẫu dưới dạng văn bản thuần túy, không phải dưới dạng phần tử nhập HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu trong thư mục`dataDir` Biến đổi.
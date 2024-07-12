---
title: Thêm tiếng Nhật làm ngôn ngữ soạn thảo
linktitle: Thêm tiếng Nhật làm ngôn ngữ soạn thảo
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thêm tiếng Nhật làm ngôn ngữ soạn thảo với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để hiểu và triển khai chức năng thêm tiếng Nhật làm ngôn ngữ soạn thảo với Aspose.Words cho .NET. Tính năng này cho phép bạn đặt tùy chọn ngôn ngữ khi tải tài liệu và thêm tiếng Nhật làm ngôn ngữ chỉnh sửa.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word không chứa ngôn ngữ chỉnh sửa mặc định và chúng tôi muốn thêm tiếng Nhật vào đó. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Đặt tùy chọn ngôn ngữ sẽ được sử dụng khi tải tài liệu.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Bước 3: Kiểm tra ngôn ngữ mặc định

Sau khi tải tài liệu, chúng tôi sẽ kiểm tra xem ngôn ngữ soạn thảo mặc định đã được đặt chính xác là tiếng Nhật hay chưa. Sử dụng mã sau đây để lấy ID ngôn ngữ Viễn Đông:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Mã này kiểm tra xem ID ngôn ngữ Viễn Đông có khớp với ID tiếng Nhật hay không. Theo kết quả, nó sẽ hiển thị một thông báo tương ứng.

### Mã nguồn ví dụ cho Thêm tiếng Nhật làm ngôn ngữ chỉnh sửa bằng Aspose.Words cho .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Đặt tùy chọn ngôn ngữ sẽ được sử dụng khi tải tài liệu.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```


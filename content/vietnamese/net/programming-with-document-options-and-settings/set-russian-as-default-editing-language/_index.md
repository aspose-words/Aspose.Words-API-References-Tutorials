---
title: Đặt tiếng Nga làm ngôn ngữ chỉnh sửa mặc định
linktitle: Đặt tiếng Nga làm ngôn ngữ chỉnh sửa mặc định
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để đặt tiếng Nga làm ngôn ngữ chỉnh sửa mặc định của tài liệu với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để đặt tiếng Nga làm ngôn ngữ chỉnh sửa mặc định với Aspose.Words cho .NET. Tính năng này cho phép bạn đặt ngôn ngữ mặc định khi tải tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn đặt tiếng Nga làm ngôn ngữ chỉnh sửa mặc định. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Kiểm tra ngôn ngữ mặc định

Sau khi tải tài liệu lên, chúng tôi sẽ kiểm tra xem ngôn ngữ mặc định đã được đặt chính xác thành tiếng Nga hay chưa. Sử dụng mã sau để lấy ID ngôn ngữ mặc định:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Mã này sẽ kiểm tra xem ID ngôn ngữ có khớp với ID tiếng Nga hay không. Theo kết quả, nó sẽ hiển thị một thông báo tương ứng.

### Mã nguồn ví dụ cho Đặt tiếng Nga làm ngôn ngữ chỉnh sửa mặc định bằng Aspose.Words cho .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách đặt tiếng Nga làm ngôn ngữ soạn thảo mặc định cho tài liệu bằng Aspose.Words for .NET. Bằng cách làm theo hướng dẫn từng bước
---
title: Hiển thị lỗi ngữ pháp và chính tả
linktitle: Hiển thị lỗi ngữ pháp và chính tả
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để bật hiển thị lỗi ngữ pháp và chính tả trong tài liệu bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để cho phép hiển thị các lỗi ngữ pháp và chính tả với Aspose.Words dành cho .NET. Tính năng này cho phép bạn xem các lỗi ngữ pháp và chính tả trong tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn hiển thị các lỗi ngữ pháp và chính tả. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Kích hoạt hiển thị lỗi

Bây giờ chúng ta sẽ kích hoạt tính năng hiển thị lỗi ngữ pháp và chính tả trong tài liệu. Sử dụng đoạn mã sau để bật hiển thị lỗi:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Mã này cho phép hiển thị các lỗi ngữ pháp (`ShowGrammaticalErrors`) và lỗi chính tả (`ShowSpellingErrors`) trong tài liệu.

### Mã nguồn mẫu cho Hiển thị lỗi ngữ pháp và chính tả bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách bật hiển thị lỗi ngữ pháp và chính tả trong tài liệu bằng Aspose.Words for .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng kích hoạt tính năng này trong tài liệu của riêng mình.
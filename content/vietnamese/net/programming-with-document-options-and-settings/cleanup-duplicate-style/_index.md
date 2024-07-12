---
title: Dọn dẹp phong cách trùng lặp
linktitle: Dọn dẹp phong cách trùng lặp
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xóa các kiểu trùng lặp trong tài liệu bằng Aspose.Words cho .NET. Bao gồm mã nguồn đầy đủ.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước mã nguồn C# để dọn sạch các kiểu trùng lặp với Aspose.Words cho .NET. Tính năng này giúp loại bỏ các kiểu trùng lặp khỏi tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Ở bước này, chúng ta sẽ tải tài liệu Word mà chúng ta muốn dọn dẹp. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Đếm kiểu dáng trước khi vệ sinh

Trước khi tiến hành dọn dẹp, chúng tôi sẽ đếm số lượng kiểu có trong tài liệu. Sử dụng đoạn mã sau để hiển thị số kiểu:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Câu lệnh này hiển thị số lượng kiểu dáng có trong tài liệu.

## Bước 4: Dọn dẹp các kiểu trùng lặp

Bây giờ hãy xóa các kiểu trùng lặp khỏi tài liệu. Sử dụng đoạn mã sau để thực hiện việc dọn dẹp:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Mã này sẽ xóa các kiểu trùng lặp khỏi tài liệu bằng cách sử dụng các tùy chọn đã chỉ định. Trong ví dụ này, chúng tôi đã kích hoạt`DuplicateStyle` tùy chọn để dọn sạch các kiểu trùng lặp.

## Bước 5: Đếm kiểu dáng sau khi vệ sinh

Sau khi thực hiện vệ sinh, chúng ta sẽ đếm lại số kiểu để kiểm tra xem đã giảm chưa. Sử dụng đoạn mã sau để hiển thị số kiểu mới:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Câu lệnh này hiển thị số kiểu còn lại sau khi làm sạch.

### Mã nguồn mẫu cho Kiểu dọn dẹp trùng lặp bằng cách sử dụng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Đếm số kiểu trước khi dọn dẹp.
	Console.WriteLine(doc.Styles.Count);

	// Xóa các kiểu trùng lặp khỏi tài liệu.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// Số lượng kiểu sau khi Dọn dẹp đã giảm.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```
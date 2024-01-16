---
title: Dọn dẹp các kiểu và danh sách không sử dụng
linktitle: Dọn dẹp các kiểu và danh sách không sử dụng
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để dọn dẹp các kiểu và danh sách không sử dụng trong tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để dọn sạch các kiểu và danh sách không sử dụng bằng Aspose.Words cho .NET. Tính năng này cho phép bạn xóa các kiểu và danh sách không được sử dụng trong tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word chứa các kiểu và danh sách không sử dụng mà chúng tôi muốn xóa. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Đếm kiểu dáng và danh sách trước khi làm sạch

Trước khi làm sạch, chúng ta sẽ đếm số lượng kiểu dáng và danh sách có trong tài liệu. Sử dụng đoạn mã sau để hiển thị bộ đếm:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Các hướng dẫn này hiển thị số lượng kiểu và danh sách có trong tài liệu trước khi làm sạch.

## Bước 4: Dọn dẹp các kiểu và danh sách không sử dụng

Bây giờ hãy dọn sạch các kiểu và danh sách không sử dụng khỏi tài liệu. Sử dụng đoạn mã sau để thực hiện việc dọn dẹp:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Mã này sẽ xóa các kiểu và danh sách không sử dụng khỏi tài liệu bằng cách sử dụng các tùy chọn đã chỉ định. Trong ví dụ này, chúng tôi đã kích hoạt`UnusedStyles` tùy chọn để loại bỏ các kiểu không sử dụng và vô hiệu hóa`UnusedLists` tùy chọn để giữ danh sách ngay cả khi chúng không được sử dụng.

## Bước 5: Đếm kiểu dáng và danh sách sau khi làm sạch

Sau khi dọn dẹp, chúng tôi sẽ đếm lại các kiểu và danh sách để kiểm tra xem chúng có bị thu gọn hay không. Sử dụng đoạn mã sau để hiển thị các bộ đếm mới:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Các hướng dẫn này hiển thị số kiểu và danh sách còn lại sau khi làm sạch.

### Mã nguồn ví dụ để dọn dẹp các kiểu và danh sách không sử dụng bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// Kết hợp với các kiểu có sẵn, tài liệu hiện có tám kiểu.
	// Kiểu tùy chỉnh được đánh dấu là "đã sử dụng" trong khi có bất kỳ văn bản nào trong tài liệu
	// được định dạng theo phong cách đó. Điều này có nghĩa là 4 kiểu chúng tôi đã thêm hiện không được sử dụng.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Xóa các kiểu và danh sách không sử dụng khỏi tài liệu tùy thuộc vào CleanupOptions nhất định.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách xóa các kiểu và danh sách không sử dụng khỏi tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng áp dụng tính năng này cho tài liệu của riêng mình.


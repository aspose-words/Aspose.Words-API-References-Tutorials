---
title: Xác minh tài liệu Word được mã hóa
linktitle: Xác minh tài liệu Word được mã hóa
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xác minh tài liệu word được mã hóa bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-fileformat/verify-encrypted-document/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng tính năng Xác minh Tài liệu Word được Mã hóa với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách kiểm tra xem tài liệu có được mã hóa hay không.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Phát hiện định dạng file

 Tiếp theo, chúng tôi sử dụng`DetectFileFormat` phương pháp của`FileFormatUtil` class để phát hiện thông tin định dạng tệp. Trong ví dụ này, chúng tôi giả định rằng tài liệu được mã hóa có tên là "Encrypted.docx" và nằm trong thư mục tài liệu được chỉ định.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Bước 3: Kiểm tra xem tài liệu đã được mã hóa chưa

 Chúng tôi sử dụng`IsEncrypted` tài sản của`FileFormatInfo` đối tượng để kiểm tra xem tài liệu có được mã hóa hay không. Thuộc tính này trả về`true` nếu tài liệu được mã hóa, nếu không nó sẽ trả về`false`. Chúng tôi hiển thị kết quả trong bảng điều khiển.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Đó là tất cả ! Bạn đã kiểm tra thành công xem tài liệu có được mã hóa bằng Aspose.Words cho .NET hay không.

### Mã nguồn ví dụ để xác minh tài liệu được mã hóa bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Các câu hỏi thường gặp

### Hỏi: Các bước để xác minh tài liệu Word được mã hóa là gì?

Các bước để xác minh tài liệu Word được mã hóa như sau:

Xác định thư mục tài liệu.

Phát hiện định dạng tập tin.

Kiểm tra xem tài liệu có được mã hóa hay không.

### Hỏi: Làm cách nào tôi có thể đặt thư mục tài liệu?
 Để đặt thư mục tài liệu, bạn cần thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn trong đoạn mã sau:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Q: Làm thế nào để phát hiện định dạng tập tin?
 Bạn có thể dùng`DetectFileFormat` phương pháp của`FileFormatUtil` class để phát hiện thông tin định dạng tập tin. Trong ví dụ sau, chúng tôi giả sử rằng tài liệu được mã hóa có tên là "Encrypted.docx" và nằm trong thư mục tài liệu được chỉ định:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Hỏi: Làm cách nào để kiểm tra xem tài liệu có được mã hóa hay không?
 Bạn có thể dùng`IsEncrypted` tài sản của`FileFormatInfo` đối tượng để kiểm tra xem tài liệu có được mã hóa hay không. Thuộc tính này trả về`true` nếu tài liệu được mã hóa, nếu không nó sẽ trả về`false`. Kết quả được hiển thị trong bảng điều khiển:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Hỏi: Làm cách nào để kiểm tra xem tài liệu có được mã hóa bằng Aspose.Words cho .NET không?
Bằng cách làm theo các bước được đề cập trong hướng dẫn này và chạy mã nguồn được cung cấp, bạn có thể kiểm tra xem tài liệu có được mã hóa bằng Aspose.Words cho .NET hay không.

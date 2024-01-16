---
title: Mục tiêu so sánh trong tài liệu Word
linktitle: Mục tiêu so sánh trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu tính năng so sánh mục tiêu trong tài liệu word của Aspose.Words cho .NET cho phép bạn so sánh các tài liệu và tạo một tài liệu mới chứa các thay đổi đã thực hiện.
type: docs
weight: 10
url: /vi/net/compare-documents/comparison-target/
---
Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, mã này sử dụng mục tiêu so sánh trong chức năng tài liệu word của Aspose.Words cho .NET.

## Bước 1: Giới thiệu

Tính năng so sánh mục tiêu của Aspose.Words cho .NET cho phép bạn so sánh hai tài liệu và tạo một tài liệu mới chứa các thay đổi được thực hiện đối với tài liệu đích. Điều này có thể hữu ích để theo dõi những thay đổi được thực hiện giữa các phiên bản khác nhau của tài liệu.

## Bước 2: Thiết lập môi trường

Trước khi bắt đầu, bạn cần thiết lập môi trường phát triển của mình để hoạt động với Aspose.Words cho .NET. Đảm bảo bạn đã cài đặt thư viện Aspose.Words và có dự án C# phù hợp để nhúng mã vào.

## Bước 3: Thêm các cụm lắp ráp cần thiết

Để sử dụng tính năng mục tiêu so sánh của Aspose.Words cho .NET, bạn phải thêm các tập hợp cần thiết vào dự án của mình. Đảm bảo bạn có tài liệu tham khảo thích hợp về Aspose.Words trong dự án của mình.

```csharp
using Aspose.Words;
```

## Bước 4: Khởi tạo tài liệu

Ở bước này, chúng ta sẽ khởi tạo hai tài liệu để so sánh. Bạn phải chỉ định đường dẫn thư mục nơi chứa tài liệu của bạn cũng như tên của tài liệu nguồn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Khởi tạo tài liệu A để so sánh.
Document docA = new Document(dataDir + "DocumentA.docx");

// Sao chép tài liệu A để tạo một bản sao giống hệt tài liệu B.
Document docB = docA.Clone();
```

## Bước 5: Cấu hình các tùy chọn so sánh

Trong bước này, chúng tôi sẽ định cấu hình các tùy chọn so sánh để chỉ định hành vi so sánh. Các tùy chọn bao gồm khả năng bỏ qua định dạng, cũng như mục tiêu so sánh, đó là tùy chọn "Hiển thị các thay đổi trong" trong hộp thoại "So sánh Tài liệu" của Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Bước 6: So sánh tài liệu

Bây giờ chúng ta sẽ so sánh các tài liệu và tạo ra kết quả trong một tài liệu mới.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 Các`Compare`phương pháp so sánh tài liệu A với tài liệu B và lưu các thay đổi vào tài liệu A. Bạn có thể chỉ định tên người dùng và ngày so sánh để tham khảo.

### Mã nguồn mẫu cho Mục tiêu so sánh bằng Aspose.Words cho .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Liên quan đến tùy chọn "Hiển thị các thay đổi trong" của Microsoft Word trong hộp thoại "So sánh Tài liệu".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Phần kết luận

Trong bài viết này, chúng tôi đã khám phá tính năng mục tiêu khác của Aspose.Words cho .NET. Tính năng này cho phép bạn so sánh hai tài liệu và tạo một tài liệu mới chứa những thay đổi đã thực hiện. Bạn có thể sử dụng kiến thức này để theo dõi những thay đổi giữa các phiên bản khác nhau của tài liệu.

### Câu hỏi thường gặp

#### Câu hỏi: Mục đích của việc sử dụng Mục tiêu so sánh trong Aspose.Words cho .NET là gì?

Đáp: Mục tiêu so sánh trong Aspose.Words dành cho .NET cho phép bạn so sánh hai tài liệu và tạo một tài liệu mới chứa những thay đổi được thực hiện đối với tài liệu đích. Tính năng này hữu ích để theo dõi các thay đổi được thực hiện giữa các phiên bản khác nhau của tài liệu và trực quan hóa sự khác biệt trong một tài liệu riêng biệt.

#### Câu hỏi: Làm cách nào để sử dụng Mục tiêu so sánh trong Aspose.Words cho .NET?

Trả lời: Để sử dụng Mục tiêu so sánh trong Aspose.Words cho .NET, hãy làm theo các bước sau:
1. Thiết lập môi trường phát triển của bạn với thư viện Aspose.Words.
2. Thêm các tập hợp cần thiết vào dự án của bạn bằng cách tham khảo Aspose.Words.
3.  Khởi tạo các tài liệu mà bạn muốn so sánh bằng cách sử dụng`Document` lớp học hoặc`DocumentBuilder` lớp học.
4.  Định cấu hình các tùy chọn so sánh bằng cách tạo một`CompareOptions` đối tượng và các thuộc tính cài đặt như`IgnoreFormatting` Và`Target` (ví dụ,`ComparisonTargetType.New` cho mục tiêu so sánh).
5.  Sử dụng`Compare` phương pháp trên một tài liệu, chuyển tài liệu khác và`CompareOptions` đối tượng làm tham số. Phương pháp này sẽ so sánh các tài liệu và lưu các thay đổi trong tài liệu đầu tiên.

####  Hỏi: Mục đích của việc này là gì?`Target` property in the `CompareOptions` class?

 Đáp: Cái`Target` tài sản ở`CompareOptions` lớp cho phép bạn chỉ định mục tiêu so sánh, tương tự như tùy chọn "Hiển thị các thay đổi trong" trong hộp thoại "So sánh Tài liệu" của Microsoft Word. Mục tiêu có thể được đặt thành`ComparisonTargetType.New` để hiển thị những thay đổi trong một tài liệu mới,`ComparisonTargetType.Current` để hiển thị những thay đổi trong tài liệu hiện tại, hoặc`ComparisonTargetType.Formatting` để chỉ hiển thị các thay đổi định dạng.
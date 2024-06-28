---
title: So sánh chi tiết trong tài liệu Word
linktitle: So sánh chi tiết trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu Tính năng So sánh chi tiết trong tài liệu word của Aspose.Words for .NET cho phép so sánh các tài liệu theo từng ký tự, báo cáo các thay đổi được thực hiện.
type: docs
weight: 10
url: /vi/net/compare-documents/comparison-granularity/
---
Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng tính năng So sánh mức độ chi tiết trong tài liệu word của Aspose.Words cho .NET.

## Bước 1: Giới thiệu

Tính năng So sánh mức độ chi tiết của Aspose.Words cho .NET cho phép bạn so sánh các tài liệu ở cấp độ ký tự. Điều này có nghĩa là mỗi ký tự sẽ được so sánh và những thay đổi sẽ được báo cáo tương ứng.

## Bước 2: Thiết lập môi trường

Trước khi bắt đầu, bạn cần thiết lập môi trường phát triển của mình để hoạt động với Aspose.Words cho .NET. Đảm bảo bạn đã cài đặt thư viện Aspose.Words và có dự án C# phù hợp để nhúng mã vào.

## Bước 3: Thêm các cụm lắp ráp cần thiết

Để sử dụng tính năng So sánh chi tiết của Aspose.Words cho .NET, bạn cần thêm các tập hợp cần thiết vào dự án của mình. Đảm bảo bạn có tài liệu tham khảo thích hợp về Aspose.Words trong dự án của mình.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Bước 4: Tạo tài liệu

Trong bước này, chúng ta sẽ tạo hai tài liệu bằng lớp DocumentBuilder. Những tài liệu này sẽ được sử dụng để so sánh.

```csharp
// Tạo tài liệu A
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Tạo tài liệu B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Bước 5: Cấu hình các tùy chọn so sánh

Trong bước này, chúng tôi sẽ định cấu hình các tùy chọn so sánh để chỉ định mức độ chi tiết so sánh. Ở đây chúng tôi sẽ sử dụng mức độ chi tiết ở cấp độ ký tự.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Bước 6: So sánh tài liệu

Bây giờ hãy so sánh các tài liệu bằng phương thức Compare của lớp Document. Những thay đổi sẽ được lưu trong tài liệu A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 Các`Compare` phương pháp so sánh tài liệu A với tài liệu B và lưu các thay đổi vào tài liệu A. Bạn có thể chỉ định tên tác giả và ngày so sánh để tham khảo.

## Phần kết luận

Trong bài viết này, chúng tôi đã khám phá tính năng So sánh mức độ chi tiết của Aspose.Words cho .NET. Tính năng này cho phép bạn so sánh các tài liệu ở cấp độ ký tự và báo cáo các thay đổi. Bạn có thể sử dụng kiến thức này để thực hiện so sánh tài liệu chi tiết trong dự án của mình.

### Mã nguồn mẫu để so sánh mức độ chi tiết bằng Aspose.Words cho .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá tính năng So sánh chi tiết của Aspose.Words cho .NET. Tính năng này cho phép bạn chỉ định mức độ chi tiết khi so sánh tài liệu. Bằng cách chọn các mức độ chi tiết khác nhau, bạn có thể thực hiện so sánh chi tiết ở cấp độ ký tự, từ hoặc khối, tùy thuộc vào yêu cầu cụ thể của bạn. Aspose.Words for .NET cung cấp khả năng so sánh tài liệu linh hoạt và mạnh mẽ, giúp dễ dàng xác định sự khác biệt trong tài liệu với mức độ chi tiết khác nhau.

### Câu hỏi thường gặp

#### Câu hỏi: Mục đích của việc sử dụng Độ chi tiết so sánh trong Aspose.Words cho .NET là gì?

Trả lời: Độ chi tiết so sánh trong Aspose.Words dành cho .NET cho phép bạn chỉ định mức độ chi tiết khi so sánh các tài liệu. Với tính năng này, bạn có thể so sánh các tài liệu ở các cấp độ khác nhau, chẳng hạn như cấp độ ký tự, cấp độ từ hoặc thậm chí cấp độ khối. Mỗi mức độ chi tiết cung cấp một mức độ chi tiết khác nhau trong kết quả so sánh.

#### Câu hỏi: Làm cách nào để sử dụng Độ chi tiết so sánh trong Aspose.Words cho .NET?

Trả lời: Để sử dụng Độ chi tiết so sánh trong Aspose.Words cho .NET, hãy làm theo các bước sau:
1. Thiết lập môi trường phát triển của bạn với thư viện Aspose.Words.
2. Thêm các tập hợp cần thiết vào dự án của bạn bằng cách tham khảo Aspose.Words.
3.  Tạo các tài liệu mà bạn muốn so sánh bằng cách sử dụng`DocumentBuilder` lớp học.
4.  Định cấu hình các tùy chọn so sánh bằng cách tạo một`CompareOptions` đối tượng và thiết lập`Granularity` thuộc tính đến mức mong muốn (ví dụ:`Granularity.CharLevel` để so sánh cấp độ nhân vật).
5.  Sử dụng`Compare` phương pháp trên một tài liệu, chuyển tài liệu khác và`CompareOptions` đối tượng làm tham số. Phương pháp này sẽ so sánh các tài liệu dựa trên mức độ chi tiết được chỉ định và lưu các thay đổi trong tài liệu đầu tiên.

#### Câu hỏi: Mức độ chi tiết so sánh có sẵn trong Aspose.Words cho .NET là gì?

Đáp: Aspose.Words for .NET cung cấp ba mức độ chi tiết so sánh:
- `Granularity.CharLevel`: So sánh các tài liệu ở cấp độ ký tự.
- `Granularity.WordLevel`: So sánh các tài liệu ở cấp độ từ.
- `Granularity.BlockLevel`: So sánh các tài liệu ở cấp độ khối.

#### Câu hỏi: Làm cách nào tôi có thể diễn giải kết quả so sánh với độ chi tiết ở cấp độ ký tự?

Đáp: Với mức độ chi tiết ở cấp độ ký tự, mỗi ký tự trong tài liệu được so sánh sẽ được phân tích để tìm ra sự khác biệt. Kết quả so sánh sẽ thể hiện những thay đổi ở cấp độ ký tự riêng lẻ, bao gồm bổ sung, xóa, sửa đổi.
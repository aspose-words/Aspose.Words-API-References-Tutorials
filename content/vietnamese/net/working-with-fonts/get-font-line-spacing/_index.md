---
title: Nhận khoảng cách dòng phông chữ
linktitle: Nhận khoảng cách dòng phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, hãy tìm hiểu cách lấy khoảng cách dòng phông chữ trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/get-font-line-spacing/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách lấy khoảng cách dòng phông chữ trong tài liệu Word bằng thư viện Aspose.Words cho .NET. Khoảng cách dòng phông chữ xác định khoảng cách dọc giữa các dòng văn bản. Chúng tôi sẽ hướng dẫn bạn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của mình.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn

## Bước 1: Tạo tài liệu mới và trình tạo tài liệu
 Đầu tiên, chúng ta sẽ tạo một tài liệu mới bằng cách khởi tạo`Document` lớp và trình tạo tài liệu bằng cách khởi tạo`DocumentBuilder` lớp học.

```csharp
// Tạo một tài liệu mới
Document doc = new Document();

//Tạo một trình tạo tài liệu
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Cấu hình phông chữ
 Tiếp theo, chúng ta sẽ định cấu hình phông chữ bằng cách đặt`Name` thuộc tính của trình tạo tài liệu.

```csharp
// Định cấu hình phông chữ
builder.Font.Name = "Calibri";
```

## Bước 3: Thêm văn bản vào tài liệu
Bây giờ chúng ta sẽ sử dụng trình tạo tài liệu để thêm văn bản được định dạng vào tài liệu.

```csharp
// Thêm văn bản vào tài liệu
builder. Writen("qText");
```

## Bước 4: Nhận khoảng cách dòng phông chữ
 Bây giờ chúng ta sẽ truy cập vào`Font` đối tượng của đoạn đầu tiên của tài liệu và lấy giá trị của`LineSpacing` tài sản.

```csharp
// Lấy khoảng cách dòng của phông chữ
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Mã nguồn mẫu cho Nhận khoảng cách dòng phông chữ bằng Aspose.Words cho .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã biết cách lấy khoảng cách dòng phông chữ trong tài liệu Word bằng Aspose.Words cho .NET. Khoảng cách dòng phông chữ rất quan trọng để kiểm soát khoảng cách dọc giữa các dòng văn bản. Hãy thoải mái sử dụng tính năng này để tùy chỉnh giao diện của văn bản trong tài liệu của bạn.

### Câu hỏi thường gặp

#### Hỏi: Làm cách nào để thay đổi khoảng cách dòng của văn bản cụ thể trong tài liệu Word?

Trả lời: Với Aspose.Words, bạn có thể dễ dàng thay đổi khoảng cách dòng của văn bản cụ thể trong tài liệu Word. Sử dụng API để chọn văn bản mong muốn và điều chỉnh khoảng cách giữa các dòng bằng cách chỉ định giá trị phù hợp.

#### Hỏi: Có thể áp dụng khoảng cách chính xác giữa các dòng trong tài liệu Word không?

Trả lời: Có, Aspose.Words cho phép bạn áp dụng khoảng cách chính xác giữa các dòng trong tài liệu Word. Bạn có thể chỉ định giá trị chính xác cho khoảng cách dòng bằng API.

#### Hỏi: Làm cách nào tôi có thể điều chỉnh khoảng cách dòng cho toàn bộ tài liệu Word?

Trả lời: Với Aspose.Words, bạn có thể dễ dàng điều chỉnh khoảng cách dòng cho toàn bộ tài liệu Word. Sử dụng các phương pháp do API cung cấp để chỉ định khoảng cách dòng mong muốn cho toàn bộ tài liệu.

#### Câu hỏi: Aspose.Words có hỗ trợ giãn cách nhiều dòng không?

Trả lời: Có, Aspose.Words hỗ trợ giãn cách nhiều dòng trong tài liệu Word. Bạn có thể đặt nhiều khoảng cách, chẳng hạn như khoảng cách bình thường 1,5 lần hoặc 2 lần cho các dòng văn bản của mình.

#### Câu hỏi: Làm cách nào để tránh các vấn đề chồng chéo dòng khi điều chỉnh giãn cách dòng?

Đáp: Để tránh các vấn đề chồng chéo dòng khi điều chỉnh khoảng cách giữa các dòng, hãy đảm bảo chọn các giá trị giãn cách thích hợp. Đồng thời kiểm tra kết xuất cuối cùng của tài liệu của bạn để đảm bảo rằng văn bản vẫn có thể đọc được và được định dạng tốt.
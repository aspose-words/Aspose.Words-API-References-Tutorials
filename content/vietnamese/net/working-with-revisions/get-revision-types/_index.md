---
title: Nhận sửa đổi các loại từ
linktitle: Nhận sửa đổi các loại từ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách lấy các loại từ sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước này giúp bạn xử lý các bản sửa đổi tài liệu một cách hiệu quả.
type: docs
weight: 10
url: /vi/net/working-with-revisions/get-revision-types/
---
## Giới thiệu

Bạn đã bao giờ thấy mình ngập đầu trong biển sửa đổi tài liệu, tự hỏi ai đã di chuyển cái gì và khi nào? Bạn không đơn độc. Xử lý các bản sửa đổi tài liệu có thể là một công việc tẻ nhạt, đặc biệt khi xử lý các tài liệu có phạm vi rộng. Nhưng đừng lo lắng! Với Aspose.Words for .NET, bạn có thể dễ dàng xác định và quản lý các bản sửa đổi này. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước về cách lấy các loại từ sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET. Vì vậy, hãy thắt dây an toàn và cùng lao vào!

## Điều kiện tiên quyết

Trước khi bắt tay vào làm một số mã, bạn sẽ cần một số thứ:

1.  Aspose.Words for .NET Library: Nếu bạn chưa có, hãy tải xuống từ[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ IDE tương thích .NET nào khác.
3. Kiến thức cơ bản về C#: Hiểu biết về ngôn ngữ lập trình C# sẽ có lợi.
4.  Tài liệu Word có bản sửa đổi: Đảm bảo bạn có`.docx`tệp có các thay đổi được theo dõi để kiểm tra mã.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Điều này sẽ cho phép bạn truy cập các chức năng do Aspose.Words cung cấp cho .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

Hãy chia ví dụ thành nhiều bước để hiểu và thực hiện tốt hơn.

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, bạn cần xác định đường dẫn đến thư mục tài liệu của mình. Đây là nơi chứa tài liệu Word có sửa đổi của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tải tài liệu Word của bạn

Tiếp theo, bạn cần tải tài liệu Word vào dự án của mình. Tài liệu này phải có những bản sửa đổi mà bạn muốn phân tích.

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

 Đảm bảo rằng tập tin`Revisions.docx` tồn tại trong thư mục được chỉ định.

## Bước 3: Truy cập Bộ sưu tập đoạn văn

Bây giờ tài liệu của bạn đã được tải, bạn cần truy cập các đoạn văn trong phần đầu tiên của nội dung tài liệu. Điều này sẽ giúp bạn lặp lại từng đoạn để kiểm tra các bản sửa đổi.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## Bước 4: Lặp lại các đoạn văn và kiểm tra các bản sửa đổi

Đây là nơi phép thuật xảy ra. Bạn sẽ lặp lại từng đoạn văn và kiểm tra xem nó đã được di chuyển (xóa hay chèn) chưa.

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

 Vòng lặp này đi qua từng đoạn và sử dụng`IsMoveFromRevision`Và`IsMoveToRevision` thuộc tính để xác định xem đoạn văn đã được di chuyển (xóa) hay di chuyển (chèn).

## Phần kết luận

Và bạn có nó! Chỉ với một vài dòng mã, bạn có thể dễ dàng xác định các loại bản sửa đổi trong tài liệu Word của mình bằng Aspose.Words cho .NET. Thư viện mạnh mẽ này giúp việc xử lý các bản sửa đổi tài liệu trở nên dễ dàng, cho phép bạn tập trung vào các nhiệm vụ quan trọng hơn. 

## Câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Words cho .NET để theo dõi các thay đổi do người dùng cụ thể thực hiện không?

Có, Aspose.Words for .NET cung cấp chức năng truy cập chi tiết sửa đổi, bao gồm cả tác giả của các thay đổi.

### Có bản dùng thử miễn phí dành cho Aspose.Words cho .NET không?

 Tuyệt đối! Bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).

### Làm cách nào tôi có thể xin giấy phép tạm thời cho Aspose.Words cho .NET?

 Bạn có thể yêu cầu và xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể tìm tài liệu chi tiết hơn về Aspose.Words cho .NET ở đâu?

 Tài liệu chi tiết có sẵn trên[trang web giả định](https://reference.aspose.com/words/net/).

### Tôi có thể sử dụng Aspose.Words cho .NET trong một dự án phi thương mại không?

Có, Aspose.Words for .NET có thể được sử dụng trong cả dự án thương mại và phi thương mại, nhưng hãy đảm bảo kiểm tra các điều khoản cấp phép.
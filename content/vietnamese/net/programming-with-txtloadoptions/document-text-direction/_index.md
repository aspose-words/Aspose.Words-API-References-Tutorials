---
title: Hướng văn bản tài liệu
linktitle: Hướng văn bản tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt hướng văn bản tài liệu trong Word bằng Aspose.Words cho .NET với hướng dẫn từng bước này. Hoàn hảo để xử lý các ngôn ngữ từ phải sang trái.
type: docs
weight: 10
url: /vi/net/programming-with-txtloadoptions/document-text-direction/
---
## Giới thiệu

Khi làm việc với tài liệu Word, đặc biệt là những tài liệu chứa nhiều ngôn ngữ hoặc có nhu cầu định dạng đặc biệt, việc đặt hướng văn bản có thể rất quan trọng. Ví dụ: khi xử lý các ngôn ngữ từ phải sang trái như tiếng Do Thái hoặc tiếng Ả Rập, bạn có thể cần điều chỉnh hướng văn bản cho phù hợp. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách đặt hướng văn bản tài liệu bằng Aspose.Words cho .NET. 

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có những điều sau:

-  Thư viện Aspose.Words for .NET: Đảm bảo bạn đã cài đặt Aspose.Words for .NET. Bạn có thể tải nó xuống từ[trang web giả định](https://releases.aspose.com/words/net/).
- Visual Studio: Môi trường phát triển để viết và thực thi mã C#.
- Kiến thức cơ bản về C#: Làm quen với lập trình C# sẽ có ích vì chúng ta sẽ viết một số mã.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các không gian tên cần thiết để làm việc với Aspose.Words trong dự án của mình. Đây là cách bạn có thể làm điều đó:

```csharp
using Aspose.Words;
using Aspose.Words.Loading;
```

Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để thao tác với tài liệu Word.

## Bước 1: Xác định đường dẫn đến thư mục tài liệu của bạn

Đầu tiên, thiết lập đường dẫn đến nơi chứa tài liệu của bạn. Điều này rất quan trọng để tải và lưu tập tin một cách chính xác.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi tài liệu của bạn được lưu trữ.

## Bước 2: Tạo TxtLoadOptions với Cài đặt hướng tài liệu

 Tiếp theo, bạn sẽ cần tạo một phiên bản của`TxtLoadOptions` và thiết lập nó`DocumentDirection` tài sản. Điều này cho Aspose.Words biết cách xử lý hướng văn bản trong tài liệu.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };
```

 Trong ví dụ này, chúng tôi sử dụng`DocumentDirection.Auto` để Aspose.Words tự động xác định hướng dựa trên nội dung.

## Bước 3: Tải tài liệu

 Bây giờ, hãy tải tài liệu bằng cách sử dụng`Document` lớp và được xác định trước đó`loadOptions`.

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Đây,`"Hebrew text.txt"` là tên của tập tin văn bản của bạn. Đảm bảo tệp này tồn tại trong thư mục được chỉ định của bạn.

## Bước 4: Truy cập và kiểm tra định dạng hai chiều của đoạn văn

Để xác nhận rằng hướng văn bản được đặt chính xác, hãy truy cập đoạn đầu tiên của tài liệu và kiểm tra định dạng hai chiều của nó.

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

Bước này hữu ích cho việc gỡ lỗi và xác minh rằng hướng văn bản của tài liệu đã được áp dụng như mong đợi.

## Bước 5: Lưu tài liệu với cài đặt mới

Cuối cùng, lưu tài liệu để áp dụng và duy trì các thay đổi.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Đây,`"WorkingWithTxtLoadOptions.DocumentTextDirection.docx"` là tên của tập tin đầu ra. Đảm bảo chọn tên phản ánh những thay đổi bạn đã thực hiện.

## Phần kết luận

Đặt hướng văn bản trong tài liệu Word là một quá trình đơn giản với Aspose.Words dành cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng định cấu hình cách tài liệu của bạn xử lý văn bản từ phải sang trái hoặc từ trái sang phải. Cho dù bạn đang làm việc với tài liệu đa ngôn ngữ hay cần định dạng hướng văn bản cho các ngôn ngữ cụ thể, Aspose.Words đều cung cấp giải pháp mạnh mẽ để đáp ứng nhu cầu của bạn.

## Câu hỏi thường gặp

###  cái gì là`DocumentDirection` property used for?

 Các`DocumentDirection` tài sản ở`TxtLoadOptions` xác định hướng văn bản cho tài liệu. Nó có thể được đặt thành`DocumentDirection.Auto`, `DocumentDirection.LeftToRight` , hoặc`DocumentDirection.RightToLeft`.

### Tôi có thể đặt hướng văn bản cho các đoạn cụ thể thay vì toàn bộ tài liệu không?

 Có, bạn có thể đặt hướng văn bản cho các đoạn văn cụ thể bằng cách sử dụng`ParagraphFormat.Bidi` tài sản, nhưng`TxtLoadOptions.DocumentDirection` thuộc tính đặt hướng mặc định cho toàn bộ tài liệu.

###  Những định dạng tệp nào được hỗ trợ để tải với`TxtLoadOptions`?

`TxtLoadOptions` được sử dụng chủ yếu để tải các tệp văn bản (.txt). Đối với các định dạng tệp khác, hãy sử dụng các lớp khác nhau như`DocLoadOptions` hoặc`DocxLoadOptions`.

### Làm cách nào tôi có thể xử lý các tài liệu có hướng văn bản hỗn hợp?

 Đối với các tài liệu có hướng văn bản hỗn hợp, bạn có thể cần xử lý định dạng trên cơ sở từng đoạn văn. Sử dụng`ParagraphFormat.Bidi` thuộc tính để điều chỉnh hướng của từng đoạn nếu cần.

### Tôi có thể tìm thêm thông tin về Aspose.Words cho .NET ở đâu?

 Để biết thêm chi tiết, hãy xem[Aspose.Words cho tài liệu .NET](https://reference.aspose.com/words/net/) . Bạn cũng có thể khám phá các tài nguyên bổ sung như[Liên kết tải xuống](https://releases.aspose.com/words/net/), [Mua](https://purchase.aspose.com/buy), [Dùng thử miễn phí](https://releases.aspose.com/), [Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) , Và[Ủng hộ](https://forum.aspose.com/c/words/8).
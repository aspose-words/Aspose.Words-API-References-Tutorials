---
title: Hướng văn bản tài liệu
linktitle: Hướng văn bản tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chỉ định hướng văn bản trong tài liệu của bạn bằng Aspose.Words for .NET. Cải thiện hiển thị cho các ngôn ngữ từ phải sang trái.
type: docs
weight: 10
url: /vi/net/programming-with-txtloadoptions/document-text-direction/
---

Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp cho tính năng "Hướng văn bản tài liệu" với Aspose.Words cho .NET. Tính năng này cho phép bạn chỉ định hướng của văn bản trong tài liệu, điều này đặc biệt hữu ích cho các ngôn ngữ được viết từ phải sang trái, chẳng hạn như tiếng Do Thái hoặc tiếng Ả Rập.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập môi trường phát triển của mình với Aspose.Words for .NET. Đảm bảo bạn đã thêm các tham chiếu cần thiết và nhập các không gian tên thích hợp.

## Bước 2: Định cấu hình tùy chọn tải lên

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn tải tài liệu. Chúng tôi tạo ra một cái mới`TxtLoadOptions` đối tượng và thiết lập`DocumentDirection`tài sản để`DocumentDirection.Auto`. Giá trị này yêu cầu Aspose.Words tự động xác định hướng văn bản dựa trên nội dung của tài liệu.

## Bước 3: Tải tài liệu

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Ở bước này, chúng ta tải tài liệu bằng cách sử dụng`Document` phương thức và chuyển đường dẫn đến tệp văn bản để tải. Chúng tôi cũng sử dụng các tùy chọn tải được chỉ định.

## Bước 4: Thao tác với đoạn văn và hiển thị hướng văn bản

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Trong bước này, chúng ta truy cập đoạn đầu tiên của tài liệu bằng cách sử dụng`FirstSection`Và`Body` của cải. Tiếp theo, chúng ta truy cập vào`ParagraphFormat.Bidi` thuộc tính để lấy hướng văn bản của đoạn văn. Sau đó chúng tôi hiển thị giá trị này trong bảng điều khiển.

## Bước 5: Lưu tài liệu

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Ở bước cuối cùng này, chúng tôi lưu tài liệu kết quả ở định dạng .docx bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra.

Bây giờ bạn có thể chạy mã nguồn để tải tài liệu văn bản và xác định hướng văn bản. Tài liệu thu được sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Mã nguồn mẫu cho chức năng định hướng văn bản của tài liệu với Aspose.Words for .NET.


```csharp

            
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá tính năng hướng văn bản tài liệu trong Aspose.Words dành cho .NET. Chúng tôi đã học cách chỉ định hướng của văn bản trong tài liệu, đặc biệt đối với các ngôn ngữ được viết từ phải sang trái, chẳng hạn như tiếng Do Thái hoặc tiếng Ả Rập.

Tính năng này rất cần thiết để đảm bảo văn bản được hiển thị chính xác trong tài liệu đa ngôn ngữ. Bằng cách sử dụng các tùy chọn tải thích hợp, Aspose.Words có thể tự động phát hiện hướng của văn bản và áp dụng hướng đó cho tài liệu.

Với Aspose.Words, bạn có thể dễ dàng thao tác với hướng văn bản trong tài liệu của mình, mang lại trải nghiệm đọc mượt mà và trực quan cho người dùng.

Điều quan trọng cần lưu ý là tính năng này đặc biệt hữu ích khi Xử lý văn bản với các ngôn ngữ yêu cầu hướng văn bản cụ thể. Aspose.Words làm cho công việc này trở nên dễ dàng bằng cách cung cấp các công cụ mạnh mẽ để quản lý hướng văn bản trong tài liệu của bạn.

Hãy nhớ sử dụng các tùy chọn tải thích hợp, chẳng hạn như đặt hướng văn bản tự động, để có được kết quả bạn muốn trong tài liệu của mình.

Aspose.Words for .NET cung cấp nhiều tính năng nâng cao để thao tác và tạo tài liệu. Bằng cách khám phá sâu hơn các tài liệu và ví dụ do Aspose.Words cung cấp, bạn sẽ có thể khai thác triệt để các khả năng của thư viện mạnh mẽ này.

Vì vậy, đừng ngần ngại tích hợp hướng văn bản tài liệu vào các dự án Aspose.Words for .NET của bạn và tận dụng lợi ích của nó để tạo ra các tài liệu đa ngôn ngữ hấp dẫn và chất lượng cao.
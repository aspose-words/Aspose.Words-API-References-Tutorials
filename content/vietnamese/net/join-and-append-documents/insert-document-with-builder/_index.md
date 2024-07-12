---
title: Chèn tài liệu bằng Builder
linktitle: Chèn tài liệu bằng Builder
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hợp nhất hai tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước để chèn tài liệu bằng DocumentBuilder và giữ nguyên định dạng.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/insert-document-with-builder/
---
## Giới thiệu

Như vậy, bạn đã có hai tài liệu Word và bạn đang muốn hợp nhất chúng thành một. Bạn có thể đang nghĩ: "Có cách nào dễ dàng để thực hiện việc này theo chương trình không?" Tuyệt đối! Hôm nay, tôi sẽ hướng dẫn bạn quy trình chèn tài liệu này vào tài liệu khác bằng thư viện Aspose.Words cho .NET. Phương pháp này cực kỳ tiện dụng, đặc biệt khi bạn đang xử lý các tài liệu lớn hoặc cần tự động hóa quy trình. Hãy đi sâu vào ngay!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có mọi thứ bạn cần:

1.  Aspose.Words for .NET: Nếu chưa có, bạn có thể tải xuống từ[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Đảm bảo bạn đã cài đặt Visual Studio hoặc bất kỳ IDE phù hợp nào khác.
3. Kiến thức cơ bản về C#: Làm quen một chút với C# sẽ giúp ích rất nhiều.

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết để truy cập các chức năng của thư viện Aspose.Words. Đây là cách bạn có thể làm điều đó:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Bây giờ chúng ta đã có sẵn các điều kiện tiên quyết, hãy chia nhỏ quy trình theo từng bước.

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước khi bắt đầu viết mã, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là nơi lưu trữ tài liệu nguồn và đích của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi tài liệu của bạn được đặt. Điều này sẽ giúp chương trình tìm thấy các tập tin của bạn một cách dễ dàng.

## Bước 2: Tải tài liệu nguồn và đích

Tiếp theo, chúng ta cần tải các tài liệu mà chúng ta muốn làm việc. Trong ví dụ này, chúng ta có tài liệu nguồn và tài liệu đích.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Ở đây, chúng tôi đang sử dụng`Document` class từ thư viện Aspose.Words để tải tài liệu của chúng tôi. Đảm bảo tên tệp khớp với tên trong thư mục của bạn.

## Bước 3: Tạo đối tượng DocumentBuilder

 Các`DocumentBuilder` lớp là một công cụ mạnh mẽ trong thư viện Aspose.Words. Nó cho phép chúng ta điều hướng và thao tác với tài liệu.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 Ở bước này, chúng ta đã tạo một`DocumentBuilder` đối tượng cho tài liệu đích của chúng tôi. Điều này sẽ giúp chúng ta chèn nội dung vào tài liệu.

## Bước 4: Di chuyển đến cuối tài liệu

Chúng ta cần di chuyển con trỏ trình tạo đến cuối tài liệu đích trước khi chèn tài liệu nguồn.

```csharp
builder.MoveToDocumentEnd();
```

Điều này đảm bảo rằng tài liệu nguồn được chèn vào cuối tài liệu đích.

## Bước 5: Chèn ngắt trang

Để giữ mọi thứ gọn gàng, hãy thêm dấu ngắt trang trước khi chèn tài liệu nguồn. Điều này sẽ bắt đầu nội dung của tài liệu nguồn trên một trang mới.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Ngắt trang đảm bảo rằng nội dung tài liệu nguồn bắt đầu trên một trang mới, làm cho tài liệu được hợp nhất trông chuyên nghiệp.

## Bước 6: Chèn tài liệu nguồn

Bây giờ đến phần thú vị—thực sự là chèn tài liệu nguồn vào tài liệu đích.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 Sử dụng`InsertDocument` phương pháp này, chúng ta có thể chèn toàn bộ tài liệu nguồn vào tài liệu đích. Các`ImportFormatMode.KeepSourceFormatting` đảm bảo rằng định dạng của tài liệu nguồn được giữ nguyên.

## Bước 7: Lưu tài liệu đã hợp nhất

Cuối cùng, hãy lưu tài liệu đã hợp nhất. Điều này sẽ kết hợp các tài liệu nguồn và đích vào một tệp.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Bằng cách lưu tài liệu, chúng tôi hoàn thành quá trình hợp nhất hai tài liệu. Tài liệu mới của bạn hiện đã sẵn sàng và được lưu trong thư mục được chỉ định.

## Phần kết luận

Và bạn có nó rồi đấy! Bạn đã chèn thành công tài liệu này vào tài liệu khác bằng Aspose.Words for .NET. Phương pháp này không chỉ hiệu quả mà còn giữ nguyên định dạng của cả hai tài liệu, đảm bảo việc hợp nhất liền mạch. Cho dù bạn đang làm việc trên một dự án một lần hay cần tự động xử lý tài liệu, Aspose.Words for .NET đều có thể giúp bạn.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?  
Aspose.Words for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa, chuyển đổi và thao tác các tài liệu Word theo chương trình.

### Tôi có thể giữ nguyên định dạng của tài liệu nguồn không?  
 Có, bằng cách sử dụng`ImportFormatMode.KeepSourceFormatting`, định dạng của tài liệu nguồn được giữ nguyên khi nó được chèn vào tài liệu đích.

### Tôi có cần giấy phép để sử dụng Aspose.Words cho .NET không?  
 Có, Aspose.Words for .NET yêu cầu giấy phép để có đầy đủ chức năng. Bạn có thể nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.

### Tôi có thể tự động hóa quá trình này không?  
Tuyệt đối! Phương pháp được mô tả có thể được tích hợp vào các ứng dụng lớn hơn để tự động hóa các tác vụ xử lý tài liệu.

### Tôi có thể tìm thêm tài nguyên và hỗ trợ ở đâu?  
Để biết thêm thông tin, bạn có thể kiểm tra[tài liệu](https://reference.aspose.com/words/net/) , hoặc ghé thăm[diễn đàn hỗ trợ](https://forum.aspose.com/c/words/8) để được hỗ trợ.
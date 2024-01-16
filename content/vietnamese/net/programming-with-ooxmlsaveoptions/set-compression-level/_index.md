---
title: Đặt mức nén
linktitle: Đặt mức nén
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt mức nén khi lưu tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp để đặt mức nén khi lưu tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn kiểm soát mức độ nén của tài liệu được tạo.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập môi trường phát triển của mình với Aspose.Words for .NET. Đảm bảo bạn đã thêm các tham chiếu cần thiết và nhập các không gian tên thích hợp.

## Bước 2: Tải tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Ở bước này, chúng ta tải tài liệu bằng cách sử dụng`Document` phương thức và chuyển đường dẫn đến tệp DOCX để tải.

## Bước 3: Định cấu hình tùy chọn sao lưu OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn lưu OOXML bằng cách sử dụng`OoxmlSaveOptions` lớp học. Chúng tôi đặt mức nén thành`SuperFast` để nén nhanh hơn.

## Bước 4: Lưu tài liệu với mức nén quy định

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Ở bước cuối cùng này, chúng tôi lưu tài liệu bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra bằng`.docx` tiện ích mở rộng, cùng với các tùy chọn lưu được chỉ định.

Bây giờ bạn có thể chạy mã nguồn để đặt mức nén khi lưu tài liệu. Tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Mã nguồn mẫu cho Đặt mức nén bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá chức năng đặt mức nén khi lưu tài liệu bằng Aspose.Words cho .NET. Bằng cách chỉ định mức nén thích hợp, bạn có thể tối ưu hóa kích thước tài liệu và tốc độ tạo.

 Các`OoxmlSaveOptions` lớp cung cấp sự linh hoạt để kiểm soát mức độ nén bằng cách thiết lập`CompressionLevel` thuộc tính thành một giá trị thích hợp, chẳng hạn như`SuperFast`. Điều này cho phép bạn đạt được sự cân bằng phù hợp giữa kích thước tệp và tốc độ sao lưu dựa trên nhu cầu cụ thể của bạn.

Sử dụng tính năng nén có thể có lợi khi bạn cần giảm kích thước tệp được tạo, đặc biệt đối với các tài liệu lớn. Điều này có thể giúp việc lưu trữ, chia sẻ và truyền tải tài liệu trở nên dễ dàng hơn.

Aspose.Words for .NET cung cấp nhiều tùy chọn và tính năng mạnh mẽ để thao tác tài liệu. Bằng cách sử dụng các tùy chọn sao lưu thích hợp, bạn có thể tùy chỉnh quy trình tạo tài liệu và tối ưu hóa hiệu suất ứng dụng của mình.

Vui lòng khám phá thêm các tính năng của Aspose.Words for .NET để nâng cao quy trình tạo tài liệu của bạn.

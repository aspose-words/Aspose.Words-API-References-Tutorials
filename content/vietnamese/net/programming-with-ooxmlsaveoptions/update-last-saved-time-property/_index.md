---
title: Cập nhật thuộc tính thời gian đã lưu lần cuối
linktitle: Cập nhật thuộc tính thời gian đã lưu lần cuối
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tự động cập nhật thuộc tính Thời gian lưu lần cuối khi lưu tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp để cập nhật thuộc tính tiết kiệm thời gian cuối cùng khi lưu tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn tự động cập nhật thuộc tính thời gian lưu cuối cùng của tài liệu được tạo.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn lưu OOXML bằng cách sử dụng`OoxmlSaveOptions` lớp học. Chúng tôi cho phép cập nhật tự động thuộc tính thời gian lưu cuối cùng bằng cách cài đặt`UpdateLastSavedTimeProperty` ĐẾN`true`.

## Bước 4: Lưu tài liệu với thuộc tính được cập nhật

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Ở bước cuối cùng này, chúng tôi lưu tài liệu bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra bằng`.docx` tiện ích mở rộng, cùng với các tùy chọn lưu được chỉ định.

Bây giờ bạn có thể chạy mã nguồn để tự động cập nhật thuộc tính tiết kiệm thời gian cuối cùng khi lưu tài liệu. Tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Mã nguồn mẫu để cập nhật thuộc tính thời gian đã lưu lần cuối bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá tính năng tự động cập nhật thuộc tính tiết kiệm thời gian cuối cùng khi lưu tài liệu bằng Aspose.Words cho .NET. Bằng cách bật tính năng này với các tùy chọn lưu OOXML, bạn có thể đảm bảo rằng thuộc tính tiết kiệm thời gian cuối cùng được cập nhật tự động trong tài liệu được tạo.

Việc cập nhật thuộc tính lưu thời gian cuối cùng có thể hữu ích cho việc theo dõi các thay đổi và phiên bản của tài liệu. Nó cũng theo dõi thời điểm tài liệu được lưu lần cuối, điều này có thể hữu ích trong nhiều trường hợp khác nhau.

Aspose.Words for .NET giúp dễ dàng tự động cập nhật thuộc tính Thời gian sao lưu cuối cùng bằng cách cung cấp các tùy chọn sao lưu linh hoạt và mạnh mẽ. Bạn có thể tích hợp tính năng này vào các dự án của mình để đảm bảo rằng các tài liệu được tạo có thông tin sao lưu chính xác.
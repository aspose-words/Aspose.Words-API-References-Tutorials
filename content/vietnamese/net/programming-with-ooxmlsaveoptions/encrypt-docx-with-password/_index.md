---
title: Mã hóa Docx bằng mật khẩu
linktitle: Mã hóa Docx bằng mật khẩu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách mã hóa tệp DOCX bằng mật khẩu bằng Aspose.Words cho .NET. Hướng dẫn đầy đủ về bảo mật tài liệu.
type: docs
weight: 10
url: /vi/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp để mã hóa tệp DOCX bằng mật khẩu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn bảo vệ tài liệu của mình bằng cách chỉ có thể truy cập tài liệu bằng mật khẩu được chỉ định.

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn lưu OOXML bằng cách tạo một`OoxmlSaveOptions` sự vật. Chúng tôi chỉ định mật khẩu mong muốn để mã hóa tài liệu bằng cách đặt`Password` property vào mật khẩu tùy chỉnh của bạn.

## Bước 4: Mã hóa tài liệu bằng mật khẩu

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

 Ở bước cuối cùng này, chúng tôi lưu tài liệu bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra bằng`.docx` tiện ích mở rộng, cùng với các tùy chọn lưu được chỉ định.

Bây giờ bạn có thể chạy mã nguồn để mã hóa tài liệu DOCX của mình bằng mật khẩu. Tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx". Hãy đảm bảo giữ mật khẩu của bạn an toàn vì nó sẽ cần thiết để mở tài liệu được mã hóa.

### Mã nguồn mẫu cho Mã hóa Docx bằng mật khẩu bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá chức năng mã hóa tệp DOCX bằng mật khẩu bằng Aspose.Words cho .NET. Chúng tôi đã học cách bảo vệ tài liệu của mình bằng cách làm cho chúng chỉ có thể truy cập được bằng mật khẩu được chỉ định.

Mã hóa tài liệu là một biện pháp bảo mật thiết yếu để bảo vệ thông tin nhạy cảm. Nhờ Aspose.Words cho .NET, chúng ta có thể dễ dàng thêm chức năng này vào các ứng dụng của mình.

Bằng cách làm theo các bước được cung cấp, bạn có thể tích hợp mã hóa mật khẩu vào các dự án Aspose.Words for .NET và đảm bảo tính bảo mật cho tài liệu của bạn.

Vui lòng thử nghiệm các tính năng khác do Aspose.Words cho .NET cung cấp để làm phong phú thêm ứng dụng của bạn bằng các tính năng thao tác tài liệu nâng cao.

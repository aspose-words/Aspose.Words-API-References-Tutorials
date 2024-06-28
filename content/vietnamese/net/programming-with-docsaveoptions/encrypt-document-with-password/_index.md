---
title: Mã hóa tài liệu bằng mật khẩu
linktitle: Mã hóa tài liệu bằng mật khẩu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách mã hóa tài liệu bằng mật khẩu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Bảo mật tài liệu là điều cần thiết khi Xử lý văn bản với các tệp trong ứng dụng C#. Với thư viện Aspose.Words dành cho .NET, bạn có thể dễ dàng bảo vệ tài liệu của mình bằng cách mã hóa chúng bằng mật khẩu. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn Aspose.Words cho .NET C# để mã hóa tài liệu bằng cách sử dụng tùy chọn lưu DocSaveOptions.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện mạnh mẽ để tạo, chỉnh sửa, chuyển đổi và bảo vệ tài liệu Word trên các nền tảng khác nhau bao gồm .NET. Nó cung cấp nhiều tính năng để thao tác với tài liệu, chẳng hạn như chèn văn bản, thay đổi định dạng, thêm phần và hơn thế nữa.

## Bước 1: Xác định thư mục tài liệu

Bước đầu tiên là đặt thư mục nơi bạn muốn lưu tài liệu được mã hóa. Bạn phải chỉ định đường dẫn thư mục đầy đủ. Ví dụ :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tạo và chỉnh sửa tài liệu

Sau đó, bạn có thể tạo một tài liệu và thêm nội dung vào đó. Sử dụng lớp DocumentBuilder do Aspose.Words cung cấp để xây dựng nội dung tài liệu của bạn. Ví dụ :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

Trong ví dụ này, chúng tôi tạo một tài liệu trống mới và sau đó sử dụng DocumentBuilder để viết văn bản "Xin chào thế giới!".

## Bước 3: Định cấu hình tùy chọn ghi

Bây giờ hãy định cấu hình các tùy chọn lưu cho tài liệu của chúng tôi. Sử dụng lớp DocSaveOptions để chỉ định cài đặt lưu. Ví dụ :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

Trong ví dụ này, chúng tôi tạo một đối tượng DocSaveOptions mới và đặt thuộc tính Mật khẩu thành "mật khẩu" để mã hóa tài liệu bằng mật khẩu này.

## Bước 4: Kích hoạt tính năng “Mã hóa tài liệu bằng mật khẩu”

Chúng tôi đã cấu hình các tùy chọn cho

đăng ký bằng mật khẩu đã chỉ định, thao tác này sẽ tự động kích hoạt tính năng "Mã hóa tài liệu bằng mật khẩu". Điều này đảm bảo rằng tài liệu được mã hóa bằng mật khẩu được chỉ định khi lưu.

## Bước 5: Lưu tài liệu

Cuối cùng, bạn có thể lưu tài liệu bằng phương thức Save của lớp Document. Chỉ định đường dẫn đầy đủ đến tệp và tên tệp mong muốn. Ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Đảm bảo thay thế "dataDir" bằng đường dẫn thư mục tới tài liệu của bạn.

### Mã nguồn ví dụ cho các tùy chọn lưu DocSaveOptions với chức năng "Mã hóa tài liệu bằng mật khẩu" bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo và chỉnh sửa tài liệu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Định cấu hình tùy chọn lưu với tính năng "Mã hóa tài liệu bằng mật khẩu"
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Lưu tài liệu với các tùy chọn được chỉ định
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách sử dụng thư viện Aspose.Words cho .NET để mã hóa tài liệu bằng mật khẩu bằng cách sử dụng tùy chọn lưu DocSaveOptions. Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng áp dụng chức năng này trong ứng dụng C# của mình. Mã hóa tài liệu bằng mật khẩu đảm bảo tính bảo mật và an toàn khi xử lý nó.
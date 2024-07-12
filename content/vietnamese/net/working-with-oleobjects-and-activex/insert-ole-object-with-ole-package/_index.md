---
title: Chèn đối tượng Ole vào Word bằng gói Ole
linktitle: Chèn đối tượng Ole vào Word bằng gói Ole
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn đối tượng OLE có gói OLE vào tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới minh họa cách chèn đối tượng OLE vào word bằng gói OLE bằng Aspose.Words cho .NET.

## Bước 1: Nhập các tài liệu tham khảo cần thiết
Trước khi bắt đầu, hãy đảm bảo bạn đã nhập các tham chiếu cần thiết để sử dụng Aspose.Words cho .NET vào dự án của mình. Điều này bao gồm việc nhập thư viện Aspose.Words và thêm các không gian tên cần thiết vào tệp nguồn của bạn.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Bước 2: Tạo tài liệu mới và trình tạo tài liệu
 Trong bước này, chúng ta sẽ tạo một tài liệu mới bằng cách sử dụng`Document` lớp và trình tạo tài liệu bằng cách sử dụng`DocumentBuilder` lớp học.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn đối tượng OLE bằng gói OLE
 Sử dụng Trình tạo tài liệu`InsertOleObject` phương pháp chèn một đối tượng OLE với gói OLE vào tài liệu. Chỉ định luồng dữ liệu, loại đối tượng, tùy chọn hiển thị và các cài đặt cần thiết khác.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Bước 4: Lưu tài liệu
 Sử dụng tài liệu`Save` phương pháp lưu tài liệu vào một tập tin.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Mã nguồn mẫu để chèn đối tượng OLE bằng gói OLE với Aspose.Words cho .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Đây là mẫu mã hoàn chỉnh để chèn đối tượng OLE bằng gói OLE với Aspose.Words cho .NET. Hãy nhớ nhập các tài liệu tham khảo cần thiết và làm theo các bước được mô tả trước đó để tích hợp mã này vào dự án của bạn.

## Phần kết luận

Để kết luận, chúng tôi đã thực hiện hướng dẫn từng bước để chèn đối tượng OLE vào tài liệu Word có gói OLE bằng Aspose.Words cho .NET.

Bằng cách làm theo các bước này, bạn sẽ có thể chèn thành công các đối tượng OLE với các gói OLE vào tài liệu Word của mình bằng Aspose.Words for .NET. Hãy nhớ nhập các tài liệu tham khảo cần thiết và làm theo hướng dẫn cẩn thận để có được kết quả mong muốn.

### Câu hỏi thường gặp về chèn đối tượng ole vào word bằng gói ole

#### Câu hỏi: Tôi cần nhập thông tin xác thực nào để sử dụng Aspose.Words cho .NET?

Trả lời: Để sử dụng Aspose.Words cho .NET, bạn cần nhập các tài liệu tham khảo sau:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Hỏi: Làm cách nào để tạo một tài liệu mới và một trình tạo tài liệu?

 Đáp: Bạn có thể tạo một tài liệu mới bằng cách sử dụng`Document` lớp và trình tạo tài liệu bằng cách sử dụng`DocumentBuilder` lớp, như được hiển thị dưới đây:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Câu hỏi: Làm cách nào để chèn đối tượng OLE có gói OLE vào tài liệu?

 Đáp: Hãy sử dụng`InsertOleObject`phương pháp của người xây dựng tài liệu (`DocumentBuilder`) để chèn một đối tượng OLE có gói OLE vào tài liệu. Chỉ định luồng dữ liệu, loại đối tượng, tùy chọn hiển thị và các cài đặt cần thiết khác. Đây là một ví dụ :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Hỏi: Làm thế nào để lưu tài liệu?

 A: Sử dụng tài liệu`Save` phương pháp lưu tài liệu vào một tập tin. Đây là một ví dụ :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Câu hỏi: Bạn có thể cung cấp ví dụ hoàn chỉnh về cách chèn đối tượng OLE bằng gói OLE bằng Aspose.Words cho .NET không?

Trả lời: Đây là mã mẫu hoàn chỉnh để chèn đối tượng OLE bằng gói OLE bằng Aspose.Words cho .NET. Hãy đảm bảo nhập các tài liệu tham khảo cần thiết và làm theo các bước được mô tả trước đây để tích hợp mã này vào dự án của bạn:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Phần này kết thúc hướng dẫn của chúng tôi về cách chèn đối tượng OLE với gói OLE vào tài liệu Word bằng Aspose.Words cho .NET. Vui lòng nhập các tài liệu tham khảo cần thiết và làm theo các bước được mô tả để tích hợp mã này vào dự án của bạn. Nếu bạn có bất kỳ câu hỏi nào, xin vui lòng liên hệ với chúng tôi.
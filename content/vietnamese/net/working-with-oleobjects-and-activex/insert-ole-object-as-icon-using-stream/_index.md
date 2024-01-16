---
title: Chèn đối tượng Ole làm biểu tượng bằng luồng
linktitle: Chèn đối tượng Ole làm biểu tượng bằng luồng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn đối tượng OLE làm biểu tượng bằng luồng với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới minh họa cách chèn đối tượng OLE làm biểu tượng bằng cách sử dụng luồng có Aspose.Words cho .NET.

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

## Bước 3: Chèn đối tượng OLE làm biểu tượng từ luồng
 Sử dụng Trình tạo tài liệu`InsertOleObjectAsIcon` phương pháp chèn đối tượng OLE dưới dạng biểu tượng từ luồng vào tài liệu. Chỉ định luồng dữ liệu, loại đối tượng, đường dẫn biểu tượng và tên đối tượng được nhúng.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Bước 4: Lưu tài liệu
 Sử dụng tài liệu`Save` phương pháp lưu tài liệu vào một tập tin.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Mã nguồn ví dụ để chèn đối tượng OLE làm biểu tượng bằng luồng với Aspose.Words cho .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Đây là mẫu mã hoàn chỉnh để chèn đối tượng OLE làm biểu tượng bằng cách sử dụng luồng có Aspose.Words cho .NET. Hãy nhớ nhập các tài liệu tham khảo cần thiết và làm theo các bước được mô tả trước đó để tích hợp mã này vào dự án của bạn.

## Phần kết luận

Hướng dẫn từng bước ở trên giải thích cách chèn đối tượng OLE làm biểu tượng trong tài liệu Word bằng cách sử dụng luồng với Aspose.Words cho .NET. Bằng cách làm theo các bước được mô tả, bạn sẽ có thể tích hợp chức năng này vào dự án của mình. Đảm bảo nhập các tham chiếu cần thiết, tạo tài liệu mới và trình tạo tài liệu, chèn đối tượng OLE làm biểu tượng từ luồng, sau đó lưu tài liệu. Hãy sử dụng mã mẫu được cung cấp làm điểm bắt đầu và tùy chỉnh mã đó theo nhu cầu của bạn.

### Câu hỏi thường gặp

#### H. Làm cách nào để nhập các tài liệu tham khảo cần thiết để sử dụng Aspose.Words cho .NET?

A. Để nhập các tài liệu tham khảo cần thiết, bạn phải làm theo các bước sau:

 Thêm những điều sau`using` các câu lệnh ở đầu tệp nguồn của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Đảm bảo bạn đã thêm thư viện Aspose.Words vào dự án của mình.

#### H. Làm cách nào để tạo tài liệu và trình tạo tài liệu mới bằng Aspose.Words cho .NET?

A. Để tạo một tài liệu và trình tạo tài liệu mới, bạn có thể làm theo các bước sau:

 Sử dụng`Document` lớp để tạo một tài liệu mới:

```csharp
Document doc = new Document();
```
 Sử dụng`DocumentBuilder`lớp để tạo trình tạo tài liệu được liên kết với tài liệu đã tạo trước đó:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Câu hỏi: Làm cách nào để chèn đối tượng OLE dưới dạng biểu tượng từ luồng bằng Aspose.Words cho .NET?

A. Để chèn đối tượng OLE làm biểu tượng từ luồng, bạn có thể làm theo các bước sau:

 Sử dụng`InsertOleObjectAsIcon` phương thức của trình tạo tài liệu để chèn đối tượng OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q. Làm cách nào để lưu tài liệu vào một tập tin?

A.  Để lưu tài liệu vào một tập tin, bạn có thể sử dụng`Save` phương pháp của tài liệu chỉ định đường dẫn đích:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Câu hỏi: Làm cách nào để nhúng mã để chèn đối tượng OLE làm biểu tượng từ luồng vào dự án của tôi?

A. Để nhúng mã để chèn đối tượng OLE dưới dạng biểu tượng từ luồng vào dự án của bạn, hãy làm theo các bước sau:
-  Nhập các tài liệu tham khảo cần thiết bằng cách thêm thích hợp`using` các câu lệnh.
-  Tạo một tài liệu mới và trình tạo tài liệu bằng cách sử dụng`Document` Và`DocumentBuilder` các lớp học.
- Sử dụng mã để chèn đối tượng OLE làm biểu tượng từ luồng.
-  Lưu tài liệu bằng cách sử dụng`Save` phương pháp với đường dẫn đích thích hợp.

Bằng cách làm theo các bước này, bạn sẽ có thể chèn thành công đối tượng OLE dưới dạng biểu tượng từ luồng bằng Aspose.Words cho .NET. Hãy nhớ làm theo hướng dẫn và nhập các tài liệu tham khảo cần thiết để có được kết quả mong muốn.
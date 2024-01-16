---
title: Chèn đối tượng Ole vào tài liệu Word dưới dạng biểu tượng
linktitle: Chèn đối tượng Ole vào tài liệu Word dưới dạng biểu tượng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn đối tượng OLE vào tài liệu word dưới dạng biểu tượng với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới minh họa cách chèn đối tượng OLE vào tài liệu word dưới dạng biểu tượng bằng cách sử dụng Aspose.Words cho .NET.

## Bước 1: Nhập các tài liệu tham khảo cần thiết
Trước khi bắt đầu, hãy đảm bảo bạn đã nhập các tham chiếu cần thiết để sử dụng Aspose.Words cho .NET vào dự án của mình. Điều này bao gồm việc nhập thư viện Aspose.Words và thêm các không gian tên cần thiết vào tệp nguồn của bạn.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Bước 2: Tạo tài liệu mới và trình tạo tài liệu
 Trong bước này, chúng ta sẽ tạo một tài liệu mới bằng cách sử dụng`Document` lớp và trình tạo tài liệu bằng cách sử dụng`DocumentBuilder` lớp học.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn đối tượng OLE làm biểu tượng
 Sử dụng Trình tạo tài liệu`InsertOleObjectAsIcon`phương pháp chèn một đối tượng OLE làm biểu tượng vào tài liệu. Chỉ định đường dẫn tệp OLE, cờ hiển thị, đường dẫn biểu tượng và tên đối tượng được nhúng.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Bước 4: Lưu tài liệu
 Sử dụng tài liệu`Save` phương pháp lưu tài liệu vào một tập tin.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Mã nguồn ví dụ để chèn đối tượng OLE làm biểu tượng với Aspose.Words cho .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Đây là mẫu mã hoàn chỉnh để chèn đối tượng OLE làm biểu tượng với Aspose.Words dành cho .NET. Hãy nhớ nhập các tài liệu tham khảo cần thiết và làm theo các bước được mô tả trước đó để tích hợp mã này vào dự án của bạn.

## Phần kết luận

Để kết luận, chúng tôi đã khám phá hướng dẫn từng bước để chèn đối tượng OLE làm biểu tượng trong tài liệu Word bằng Aspose.Words cho .NET.

Bằng cách làm theo các bước này, bạn sẽ có thể chèn thành công đối tượng OLE làm biểu tượng trong tài liệu Word của mình bằng Aspose.Words for .NET. Hãy nhớ nhập các tài liệu tham khảo cần thiết và làm theo hướng dẫn cẩn thận để có được kết quả mong muốn.

### Câu hỏi thường gặp về chèn đối tượng ole vào tài liệu word dưới dạng biểu tượng

#### Câu hỏi: Cần có những tham chiếu nào để chèn đối tượng OLE làm biểu tượng trong tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Bạn cần nhập các tài liệu tham khảo sau vào dự án của mình để sử dụng Aspose.Words cho .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### H. Làm cách nào để tạo trình tạo tài liệu và tài liệu mới trong Aspose.Words cho .NET?

 Đáp: Bạn có thể tạo một tài liệu mới bằng cách sử dụng`Document` lớp và trình tạo tài liệu bằng cách sử dụng`DocumentBuilder` lớp học. Đây là một ví dụ :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### H. Làm cách nào để chèn đối tượng OLE làm biểu tượng trong tài liệu?

 Đáp: Sử dụng Trình tạo tài liệu`InsertOleObjectAsIcon` phương pháp chèn một đối tượng OLE làm biểu tượng. Chỉ định đường dẫn tệp OLE, cờ hiển thị, đường dẫn biểu tượng và tên đối tượng được nhúng. Đây là một ví dụ :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### H. Làm cách nào để lưu tài liệu với đối tượng OLE được chèn dưới dạng biểu tượng?

 A: Sử dụng tài liệu`Save` phương pháp lưu tài liệu vào một tập tin. Đây là một ví dụ :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```
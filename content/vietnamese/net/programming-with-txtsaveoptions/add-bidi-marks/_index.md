---
title: Thêm dấu Bidi vào tài liệu Word
linktitle: Thêm dấu Bidi vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm dấu Bidi vào tài liệu Word bằng Aspose.Words cho .NET và tạo tài liệu đa ngôn ngữ chuyên nghiệp.
type: docs
weight: 10
url: /vi/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, chỉnh sửa và thao tác các tài liệu Word trong ứng dụng C#. Trong số các tính năng được Aspose.Words cung cấp là khả năng thêm dấu Bidi (Hai chiều) vào tài liệu. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn C# của Aspose.Words cho .NET để thêm dấu Bidi vào tài liệu.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện phổ biến giúp việc Xử lý văn bản bằng tài liệu Word trở nên dễ dàng và hiệu quả. Nó cung cấp nhiều tính năng để tạo, chỉnh sửa và thao tác với tài liệu Word, bao gồm cả việc thêm dấu Bidi.

## Tạo tài liệu và thêm nội dung

Bước đầu tiên là tạo một tài liệu mới và thêm nội dung vào đó. Sử dụng lớp Tài liệu để tạo một phiên bản tài liệu mới. Sau đó sử dụng lớp DocumentBuilder để thêm văn bản vào tài liệu. Đây là một ví dụ :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

Trong ví dụ này, chúng tôi tạo một tài liệu mới và sử dụng DocumentBuilder để thêm văn bản. Chúng tôi đã thêm ba dòng văn bản: một bằng tiếng Anh, một bằng tiếng Do Thái và một bằng tiếng Ả Rập để minh họa việc thêm nội dung bằng các ngôn ngữ khác nhau.

## Đã thêm dấu Bidi

Sau khi đã thêm nội dung, bây giờ chúng ta có thể thêm dấu Bidi vào tài liệu. Để làm điều này, chúng tôi sử dụng lớp TxtSaveOptions và đặt thuộc tính AddBidiMarks thành true. Đây là cách thực hiện:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Trong ví dụ này, chúng tôi tạo một phiên bản TxtSaveOptions và đặt thuộc tính AddBidiMarks thành true. Tiếp theo, chúng ta sử dụng phương thức Save của lớp Document để lưu tài liệu có dấu Bidi.

### Mã nguồn ví dụ cho chức năng "Thêm nhãn giá thầu" với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và thêm nội dung
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Thêm dấu Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách sử dụng Aspose.Words cho .NET để thêm dấu Bidi vào tài liệu Word bằng mã nguồn C# được cung cấp. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng thêm dấu Bidi vào tài liệu Word trong ứng dụng C# của mình. Aspose.Words cung cấp tính linh hoạt và sức mạnh to lớn cho Xử lý văn bản với định dạng văn bản và quản lý ngôn ngữ, cho phép bạn tạo tài liệu đa ngôn ngữ một cách chuyên nghiệp.

### Các câu hỏi thường gặp

#### Câu hỏi: Aspose.Words dành cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, chỉnh sửa và thao tác các tài liệu Word trong ứng dụng C#. Nó cung cấp nhiều tính năng để Xử lý văn bản với tài liệu Word, bao gồm thêm dấu Bidi (hai chiều).

#### Câu hỏi: Aspose.Words for .NET cung cấp những tính năng gì?
Aspose.Words for .NET cung cấp nhiều tính năng để tạo, chỉnh sửa và thao tác với tài liệu Word. Một số tính năng này bao gồm tạo tài liệu, thêm nội dung, định dạng văn bản, quản lý bảng, hợp nhất và chia tách tài liệu, chuyển đổi tài liệu, v.v.

#### Câu hỏi: Làm cách nào tôi có thể thêm dấu Bidi vào tài liệu Word bằng Aspose.Words cho .NET?
Bạn có thể thêm dấu Bidi vào tài liệu Word bằng cách làm theo các bước sau:

 Tạo một tài liệu mới bằng cách sử dụng`Document` lớp học.

 Sử dụng`DocumentBuilder` class để thêm nội dung vào tài liệu.

 Khi bạn đã thêm nội dung, hãy sử dụng`TxtSaveOptions` lớp và thiết lập`AddBidiMarks`tài sản để`true`.

 Lưu tài liệu có dấu Bidi bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

#### Câu hỏi: Aspose.Words có hỗ trợ nhiều ngôn ngữ để thêm nhãn Bidi không?
Có, Aspose.Words hỗ trợ nhiều ngôn ngữ để thêm nhãn Bidi. Bạn có thể thêm dấu Bidi vào văn bản bằng các ngôn ngữ khác nhau, chẳng hạn như tiếng Anh, tiếng Do Thái và tiếng Ả Rập, bằng cách sử dụng Aspose.Words cho .NET.

#### Hỏi: Có tùy chọn bổ sung nào để lưu tài liệu bằng nhãn Bidi không?
 Có, bạn có thể chỉ định các tùy chọn khác khi lưu tài liệu có dấu Bidi bằng cách sử dụng`TxtSaveOptions` lớp học. Ví dụ: bạn có thể đặt định dạng lưu tài liệu, tùy chọn mã hóa, v.v.
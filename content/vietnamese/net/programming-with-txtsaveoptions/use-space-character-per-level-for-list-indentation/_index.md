---
title: Sử dụng ký tự khoảng trắng trên mỗi cấp độ để thụt danh sách
linktitle: Sử dụng ký tự khoảng trắng trên mỗi cấp độ để thụt danh sách
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước về cách sử dụng ký tự khoảng trắng theo cấp độ để thụt lề danh sách trong Aspose.Words for .NET. Tạo tài liệu Word có cấu trúc tốt một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, chỉnh sửa và thao tác các tài liệu Word trong ứng dụng C#. Trong số các tính năng được Aspose.Words cung cấp là khả năng sử dụng một ký tự khoảng trắng cho mỗi cấp độ để thụt lề danh sách. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# của Aspose.Words cho .NET để triển khai chức năng này.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện phổ biến giúp việc Xử lý văn bản bằng tài liệu Word trở nên dễ dàng và hiệu quả. Nó cung cấp nhiều chức năng để tạo, sửa đổi và thao tác với tài liệu Word, bao gồm quản lý danh sách và thụt lề.

## Tạo tài liệu và thêm nội dung

Bước đầu tiên là tạo một tài liệu mới và thêm nội dung vào đó. Sử dụng lớp Tài liệu để tạo một phiên bản tài liệu mới. Sau đó, sử dụng lớp DocumentBuilder để thêm văn bản và tạo danh sách có nhiều cấp độ thụt lề. Đây là một ví dụ :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tạo danh sách có ba cấp độ thụt lề
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Trong ví dụ này, chúng tôi tạo một tài liệu mới và sử dụng DocumentBuilder để thêm văn bản và tạo danh sách có ba cấp độ thụt lề. Chúng tôi đã thêm ba mục vào danh sách, mỗi mục chỉ ra một cấp độ bổ sung.

## Sử dụng một ký tự khoảng trắng cho mỗi cấp độ để thụt lề danh sách

Sau khi đã thêm nội dung, giờ đây chúng ta có thể định cấu hình thụt lề danh sách bằng cách sử dụng một ký tự khoảng trắng cho mỗi cấp độ. Để làm điều này, chúng tôi sử dụng lớp TxtSaveOptions và đặt thuộc tính ListIndentation.Count thành số mức thụt lề và thuộc tính ListIndentation.Character cho ký tự khoảng trắng sẽ sử dụng. Đây là cách thực hiện:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

Trong ví dụ này, chúng tôi tạo một phiên bản của TxtSaveOptions và đặt thuộc tính ListIndentation.Count thành 3 để cho biết rằng có ba mức thụt lề trong danh sách. Chúng tôi cũng đặt thuộc tính ListIndentation.Character thành ký tự khoảng trắng (' ') mà chúng tôi muốn sử dụng để thụt lề.

### Mã nguồn mẫu cho tính năng "Sử dụng một ký tự khoảng trắng cho mỗi cấp độ để thụt lề danh sách" với Aspose.Words for .NET

Đây là mã nguồn mẫu hoàn chỉnh cho tính năng "Sử dụng một ký tự khoảng trắng cho mỗi cấp độ để thụt lề danh sách" với Aspose.Words dành cho .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Đường dẫn đến thư mục tài liệu của bạn
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Tạo tài liệu và thêm nội dung
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Tạo danh sách có ba cấp độ thụt lề
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Sử dụng một ký tự khoảng trắng cho mỗi cấp độ để thụt lề danh sách
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Lưu tài liệu với các tùy chọn được chỉ định
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách sử dụng Aspose.Words cho .NET để áp dụng chức năng "Sử dụng một ký tự khoảng trắng cho mỗi cấp độ cho thụt lề danh sách". Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng định cấu hình thụt lề danh sách trong tài liệu Word của mình bằng cách sử dụng một ký tự khoảng trắng cho mỗi cấp độ. Aspose.Words cung cấp tính linh hoạt và sức mạnh to lớn cho Xử lý văn bản với định dạng văn bản và quản lý danh sách, cho phép bạn tạo các tài liệu có cấu trúc tốt trong ứng dụng C# của mình.

### Các câu hỏi thường gặp

#### Câu hỏi: Aspose.Words dành cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, chỉnh sửa và thao tác các tài liệu Word trong ứng dụng C#. Nó cung cấp nhiều tính năng để Xử lý văn bản bằng tài liệu Word, bao gồm khả năng sử dụng một khoảng trắng cho mỗi cấp độ để thụt lề danh sách.

#### Câu hỏi: Làm cách nào tôi có thể sử dụng một khoảng trắng cho mỗi cấp độ để thụt lề danh sách với Aspose.Words cho .NET?
Bạn có thể sử dụng một khoảng trắng cho mỗi cấp độ để thụt lề danh sách bằng cách làm theo các bước sau:

 Tạo một tài liệu mới bằng cách sử dụng`Document` lớp học.

 Sử dụng`DocumentBuilder`class để thêm nội dung vào tài liệu và tạo danh sách có nhiều cấp độ thụt lề.

 Khi bạn đã thêm nội dung và định cấu hình thụt lề danh sách, hãy sử dụng`TxtSaveOptions` lớp và thiết lập`ListIndentation.Count` thuộc tính với số lượng mức thụt lề và`ListIndentation.Character` thuộc tính trên không gian (`' '`) để sử dụng.

 Lưu tài liệu với các tùy chọn đã chỉ định bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

#### Câu hỏi: Aspose.Words có hỗ trợ các ký tự khác để thụt lề danh sách không?
Có, Aspose.Words hỗ trợ các ký tự khác để thụt lề danh sách. Bạn có thể sử dụng các ký tự không phải khoảng trắng, chẳng hạn như tab (`'\t'` ) hoặc các ký tự đặc biệt khác, bằng cách đặt`ListIndentation.Character` thuộc tính cho ký tự mong muốn.

#### Câu hỏi: Có thể tùy chỉnh số lượng khoảng trắng trên mỗi cấp độ để thụt lề danh sách không?
 Có, bạn có thể tùy chỉnh số lượng khoảng trắng trên mỗi cấp độ để thụt lề danh sách bằng cách thay đổi giá trị của`ListIndentation.Count` tài sản ở`TxtSaveOptions` lớp học. Bạn có thể chỉ định số lượng khoảng trắng bạn muốn cho mỗi cấp độ thụt lề.

#### Câu hỏi: Aspose.Words cung cấp những tính năng nào khác để quản lý danh sách?
Aspose.Words cung cấp nhiều tính năng để quản lý danh sách trong tài liệu Word. Bạn có thể tạo danh sách được đánh số hoặc đánh dấu đầu dòng, đặt mức thụt lề, tùy chỉnh kiểu danh sách, thêm mục danh sách, v.v.
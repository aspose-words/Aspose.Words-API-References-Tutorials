---
title: Sửa đổi hình dạng
linktitle: Sửa đổi hình dạng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xử lý các bản sửa đổi hình dạng trong tài liệu Word bằng Aspose.Words dành cho .NET với hướng dẫn toàn diện này. Theo dõi chính các thay đổi, chèn hình dạng, v.v.
type: docs
weight: 10
url: /vi/net/working-with-revisions/shape-revision/
---
## Giới thiệu

Chỉnh sửa tài liệu Word theo chương trình có thể là một nhiệm vụ khó khăn, đặc biệt là khi xử lý các hình dạng. Cho dù bạn đang tạo báo cáo, thiết kế mẫu hay chỉ đơn giản là tự động hóa việc tạo tài liệu, khả năng theo dõi và quản lý các sửa đổi hình dạng là rất quan trọng. Aspose.Words for .NET cung cấp một API mạnh mẽ để làm cho quá trình này trở nên liền mạch và hiệu quả. Trong hướng dẫn này, chúng ta sẽ đi sâu vào chi tiết cụ thể về việc sửa đổi hình dạng trong tài liệu Word, đảm bảo bạn có các công cụ và kiến thức để quản lý tài liệu của mình một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có mọi thứ mình cần:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words. bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Bạn nên thiết lập môi trường phát triển, chẳng hạn như Visual Studio.
- Hiểu biết cơ bản về C#: Làm quen với ngôn ngữ lập trình C# và các khái niệm cơ bản về lập trình hướng đối tượng.
- Tài liệu Word: Một tài liệu Word để làm việc hoặc bạn có thể tạo một tài liệu trong quá trình hướng dẫn.

## Nhập không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết. Những thứ này sẽ cung cấp cho chúng ta quyền truy cập vào các lớp và phương thức cần thiết để xử lý các tài liệu và hình dạng Word.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước khi bắt đầu làm việc với các hình dạng, chúng ta cần xác định đường dẫn đến thư mục tài liệu của mình. Đây là nơi chúng tôi sẽ lưu các tài liệu đã sửa đổi của mình.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo một tài liệu mới

Hãy tạo một tài liệu Word mới để chúng ta chèn và sửa đổi các hình dạng.

```csharp
Document doc = new Document();
```

## Bước 3: Chèn hình dạng nội tuyến

Chúng ta sẽ bắt đầu bằng cách chèn một hình dạng nội tuyến vào tài liệu của mình mà không theo dõi các sửa đổi. Hình dạng nội tuyến là hình dạng chạy cùng với văn bản.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Bước 4: Bắt đầu theo dõi các bản sửa đổi

Để theo dõi các thay đổi trong tài liệu của chúng tôi, chúng tôi cần kích hoạt tính năng theo dõi sửa đổi. Điều này rất cần thiết để xác định các sửa đổi được thực hiện đối với hình dạng.

```csharp
doc.StartTrackRevisions("John Doe");
```

## Bước 5: Chèn một hình dạng khác có sửa đổi

Bây giờ tính năng theo dõi sửa đổi đã được bật, hãy chèn một hình dạng khác. Lần này, mọi thay đổi sẽ được theo dõi.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Bước 6: Truy xuất và sửa đổi hình dạng

Chúng ta có thể truy xuất tất cả các hình dạng trong tài liệu và sửa đổi chúng nếu cần. Ở đây, chúng ta sẽ lấy các hình dạng và loại bỏ hình đầu tiên.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## Bước 7: Lưu tài liệu

Sau khi thực hiện các thay đổi, chúng ta cần lưu tài liệu. Điều này đảm bảo tất cả các phiên bản và sửa đổi được lưu trữ.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## Bước 8: Xử lý các bản sửa đổi di chuyển hình dạng

Khi một hình dạng được di chuyển, Aspose.Words sẽ theo dõi hình dạng này dưới dạng bản sửa đổi. Điều này có nghĩa là sẽ có hai phiên bản của hình dạng: một ở vị trí ban đầu và một ở vị trí mới.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## Phần kết luận

Và bạn có nó! Bạn đã học thành công cách xử lý các sửa đổi hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Cho dù bạn đang quản lý mẫu tài liệu, tự động hóa báo cáo hay chỉ đơn giản là theo dõi các thay đổi thì những kỹ năng này đều vô giá. Bằng cách làm theo hướng dẫn từng bước này, bạn không chỉ nắm vững những điều cơ bản mà còn hiểu rõ hơn về các kỹ thuật xử lý tài liệu nâng cao hơn.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi tài liệu Word theo chương trình bằng C#.

### Tôi có thể theo dõi những thay đổi được thực hiện đối với các thành phần khác trong tài liệu Word không?
Có, Aspose.Words for .NET hỗ trợ theo dõi các thay đổi đối với các thành phần khác nhau, bao gồm văn bản, bảng, v.v.

### Làm cách nào tôi có thể dùng thử miễn phí Aspose.Words cho .NET?
 Bạn có thể dùng thử miễn phí Aspose.Words cho .NET[đây](https://releases.aspose.com/).

### Có thể chấp nhận hoặc từ chối các bản sửa đổi theo chương trình không?
Có, Aspose.Words for .NET cung cấp các phương thức để chấp nhận hoặc từ chối các bản sửa đổi theo chương trình.

### Tôi có thể sử dụng Aspose.Words cho .NET với các ngôn ngữ .NET khác ngoài C# không?
Tuyệt đối! Aspose.Words for .NET có thể được sử dụng với bất kỳ ngôn ngữ .NET nào, bao gồm VB.NET và F#.
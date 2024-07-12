---
title: Sửa đổi hình dạng
linktitle: Sửa đổi hình dạng
second_title: API xử lý tài liệu Aspose.Words
description: Sửa đổi hình dạng trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/shape-revision/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách thực hiện các sửa đổi đối với hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tạo tài liệu và thêm hình dạng

Bước đầu tiên là tạo một tài liệu mới và thêm hình dạng.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Bước 2: Theo dõi các bản sửa đổi và thêm hình dạng khác

Chúng tôi sẽ bật tính năng theo dõi sửa đổi và thêm một hình dạng khác.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Bước 3: Lấy bộ sưu tập hình dạng và kiểm tra các bản sửa đổi

Chúng ta sẽ lấy bộ sưu tập các hình dạng từ tài liệu và kiểm tra các bản sửa đổi liên quan đến từng hình dạng.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Bước 4: Kiểm tra các bản sửa đổi di chuyển hình dạng

Chúng tôi sẽ tải một tài liệu hiện có chứa các bản sửa đổi dịch chuyển hình dạng và kiểm tra các bản sửa đổi liên quan.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Mã nguồn ví dụ cho Shape Revision sử dụng Aspose.Words for .NET

Đây là mã nguồn hoàn chỉnh để thực hiện sửa đổi các hình dạng trong tài liệu bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document();

//Chèn hình dạng nội tuyến mà không theo dõi các sửa đổi.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Bắt đầu theo dõi các sửa đổi và sau đó chèn một hình dạng khác.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Nhận bộ sưu tập hình dạng của tài liệu chỉ bao gồm hai hình dạng mà chúng tôi đã thêm.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Loại bỏ hình dạng đầu tiên.
shapes[0].Remove();

// Bởi vì chúng tôi đã xóa hình dạng đó trong khi các thay đổi đang được theo dõi nên hình dạng đó được tính là một bản sửa đổi bị xóa.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Và chúng tôi đã chèn một hình dạng khác trong khi theo dõi các thay đổi, do đó hình dạng đó sẽ được tính là một bản sửa đổi chèn.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Tài liệu có một hình dạng đã được di chuyển, nhưng các bản sửa đổi di chuyển hình dạng sẽ có hai phiên bản của hình dạng đó.
// Một cái sẽ là hình dạng ở điểm đến và cái còn lại sẽ là hình dạng ở vị trí ban đầu.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Đây là động thái sửa đổi, cũng là hình dáng ở nơi đến của nó.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Đây là sự di chuyển từ bản sửa đổi, tức là hình dạng ở vị trí ban đầu của nó.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thực hiện các sửa đổi đối với hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước tạo tài liệu, bật theo dõi sửa đổi, kiểm tra các bản sửa đổi được liên kết với từng hình dạng và kiểm tra các bản sửa đổi để di chuyển hình dạng, chúng tôi có thể quản lý các bản sửa đổi thành công. Aspose.Words for .NET cung cấp API mạnh mẽ để Xử lý văn bản với các đánh giá và biểu mẫu trong tài liệu Word.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể tạo tài liệu mới và thêm hình dạng trong Aspose.Words cho .NET?

Trả lời: Để tạo tài liệu mới và thêm hình dạng trong Aspose.Words cho .NET, bạn có thể sử dụng mã sau. Ở đây chúng ta thêm hai hình dạng, một khối lập phương và một mặt trời, vào phần đầu tiên của tài liệu:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Câu hỏi: Làm cách nào để bật tính năng theo dõi sửa đổi trong Aspose.Words cho .NET?

 Trả lời: Để bật theo dõi sửa đổi trong Aspose.Words cho .NET, bạn có thể sử dụng`StartTrackRevisions` phương pháp của`Document` sự vật. Phương thức này lấy tên của tác giả của các bản sửa đổi làm tham số:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra các bản sửa đổi được liên kết với từng hình dạng trong tài liệu Aspose.Words for .NET?

Trả lời: Để kiểm tra các bản sửa đổi được liên kết với từng hình dạng trong tài liệu Aspose.Words for .NET, bạn có thể lấy bộ sưu tập các hình dạng của tài liệu bằng cách sử dụng`GetChildNodes` phương pháp với`NodeType.Shape` loại nút. Sau đó, bạn có thể truy cập từng hình dạng`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , Và`IsMoveToRevision` thuộc tính để xác định loại sửa đổi nào được liên kết với hình dạng:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra các bản sửa đổi dịch chuyển của hình dạng trong tài liệu Aspose.Words cho .NET?

 Trả lời: Để kiểm tra các bản sửa đổi dịch chuyển hình dạng trong tài liệu Aspose.Words cho .NET, bạn có thể tải tài liệu hiện có có chứa các bản sửa đổi dịch chuyển hình dạng. Sau đó, bạn có thể truy cập từng hình dạng`IsMoveFromRevision`Và`IsMoveToRevision` Properties để xác định xem nó có đang được di chuyển hay không và nếu có thì từ đâu và đến đâu:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```
---
title: Di chuyển nút trong tài liệu được theo dõi
linktitle: Di chuyển nút trong tài liệu được theo dõi
second_title: API xử lý tài liệu Aspose.Words
description: Di chuyển các nút trong tài liệu được theo dõi bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/move-node-in-tracked-document/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách di chuyển nút trong tài liệu Word được theo dõi bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tạo tài liệu

Bước đầu tiên là tạo một tài liệu mới và thêm các đoạn văn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Bước 2: Theo dõi các sửa đổi

Chúng tôi sẽ kích hoạt tính năng theo dõi sửa đổi trong tài liệu.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Bước 3: Di chuyển một nút

Chúng tôi sẽ di chuyển một nút (đoạn) từ vị trí này sang vị trí khác trong khi tạo các bản sửa đổi.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Bước 4: Dừng theo dõi đánh giá

Chúng tôi sẽ ngừng theo dõi các sửa đổi trong tài liệu.

```csharp
doc.StopTrackRevisions();
```

## Bước 5: Lưu tài liệu

 Sau khi chèn trường biểu mẫu nhập văn bản, hãy lưu tài liệu vào vị trí mong muốn bằng cách sử dụng`Save`phương pháp. Đảm bảo cung cấp đường dẫn tệp thích hợp:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Mã nguồn ví dụ cho Di chuyển nút trong tài liệu được theo dõi bằng Aspose.Words cho .NET

Đây là mã nguồn đầy đủ để di chuyển một nút trong tài liệu được theo dõi bằng Aspose.Words cho .NET:


```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Bắt đầu theo dõi các sửa đổi.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Tạo các bản sửa đổi khi di chuyển một nút từ vị trí này sang vị trí khác.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Dừng quá trình theo dõi sửa đổi.
doc.StopTrackRevisions();

// Có 3 đoạn văn bổ sung trong phạm vi chuyển từ.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách di chuyển một nút trong tài liệu Word được theo dõi bằng Aspose.Words cho .NET. Bằng cách làm theo các bước tạo tài liệu, bật theo dõi sửa đổi, di chuyển nút và dừng theo dõi sửa đổi, chúng tôi có thể thực hiện thao tác này thành công. Aspose.Words for .NET là một công cụ mạnh mẽ để Xử lý Từ bằng tài liệu Word và cung cấp các tính năng nâng cao để quản lý các bản sửa đổi. Giờ đây, bạn có thể sử dụng kiến thức này để di chuyển các nút trong tài liệu Word của riêng mình trong khi theo dõi các bản sửa đổi bằng Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể bật tính năng theo dõi sửa đổi trong tài liệu Aspose.Words for .NET?

 Trả lời: Để bật tính năng theo dõi sửa đổi trong tài liệu Aspose.Words for .NET, bạn có thể sử dụng`StartTrackRevisions` phương pháp của`Document` sự vật. Phương pháp này lấy tham số là tên tác giả của các bản sửa đổi và ngày bắt đầu theo dõi các bản sửa đổi.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Câu hỏi: Làm cách nào tôi có thể di chuyển một nút trong tài liệu được theo dõi mà không tạo ra các bản sửa đổi?

 Trả lời: Nếu bạn muốn di chuyển một nút trong tài liệu được theo dõi mà không tạo ra các bản sửa đổi, bạn có thể sử dụng`Remove` Và`InsertAfter` hoặc`InsertBefore` các phương pháp của`Node` sự vật. Ví dụ: để di chuyển một đoạn này sang đoạn khác, bạn có thể sử dụng đoạn mã sau:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Câu hỏi: Làm cách nào tôi có thể ngừng theo dõi sửa đổi trong tài liệu Aspose.Words for .NET?

 Đáp: Để ngừng theo dõi các bản sửa đổi trong tài liệu Aspose.Words for .NET, bạn có thể sử dụng`StopTrackRevisions` phương pháp của`Document` sự vật.

```csharp
doc.StopTrackRevisions();
```
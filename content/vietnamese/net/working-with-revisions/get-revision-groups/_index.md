---
title: Nhận nhóm sửa đổi
linktitle: Nhận nhóm sửa đổi
second_title: API xử lý tài liệu Aspose.Words
description: Nhận các nhóm sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/get-revision-groups/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ cho bạn biết cách lấy các nhóm sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tải tài liệu

Bước đầu tiên là tải lên tài liệu có chứa các bản sửa đổi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Bước 2: Duyệt các nhóm sửa đổi

Tiếp theo, chúng tôi sẽ lặp qua các nhóm sửa đổi có trong tài liệu và hiển thị thông tin chi tiết của chúng, chẳng hạn như tác giả, loại bản sửa đổi và văn bản đã sửa đổi.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Mã nguồn mẫu cho Nhận nhóm sửa đổi bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để lấy các nhóm sửa đổi trong tài liệu bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách lấy các nhóm sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi đã làm theo các bước để tải tài liệu và duyệt qua các nhóm đánh giá, hiển thị các chi tiết như tác giả và loại đánh giá. Giờ đây, bạn có thể áp dụng kiến thức này để phân tích các bản sửa đổi tài liệu Word của riêng mình bằng Aspose.Words for .NET.

### Câu hỏi thường gặp

#### Hỏi: Làm cách nào để tải lên tài liệu trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Document` lớp Aspose.Words dành cho .NET để tải tài liệu từ một tệp. Bạn có thể chỉ định đường dẫn tài liệu đầy đủ.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Câu hỏi: Làm cách nào để duyệt các nhóm sửa đổi trong tài liệu trong Aspose.Words dành cho .NET?

 Đáp: Hãy sử dụng`Groups` thuộc tính của tài liệu`Revisions` object để có được bộ sưu tập các nhóm sửa đổi. Sau đó, bạn có thể sử dụng vòng lặp để lặp qua từng nhóm đánh giá.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Xử lý từng nhóm đánh giá tại đây
}
```

#### Câu hỏi: Làm cách nào để có được tác giả của nhóm đánh giá trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Author` tài sản của`RevisionGroup` đối tượng để có được tác giả của nhóm sửa đổi.

```csharp
string author = group.Author;
```

#### Câu hỏi: Làm cách nào để có được loại bản sửa đổi của nhóm sửa đổi trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`RevisionType` tài sản của`RevisionGroup`object để có được loại sửa đổi của nhóm.

```csharp
string revisionType = group.RevisionType;
```
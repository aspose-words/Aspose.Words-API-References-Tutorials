---
title: Nhận thông tin chi tiết về nhóm sửa đổi
linktitle: Nhận thông tin chi tiết về nhóm sửa đổi
second_title: API xử lý tài liệu Aspose.Words
description: Nhận thông tin chi tiết về nhóm sửa đổi trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/get-revision-group-details/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách lấy thông tin chi tiết về một nhóm bản sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tải tài liệu

Bước đầu tiên là tải lên tài liệu có chứa các bản sửa đổi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Bước 2: Duyệt các bản sửa đổi

Tiếp theo, chúng tôi sẽ lặp qua các bản sửa đổi có trong tài liệu và hiển thị thông tin chi tiết của chúng, chẳng hạn như loại, tác giả, ngày tháng và văn bản đã sửa đổi.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Mã nguồn ví dụ để Nhận thông tin chi tiết về nhóm sửa đổi bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để lấy thông tin chi tiết về một nhóm bản sửa đổi trong tài liệu bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách lấy thông tin chi tiết về một nhóm bản sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách sử dụng vòng lặp và các thuộc tính thích hợp, chúng tôi có thể hiển thị các chi tiết như loại bản sửa đổi, tác giả, ngày tháng và văn bản đã sửa đổi. Aspose.Words for .NET cung cấp nhiều tính năng mạnh mẽ để thao tác với tài liệu Word, bao gồm cả quản lý sửa đổi. Giờ đây, bạn có thể sử dụng kiến thức này để lấy thông tin chi tiết về nhóm sửa đổi vào tài liệu Word của riêng mình bằng Aspose.Words for .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để tải tài liệu có bản sửa đổi vào Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Document` lớp Aspose.Words dành cho .NET để tải tài liệu từ một tệp có chứa các bản sửa đổi. Bạn có thể chỉ định đường dẫn tài liệu đầy đủ.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Câu hỏi: Làm cách nào để có được thông tin chi tiết về nhóm sửa đổi trong Aspose.Words cho .NET?

Đáp: Xem qua các bản sửa đổi của tài liệu bằng cách sử dụng vòng lặp và truy cập các thuộc tính của từng bản sửa đổi để có được thông tin chi tiết bạn muốn. Bạn có thể dùng`RevisionType`, `Author`, `DateTime` Và`ParentNode` Properties để lấy loại sửa đổi, tác giả, ngày tháng và văn bản sửa đổi tương ứng.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Hỏi: Làm cách nào để kiểm tra xem bản sửa đổi có thuộc về một nhóm trong Aspose.Words cho .NET không?

 Đáp: Hãy sử dụng`Group` tài sản của`Revision` đối tượng để kiểm tra xem bản sửa đổi có thuộc về một nhóm hay không. Nếu`Group` tài sản là`null`, điều đó có nghĩa là bản sửa đổi không thuộc về bất kỳ nhóm nào.

```csharp
if (revision.Group != null)
{
      // Bản sửa đổi thuộc về một nhóm
}
else
{
      // Bản sửa đổi không thuộc về bất kỳ nhóm nào
}
```
---
title: Nhận sửa đổi các loại từ
linktitle: Nhận sửa đổi các loại từ
second_title: API xử lý tài liệu Aspose.Words
description: Nhận các loại từ sửa đổi trong tài liệu Word với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/get-revision-types/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ cho bạn biết cách lấy các loại từ sửa đổi trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tải tài liệu

Bước đầu tiên là tải lên tài liệu có chứa các bản sửa đổi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Bước 2: Duyệt qua các đoạn văn

Tiếp theo, chúng ta sẽ xem qua các đoạn văn của tài liệu và kiểm tra các loại từ sửa đổi liên quan đến từng đoạn văn.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Mã nguồn mẫu cho Nhận các loại sửa đổi bằng Aspose.Words cho .NET

Đây là mã nguồn đầy đủ để nhận các loại sửa đổi trong tài liệu bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách lấy lại các loại từ trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi đã làm theo các bước để tải tài liệu, xem qua các đoạn văn và kiểm tra các loại đánh giá từ liên quan đến từng đoạn văn. Giờ đây, bạn có thể áp dụng kiến thức này để phân tích đánh giá từ trong tài liệu Word của riêng mình bằng Aspose.Words for .NET.

### Câu hỏi thường gặp để nhận các loại từ sửa đổi

#### Hỏi: Làm cách nào để tải lên tài liệu trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Document` lớp Aspose.Words dành cho .NET để tải tài liệu từ một tệp. Bạn có thể chỉ định đường dẫn tài liệu đầy đủ.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Câu hỏi: Làm cách nào để lặp qua các đoạn văn trong tài liệu trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Paragraphs` thuộc tính của phần tài liệu để lấy tập hợp các đoạn văn. Sau đó, bạn có thể sử dụng vòng lặp để lặp qua từng đoạn.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Xử lý từng đoạn văn ở đây
}
```

#### Hỏi: Làm cách nào để kiểm tra xem một đoạn văn đã được di chuyển (xóa) trong Aspose.Words cho .NET chưa?

 A: Sử dụng một đoạn văn`IsMoveFromRevision` tài sản để kiểm tra xem nó đã được di chuyển (xóa) chưa.

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Đoạn văn đã được di chuyển (đã xóa)
}
```

#### Hỏi: Làm cách nào để kiểm tra xem một đoạn văn đã được di chuyển (chèn) trong Aspose.Words cho .NET chưa?

 A: Sử dụng một đoạn văn`IsMoveToRevision`thuộc tính để kiểm tra xem nó đã được di chuyển (chèn) chưa.

```csharp
if (paragraph.IsMoveToRevision)
{
     // Đoạn văn đã được di chuyển (chèn)
}
```
---
title: Giữ Nguồn Cùng Nhau
linktitle: Giữ Nguồn Cùng Nhau
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng Aspose.Words cho .NET để nối và nối các tài liệu Word trong khi vẫn giữ nội dung nguồn cùng với tài liệu đích.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/keep-source-together/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Keep Source Together của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối nhiều tài liệu Word trong khi vẫn giữ nội dung của tài liệu nguồn cùng với nội dung của tài liệu đích. 

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Đã cài đặt Aspose.Words cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc cài đặt nó qua NuGet.
2. Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác.

## Bước 1: Khởi tạo thư mục tài liệu

 Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Sửa đổi giá trị của`dataDir` có thể thay đổi đường dẫn chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu nguồn và đích

Tiếp theo, bạn cần tải tài liệu nguồn và đích bằng Aspose.Words.`Document` lớp học. Cập nhật tên tập tin trong`Document` hàm tạo theo tên tài liệu của bạn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Bước 3: Đặt tài liệu nguồn xuất hiện sau nội dung của tài liệu đích

 Để đảm bảo rằng tài liệu nguồn xuất hiện ngay sau nội dung của tài liệu đích, bạn cần đặt giá trị`SectionStart` thuộc tính của phần đầu tiên trong tài liệu nguồn để`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Bước 4: Đặt định dạng đoạn văn "Keep with Next" cho tài liệu nguồn

 Để giữ các đoạn trong tài liệu nguồn lại với nhau, bạn có thể lặp qua từng đoạn trong tài liệu và đặt`KeepWithNext`tài sản để`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Bước 5: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.KeepSourceFormatting` tham số đảm bảo rằng định dạng nguồn được giữ nguyên trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 6: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất với tính năng "Giữ nguồn cùng nhau" được bật bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Mã nguồn ví dụ cho Keep Source Together bằng Aspose.Words for .NET 

Đây là mã nguồn đầy đủ cho tính năng "Keep Source Together" trong C# bằng Aspose.Words for .NET:


```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Đặt tài liệu nguồn xuất hiện ngay sau nội dung của tài liệu đích.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Keep Source Together bằng Aspose.Words for .NET. Tài liệu cuối cùng sẽ chứa nội dung được hợp nhất với các đoạn văn trong tài liệu nguồn được giữ lại với nhau.
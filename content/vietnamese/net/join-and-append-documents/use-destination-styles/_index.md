---
title: Sử dụng kiểu đích
linktitle: Sử dụng kiểu đích
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối và nối các tài liệu Word trong khi áp dụng các kiểu tài liệu đích bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/use-destination-styles/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Sử dụng Kiểu đích của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối các tài liệu Word trong khi áp dụng các kiểu của tài liệu đích.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Nối tài liệu nguồn với kiểu đích

 Để nối tài liệu nguồn vào tài liệu đích trong khi áp dụng kiểu của tài liệu đích, bạn có thể sử dụng`AppendDocument` phương pháp của`Document` lớp học với`ImportFormatMode.UseDestinationStyles` thông số.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Bước 4: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất với tính năng Sử dụng kiểu đích được bật bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Mã nguồn mẫu cho Sử dụng Kiểu đích bằng Aspose.Words cho .NET

Đây là mã nguồn đầy đủ cho tính năng "Sử dụng kiểu đích" trong C# bằng Aspose.Words cho .NET:

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Nối tài liệu nguồn bằng cách sử dụng các kiểu của tài liệu đích.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Sử dụng kiểu đích bằng Aspose.Words cho .NET. Tài liệu cuối cùng sẽ chứa nội dung được hợp nhất với các kiểu của tài liệu đích được áp dụng.
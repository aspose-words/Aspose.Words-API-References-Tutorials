---
title: Cập nhật bố cục trang
linktitle: Cập nhật bố cục trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách cập nhật bố cục trang khi nối và nối thêm tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/update-page-layout/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Cập nhật Bố cục Trang của Aspose.Words cho .NET. Tính năng này đảm bảo bố cục trang được cập nhật chính xác khi nối và nối tài liệu Word.

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

 Tiếp theo, bạn cần tải tài liệu nguồn và đích bằng Aspose.Words`Document` lớp học. Cập nhật tên tập tin trong`Document` hàm tạo theo tên tài liệu của bạn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Cập nhật bố cục trang cho tài liệu đích

 Để đảm bảo bố cục trang được cập nhật chính xác trước khi thêm tài liệu nguồn, bạn có thể gọi phương thức`UpdatePageLayout` phương pháp trên tài liệu đích.

```csharp
dstDoc.UpdatePageLayout();
```

## Bước 4: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.KeepSourceFormatting` tham số đảm bảo rằng định dạng nguồn được giữ nguyên trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 5: Cập nhật lại bố cục trang

 Sau khi nối thêm tài liệu nguồn, bạn cần gọi`UpdatePageLayout`trên tài liệu đích một lần nữa để đảm bảo rằng mọi thay đổi được thực hiện sau thao tác chắp thêm đều được phản ánh trong kết quả được hiển thị.

```csharp
dstDoc.UpdatePageLayout();
```

## Bước 6: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất với tính năng Cập nhật Bố cục Trang được bật bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Mã nguồn mẫu cho Bố cục trang cập nhật bằng Aspose.Words cho .NET

Đây là mã nguồn đầy đủ cho tính năng "Cập nhật bố cục trang" trong C# bằng Aspose.Words cho .NET:

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Nếu tài liệu đích được hiển thị dưới dạng PDF, hình ảnh, v.v.
	// hoặc UpdatePageLayout được gọi trước tài liệu nguồn. Được nối thêm,
	// thì mọi thay đổi được thực hiện sau đó sẽ không được phản ánh trong kết quả được hiển thị
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Để các thay đổi được cập nhật thành đầu ra được hiển thị, UpdatePageLayout phải được gọi lại.
	// Nếu không được gọi lại, tài liệu được nối thêm sẽ không xuất hiện trong đầu ra của lần hiển thị tiếp theo.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Cập nhật bố cục trang bằng Aspose.Words cho .NET. Tài liệu cuối cùng sẽ chứa nội dung đã hợp nhất với bố cục trang được cập nhật chính xác.
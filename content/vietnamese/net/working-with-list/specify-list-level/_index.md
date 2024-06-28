---
title: Chỉ định cấp độ danh sách
linktitle: Chỉ định cấp độ danh sách
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chỉ định cấp độ danh sách trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-list/specify-list-level/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách chỉ định cấp độ danh sách trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa có, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Tạo tài liệu và trình tạo tài liệu

Đầu tiên, tạo một tài liệu mới và trình tạo tài liệu liên quan:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Tạo và áp dụng danh sách đánh số

Tiếp theo, tạo danh sách được đánh số dựa trên một trong các mẫu danh sách của Microsoft Word và áp dụng nó cho đoạn hiện tại trong trình tạo tài liệu:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Bước 3: Đặc tả cấp độ danh sách

 Sử dụng trình tạo tài liệu`ListLevelNumber` thuộc tính để chỉ định cấp độ danh sách và thêm văn bản vào đoạn văn:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Lặp lại các bước này để xác định cấp độ danh sách và thêm văn bản ở mỗi cấp độ.

## Bước 4: Tạo và áp dụng danh sách có dấu đầu dòng

Bạn cũng có thể tạo và áp dụng danh sách có dấu đầu dòng bằng một trong các mẫu danh sách của Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Bước 5: Thêm văn bản vào cấp độ danh sách dấu đầu dòng

 Sử dụng`ListLevelNumber` thuộc tính một lần nữa để chỉ định cấp danh sách dấu đầu dòng và thêm văn bản:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Bước 6: Dừng định dạng danh sách

 Để dừng định dạng danh sách, hãy đặt`null` đến`List`thuộc tính của trình tạo tài liệu:

```csharp
builder. ListFormat. List = null;
```

## Bước 7: Lưu tài liệu đã sửa đổi

Lưu tài liệu đã sửa đổi:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Vì thế ! Bạn đã chỉ định thành công cấp độ danh sách trong tài liệu Word bằng Aspose.Words cho .NET.

### Mã nguồn mẫu để chỉ định cấp độ danh sách

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tạo danh sách đánh số dựa trên một trong các mẫu danh sách Microsoft Word.
//và áp dụng nó cho đoạn hiện tại của trình tạo tài liệu.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Có chín cấp độ trong danh sách này, hãy thử tất cả.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Tạo danh sách có dấu đầu dòng dựa trên một trong các mẫu danh sách Microsoft Word.
//và áp dụng nó cho đoạn hiện tại của trình tạo tài liệu.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Đây là một cách để dừng định dạng danh sách.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể chỉ định cấp độ danh sách trong Aspose.Words?

 Trả lời: Để chỉ định cấp độ danh sách trong Aspose.Words, bạn cần tạo một phiên bản của`List` lớp và đưa cho nó một danh sách được đánh số. Sau đó bạn có thể sử dụng`Paragraph.ListFormat.ListLevelNumber` thuộc tính để chỉ định cấp độ của từng mục danh sách. Bạn có thể liên kết danh sách này với một phần trong tài liệu của mình để các mục trong danh sách có mức độ mong muốn.

#### Câu hỏi: Có thể thay đổi định dạng đánh số của các mục danh sách trong Aspose.Words không?

 Trả lời: Có, bạn có thể thay đổi định dạng đánh số của các mục danh sách trong Aspose.Words. Các`ListLevel` lớp cung cấp một số thuộc tính cho việc này, chẳng hạn như`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, v.v. Bạn có thể sử dụng các thuộc tính này để đặt định dạng đánh số cho các mục trong danh sách, chẳng hạn như chữ số Ả Rập, chữ số La Mã, chữ cái, v.v.

#### Câu hỏi: Tôi có thể thêm các cấp độ bổ sung vào danh sách được đánh số trong Aspose.Words không?

 Trả lời: Có, có thể thêm các cấp độ bổ sung vào danh sách được đánh số trong Aspose.Words. Các`ListLevel`class cho phép bạn đặt thuộc tính định dạng cho từng cấp độ của danh sách. Bạn có thể đặt các tùy chọn như tiền tố, hậu tố, căn chỉnh, thụt lề, v.v. Điều này cho phép bạn tạo danh sách với nhiều cấp độ phân cấp.



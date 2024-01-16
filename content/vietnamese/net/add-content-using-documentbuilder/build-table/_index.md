---
title: Xây dựng bảng trong tài liệu Word
linktitle: Xây dựng bảng trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo bảng trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/build-table/
---
Trong hướng dẫn từng bước này, bạn sẽ tìm hiểu cách tạo bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể tạo một bảng có định dạng và nội dung tùy chỉnh bằng cách sử dụng lớp DocumentBuilder.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo một tài liệu mới
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Bắt đầu bảng
Tiếp theo, sử dụng phương thức StartTable của lớp DocumentBuilder để bắt đầu xây dựng bảng:

```csharp
Table table = builder.StartTable();
```

## Bước 3: Chèn ô và thêm nội dung
Bây giờ, bạn có thể chèn các ô vào bảng và thêm nội dung vào chúng bằng cách sử dụng các phương thức InsertCell và Write của lớp DocumentBuilder. Tùy chỉnh định dạng ô nếu cần:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Bước 4: Kết thúc hàng
Sau khi thêm nội dung vào các ô của hàng đầu tiên, hãy sử dụng phương thức EndRow của lớp DocumentBuilder để kết thúc hàng:

```csharp
builder.EndRow();
```

## Bước 5: Tùy chỉnh định dạng hàng
Bạn có thể tùy chỉnh định dạng của một hàng bằng cách đặt thuộc tính của các đối tượng RowFormat và CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Bước 6: Kết thúc bảng
Để hoàn thành bảng, hãy sử dụng phương thức EndTable của lớp DocumentBuilder:

```csharp
builder.EndTable();
```

### Mã nguồn ví dụ để xây dựng bảng bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để xây dựng bảng bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách tạo bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể tạo các bảng có định dạng tùy chỉnh.

### Câu hỏi thường gặp về xây dựng bảng trong tài liệu word

#### Câu hỏi: Aspose.Words dành cho .NET là gì?

Đáp: Aspose.Words for .NET là một thư viện xử lý tài liệu mạnh mẽ cho phép các nhà phát triển tạo, đọc, chỉnh sửa và chuyển đổi tài liệu Microsoft Word theo chương trình trong các ứng dụng .NET. Nó cung cấp nhiều tính năng để làm việc với tài liệu Word, chẳng hạn như thao tác văn bản, tạo bảng, bảo vệ tài liệu, định dạng, v.v.

#### Câu hỏi: Làm cách nào tôi có thể tạo bảng trong tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Để tạo bảng trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` sự vật.
2.  Sử dụng`StartTable` phương pháp của`DocumentBuilder`lớp để bắt đầu xây dựng bảng.
3.  Chèn ô vào bảng và thêm nội dung bằng cách sử dụng`InsertCell` Và`Write` các phương pháp của`DocumentBuilder` lớp học.
4.  Kết thúc hàng bằng cách sử dụng`EndRow` phương pháp của`DocumentBuilder` lớp học.
5.  Tùy chỉnh định dạng hàng bằng cách đặt thuộc tính của`RowFormat` Và`CellFormat` các đối tượng.
6.  Kết thúc bảng bằng cách sử dụng`EndTable` phương pháp của`DocumentBuilder` lớp học.
7. Lưu tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể tùy chỉnh định dạng của bảng và các ô của bảng?

 Đáp: Bạn có thể tùy chỉnh định dạng của bảng và các ô của nó bằng cách đặt các thuộc tính khác nhau của`RowFormat` Và`CellFormat` các đối tượng. Ví dụ: bạn có thể điều chỉnh căn chỉnh ô, hướng văn bản dọc và ngang, chiều cao ô, chiều cao hàng, v.v. Bằng cách sử dụng các thuộc tính này, bạn có thể đạt được hình thức mong muốn cho bảng và nội dung của nó.

#### Câu hỏi: Tôi có thể tạo các bảng phức tạp bằng các ô được hợp nhất và các tính năng nâng cao khác không?

 Trả lời: Có, Aspose.Words for .NET cung cấp các tính năng nâng cao để xây dựng các bảng phức tạp, bao gồm hỗ trợ cho các ô đã hợp nhất, bảng lồng nhau và bố cục bảng phức tạp. Bạn có thể dùng`MergeCells` phương pháp gộp ô,`StartTable`phương pháp tạo bảng lồng nhau và các phương pháp khác để đạt được cấu trúc bảng mong muốn.

#### Câu hỏi: Aspose.Words for .NET có tương thích với các định dạng tài liệu Word khác nhau không?

Trả lời: Có, Aspose.Words cho .NET tương thích với nhiều định dạng tài liệu Word khác nhau, bao gồm DOC, DOCX, RTF, v.v. Nó hỗ trợ cả định dạng cũ (DOC) và định dạng dựa trên XML hiện đại (DOCX) và cho phép bạn làm việc với các tài liệu ở các định dạng khác nhau mà không gặp bất kỳ sự cố nào.

#### Câu hỏi: Tôi có thể tìm thêm thông tin và tài liệu về Aspose.Words cho .NET ở đâu?

 Đáp: Bạn có thể tìm thấy tài liệu toàn diện và ví dụ về mã trên[Tài liệu tham khảo API](https://reference.aspose.com/words/net/). Tài liệu sẽ cung cấp thông tin chi tiết về các tính năng của thư viện và cách sử dụng chúng trong các ứng dụng .NET của bạn.
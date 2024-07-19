---
title: Xuất sang Markdown với việc căn chỉnh nội dung bảng
linktitle: Xuất sang Markdown với việc căn chỉnh nội dung bảng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xuất nội dung bảng với các cách sắp xếp khác nhau sang tệp Markdown bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# sau giúp xuất nội dung sang tệp Markdown có căn chỉnh nội dung bảng bằng thư viện Aspose.Words cho .NET. Đảm bảo bạn đã đưa thư viện Aspose.Words vào dự án của mình trước khi sử dụng mã này.

## Bước 1: Đặt đường dẫn thư mục tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu của bạn nơi tài liệu đã chỉnh sửa sẽ được lưu.

## Bước 2: Tạo tài liệu và trình tạo tài liệu

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ở đây chúng ta tạo một thể hiện của`Document` lớp và một thể hiện của`DocumentBuilder` class sẽ cho phép chúng ta thao tác với tài liệu và thêm các phần tử.

## Bước 3: Chèn các ô vào bảng với cách căn chỉnh đoạn văn khác nhau

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Chúng tôi sử dụng Trình tạo tài liệu để chèn các ô vào bảng và đặt cách sắp xếp các đoạn văn khác nhau cho mỗi ô.

## Bước 4: Đặt tùy chọn xuất Markdown và lưu tài liệu đã sửa đổi

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Chúng tôi đặt các tùy chọn xuất Markdown với các cách sắp xếp nội dung bảng khác nhau, sau đó lưu tài liệu đã sửa đổi bằng cách sử dụng từng tùy chọn căn chỉnh.

### Mã nguồn ví dụ để xuất sang Markdown với căn chỉnh nội dung bảng bằng Aspose.Words cho .NET

```csharp

            
	// Đường dẫn đến thư mục tài liệu.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Làm cho tất cả các đoạn văn bên trong bảng được căn chỉnh.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// Căn chỉnh trong trường hợp này sẽ được lấy từ đoạn đầu tiên trong cột bảng tương ứng.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Lưu tài liệu đã sửa đổi
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```

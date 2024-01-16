---
title: Ký tự Meta trong mẫu tìm kiếm
linktitle: Ký tự Meta trong mẫu tìm kiếm
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng siêu ký tự trong mẫu tìm kiếm với Aspose.Words for .NET để thao tác với tài liệu Word.
type: docs
weight: 10
url: /vi/net/find-and-replace-text/meta-characters-in-search-pattern/
---
Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng hàm Meta Character In Search Pattern trong thư viện Aspose.Words for .NET. Tính năng này cho phép bạn sử dụng các siêu ký tự đặc biệt để thực hiện tìm kiếm nâng cao và thay thế trong tài liệu Word.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Tạo một tài liệu mới

 Trước khi bắt đầu sử dụng siêu ký tự trong mẫu tìm kiếm, chúng ta cần tạo một tài liệu mới bằng Aspose.Words cho .NET. Điều này có thể được thực hiện bằng cách khởi tạo một`Document` sự vật:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Bước 2: Chèn văn bản vào tài liệu

 Sau khi có tài liệu, chúng ta có thể chèn văn bản bằng cách sử dụng`DocumentBuilder` sự vật. Trong ví dụ của chúng tôi, chúng tôi sử dụng`Writeln` Và`Write` phương pháp chèn hai dòng văn bản:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Bước 3: Tìm và thay thế văn bản bằng siêu ký tự

 Bây giờ chúng ta sẽ sử dụng`Range.Replace` chức năng tìm kiếm và thay thế văn bản bằng cách sử dụng mẫu tìm kiếm có chứa các siêu ký tự đặc biệt. Trong ví dụ của chúng tôi, chúng tôi thay thế cụm từ "Đây là dòng 1&pĐây là dòng 2" bằng "Dòng này được thay thế" bằng cách sử dụng`&p` siêu ký tự để biểu thị ngắt đoạn:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Bước 4: Chèn ngắt trang trong tài liệu

 Để minh họa việc sử dụng một siêu ký tự khác, chúng ta sẽ chèn dấu ngắt trang vào tài liệu bằng cách sử dụng`InsertBreak` phương pháp với`BreakType.PageBreak` tham số. Đầu tiên chúng ta di chuyển con trỏ từ`DocumentBuilder` đến cuối tài liệu, sau đó chúng ta chèn ngắt trang và dòng văn bản mới:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Bước 5: Tìm và thay thế bằng siêu ký tự khác

 Bây giờ chúng ta sẽ thực hiện một tìm kiếm khác và thay thế bằng cách sử dụng`&m` siêu ký tự để biểu thị ngắt trang. Chúng tôi thay thế cụm từ "Đây là dòng 1&mĐây là dòng 2" bằng "Ngắt trang được thay thế bằng văn bản mới." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Bước 6: Lưu tài liệu đã chỉnh sửa

Cuối cùng, chúng tôi lưu tài liệu đã sửa đổi vào một thư mục được chỉ định bằng cách sử dụng lệnh`Save` phương pháp:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Mã nguồn ví dụ cho các ký tự Meta trong mẫu tìm kiếm bằng cách sử dụng Aspose.Words cho .NET

Đây là mã nguồn mẫu đầy đủ để minh hoạ cách sử dụng siêu ký tự trong mẫu tìm kiếm với Aspose.Words cho .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng siêu ký tự trong mẫu tìm kiếm của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để tạo tài liệu, chèn văn bản, thực hiện tìm kiếm và thay thế bằng cách sử dụng các siêu ký tự đặc biệt, chèn ngắt trang và lưu tài liệu đã chỉnh sửa.

### Câu hỏi thường gặp

#### Câu hỏi: Tính năng Meta Ký tự trong Mẫu tìm kiếm trong Aspose.Words dành cho .NET là gì?

Trả lời: Tính năng Ký tự Meta trong Mẫu tìm kiếm trong Aspose.Words dành cho .NET cho phép bạn sử dụng các ký tự meta đặc biệt để thực hiện tìm kiếm và thay thế nâng cao trong tài liệu Word. Các siêu ký tự này cho phép bạn biểu thị dấu ngắt đoạn, dấu ngắt phần, dấu ngắt trang và các thành phần đặc biệt khác trong mẫu tìm kiếm của bạn.

#### Hỏi: Làm cách nào để tạo tài liệu mới trong Aspose.Words cho .NET?

 Đáp: Trước khi sử dụng siêu ký tự trong mẫu tìm kiếm, bạn phải tạo một tài liệu mới bằng Aspose.Words cho .NET. Điều này có thể được thực hiện bằng cách khởi tạo một`Document` sự vật. Đây là mã mẫu để tạo một tài liệu mới:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Hỏi: Làm cách nào để chèn văn bản vào tài liệu bằng Aspose.Words cho .NET?

 Đáp: Sau khi có tài liệu, bạn có thể chèn văn bản bằng cách sử dụng`DocumentBuilder` sự vật. Trong ví dụ của chúng tôi, chúng tôi sử dụng`Writeln` Và`Write` phương pháp chèn hai dòng văn bản:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### Câu hỏi: Làm cách nào để tìm kiếm và thay thế văn bản bằng siêu ký tự trong tài liệu bằng Aspose.Words cho .NET?

 Đáp: Để tìm kiếm và thay thế văn bản bằng siêu ký tự, bạn có thể sử dụng`Range.Replace` phương pháp. Trong ví dụ của chúng tôi, chúng tôi thay thế cụm từ "Đây là dòng 1&pĐây là dòng 2" bằng "Dòng này được thay thế" bằng cách sử dụng`&p` siêu ký tự để biểu thị ngắt đoạn:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### Câu hỏi: Làm cách nào để chèn dấu ngắt trang trong tài liệu bằng Aspose.Words cho .NET?

Đáp: Để minh họa việc sử dụng một siêu ký tự khác, chúng tôi sẽ chèn dấu ngắt trang vào tài liệu bằng cách sử dụng`InsertBreak` phương pháp với`BreakType.PageBreak` tham số. Đầu tiên chúng ta di chuyển con trỏ từ`DocumentBuilder` đến cuối tài liệu, sau đó chúng ta chèn ngắt trang và dòng văn bản mới:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### Câu hỏi: Làm cách nào để tìm kiếm và thay thế bằng một siêu ký tự khác trong tài liệu bằng Aspose.Words cho .NET?

 Đáp: Bây giờ chúng ta sẽ thực hiện một tìm kiếm khác và thay thế bằng cách sử dụng`&m` siêu ký tự để biểu thị ngắt trang. Chúng tôi thay thế cụm từ "Đây là dòng 1&mĐây là dòng 2" bằng "Ngắt trang được thay thế bằng văn bản mới." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### Hỏi: Làm cách nào để lưu tài liệu đã chỉnh sửa trong Aspose.Words cho .NET?

 Đáp: Khi bạn đã thực hiện các thay đổi đối với tài liệu, bạn có thể lưu nó vào một thư mục được chỉ định bằng cách sử dụng lệnh`Save` phương pháp:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```
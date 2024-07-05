---
title: Bỏ qua văn bản bên trong Xóa bản sửa đổi
linktitle: Bỏ qua văn bản bên trong Xóa bản sửa đổi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" của Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" trong thư viện Aspose.Words cho .NET. Tính năng này hữu ích khi chúng ta muốn bỏ qua văn bản bên trong các bản sửa đổi xóa khi Xử lý văn bản với tài liệu.

## Tổng quan về thư viện Aspose.Words cho .NET

Trước khi đi sâu vào chi tiết mã, hãy để tôi giới thiệu ngắn gọn về thư viện Aspose.Words cho .NET. Đây là một thư viện mạnh mẽ cho phép tạo, sửa đổi và chuyển đổi tài liệu Word trong các ứng dụng .NET. Nó cung cấp nhiều tính năng nâng cao để Xử lý văn bản với tài liệu, bao gồm cả quản lý sửa đổi.

## Hiểu tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi"

Tính năng "Bỏ qua văn bản bên trong xóa bản sửa đổi" trong Aspose.Words for .NET cho phép bạn chỉ định xem có nên bỏ qua văn bản bên trong các bản sửa đổi xóa trong một số thao tác nhất định hay không, chẳng hạn như tìm và thay thế văn bản. Khi tính năng này được bật, văn bản đã xóa bên trong các bản sửa đổi sẽ không được xem xét trong quá trình hoạt động.

## Bước 1: Tạo tài liệu mới bằng Aspose.Words cho .NET

 Trước khi bắt đầu thao tác văn bản trong tài liệu, chúng ta cần tạo một tài liệu mới bằng Aspose.Words cho .NET. Nó có thể được thực hiện bằng cách khởi tạo một`Document` sự vật:

```csharp
Document doc = new Document();
```

## Bước 2: Chèn văn bản chưa sửa đổi vào tài liệu

 Sau khi có tài liệu, chúng ta có thể chèn văn bản chưa được xem xét bằng cách sử dụng`DocumentBuilder` sự vật. Ví dụ: để chèn văn bản "Văn bản đã xóa", chúng ta có thể sử dụng`Writeln` Và`Write` phương pháp:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Bước 3: Xóa đoạn văn có theo dõi các sửa đổi

Để minh họa việc sử dụng tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi", chúng tôi sẽ xóa một đoạn văn khỏi tài liệu bằng cách sử dụng tính năng theo dõi bản sửa đổi. Điều này sẽ cho phép chúng tôi xem tính năng này ảnh hưởng như thế nào đến các hoạt động tiếp theo.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Bước 4: Áp dụng tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi"

 Bây giờ chúng ta đã chuẩn bị tài liệu của mình bằng cách xóa một đoạn văn, chúng ta có thể kích hoạt tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" bằng cách sử dụng một`FindReplaceOptions` sự vật. Chúng tôi sẽ thiết lập`IgnoreDeleted`tài sản để`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Bước 5: Sử dụng biểu thức chính quy để tìm và thay thế

Để thực hiện các thao tác tìm kiếm và thay thế trên văn bản của tài liệu, chúng ta sẽ sử dụng biểu thức chính quy. Trong ví dụ của chúng tôi, chúng tôi sẽ tìm kiếm tất cả các lần xuất hiện của chữ "e" và thay thế chúng bằng dấu hoa thị "* ". .MẠNG LƯỚI`Regex` lớp được sử dụng cho việc này:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Bước 6: Hiển thị đầu ra tài liệu đã sửa đổi

 Sau khi áp dụng tìm kiếm và thay thế, chúng ta có thể hiển thị nội dung đã thay đổi của tài liệu bằng cách sử dụng`GetText` phương pháp:

```csharp
Console.WriteLine(doc.GetText());
```

## Bước 7: Sửa đổi các tùy chọn để bao gồm văn bản đã xóa

 Nếu muốn đưa văn bản đã xóa vào kết quả đầu ra, chúng ta có thể thay đổi các tùy chọn để không bỏ qua văn bản đã xóa. Đối với điều này, chúng tôi sẽ thiết lập`IgnoreDeleted`tài sản để`false`:

```csharp
options. IgnoreDeleted = false;
```

## Bước 8: Xuất tài liệu đã sửa đổi có văn bản đã xóa

Sau khi thay đổi tùy chọn, chúng ta có thể thực hiện tìm kiếm và thay thế lại để có kết quả có văn bản đã xóa đi kèm:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Mã nguồn ví dụ cho Bỏ qua văn bản bên trong Xóa bản sửa đổi bằng Aspose.Words cho .NET

Đây là mã nguồn mẫu đầy đủ để minh hoạ cách sử dụng tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" với Aspose.Words cho .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Chèn văn bản chưa được sửa đổi.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Xóa đoạn đầu tiên có theo dõi các sửa đổi.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" trong Aspose.Words dành cho .NET. Tính năng này rất hữu ích để bỏ qua văn bản bên trong các bản sửa đổi bị xóa khi thao tác với tài liệu. Chúng tôi đã làm theo hướng dẫn từng bước để tạo tài liệu, chèn văn bản, xóa đoạn có theo dõi sửa đổi, áp dụng tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" cũng như thực hiện các thao tác tìm và thay thế.

### Câu hỏi thường gặp

#### Câu hỏi: Chức năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" trong Aspose.Words dành cho .NET là gì?

Trả lời: Chức năng "Bỏ qua văn bản bên trong xóa bản sửa đổi" trong Aspose.Words dành cho .NET cho phép bạn chỉ định xem có nên bỏ qua văn bản bên trong các bản sửa đổi xóa trong một số thao tác nhất định hay không, chẳng hạn như tìm và thay thế văn bản. Khi tính năng này được bật, văn bản đã xóa bên trong các bản sửa đổi sẽ không được xem xét trong quá trình hoạt động.

#### Câu hỏi: Aspose.Words dành cho .NET là gì?

Trả lời: Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, chỉnh sửa và chuyển đổi tài liệu Word thành ứng dụng .NET. Nó cung cấp nhiều tính năng nâng cao để Xử lý văn bản với tài liệu, bao gồm cả quản lý sửa đổi.

#### Hỏi: Làm cách nào để tạo tài liệu mới trong Aspose.Words cho .NET?

 Trả lời: Trước khi bắt đầu thao tác văn bản trong tài liệu, bạn cần tạo một tài liệu mới bằng Aspose.Words cho .NET. Điều này có thể được thực hiện bằng cách khởi tạo một`Document` sự vật. Đây là mã mẫu để tạo một tài liệu mới:

```csharp
Document doc = new Document();
```

#### Hỏi: Làm cách nào để chèn văn bản chưa chỉnh sửa vào tài liệu bằng Aspose.Words cho .NET?

 Đáp: Sau khi có tài liệu, bạn có thể chèn văn bản chưa được xem xét bằng cách sử dụng`DocumentBuilder` sự vật. Ví dụ: để chèn văn bản "Văn bản đã xóa", bạn có thể sử dụng`Writeln` Và`Write` phương pháp:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Hỏi: Làm cách nào để xóa một đoạn văn có theo dõi sửa đổi trong Aspose.Words cho .NET?

Trả lời: Để minh họa việc sử dụng chức năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi", chúng tôi sẽ xóa một đoạn văn khỏi tài liệu bằng cách sử dụng tính năng theo dõi bản sửa đổi. Điều này sẽ cho phép chúng ta xem chức năng này ảnh hưởng như thế nào đến các hoạt động tiếp theo.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Hỏi: Làm cách nào để bật tính năng "Bỏ qua văn bản bên trong Xóa bản sửa đổi" trong Aspose.Words cho .NET?

 Đáp: Bây giờ chúng ta đã chuẩn bị tài liệu bằng cách xóa một đoạn văn, chúng ta có thể kích hoạt tính năng "Bỏ qua văn bản bên trong Xóa các bản sửa đổi" bằng cách sử dụng một`FindReplaceOptions` sự vật. Chúng tôi sẽ thiết lập`IgnoreDeleted`tài sản để`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Câu hỏi: Làm cách nào để tìm kiếm và thay thế bằng cách sử dụng biểu thức chính quy trong Aspose.Words cho .NET?

Đáp: Để thực hiện các thao tác tìm kiếm và thay thế trên văn bản của tài liệu, chúng ta sẽ sử dụng biểu thức chính quy. Trong ví dụ của chúng tôi, chúng tôi sẽ tìm kiếm tất cả các lần xuất hiện của chữ "e" và thay thế chúng bằng dấu hoa thị "* ". Chúng tôi sẽ sử dụng .NET`Regex` lớp học cho việc này:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Hỏi: Làm cách nào để xem nội dung tài liệu đã thay đổi trong Aspose.Words cho .NET?

Đáp: Sau khi áp dụng tìm kiếm và thay thế, chúng ta có thể hiển thị nội dung đã thay đổi của tài liệu bằng cách sử dụng`GetText` phương pháp:

```csharp
Console.WriteLine(doc.GetText());
```

#### Câu hỏi: Làm cách nào để đưa văn bản đã xóa vào kết quả đầu ra trong Aspose.Words cho .NET?

 Trả lời: Nếu muốn đưa văn bản đã xóa vào kết quả đầu ra, chúng tôi có thể thay đổi các tùy chọn để không bỏ qua văn bản đã xóa. Đối với điều này, chúng tôi sẽ thiết lập`IgnoreDeleted`tài sản để`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Hỏi: Làm cách nào để hiển thị tài liệu đã chỉnh sửa có văn bản đã xóa trong Aspose.Words cho .NET?

Trả lời: Sau khi thay đổi các tùy chọn, chúng ta có thể thực hiện tìm kiếm mới và thay thế để nhận được kết quả có chứa văn bản đã xóa:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

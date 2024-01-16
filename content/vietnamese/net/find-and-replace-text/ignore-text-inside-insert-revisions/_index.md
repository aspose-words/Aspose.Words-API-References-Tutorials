---
title: Bỏ qua văn bản bên trong Chèn bản sửa đổi
linktitle: Bỏ qua văn bản bên trong Chèn bản sửa đổi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng tính năng "Bỏ qua văn bản bên trong Chèn bản sửa đổi" của Aspose.Words dành cho .NET để thao tác chèn bản sửa đổi trong tài liệu Word.
type: docs
weight: 10
url: /vi/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng chức năng Bỏ qua văn bản bên trong Chèn bản sửa đổi trong thư viện Aspose.Words cho .NET. Tính năng này hữu ích khi chúng ta muốn bỏ qua văn bản bên trong chèn các bản sửa đổi trong khi thao tác với tài liệu.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Tạo một tài liệu mới

 Trước khi bắt đầu thao tác văn bản bên trong các bản sửa đổi chèn, chúng ta cần tạo một tài liệu mới bằng Aspose.Words cho .NET. Điều này có thể được thực hiện bằng cách khởi tạo một`Document` sự vật:

```csharp
Document doc = new Document();
```

## Bước 2: Chèn văn bản có theo dõi sửa đổi

 Sau khi có tài liệu, chúng ta có thể chèn văn bản có theo dõi sửa đổi bằng cách sử dụng`DocumentBuilder`sự vật. Ví dụ: để chèn văn bản "Đã chèn" với tính năng theo dõi sửa đổi, chúng ta có thể sử dụng`StartTrackRevisions`, `Writeln` Và`StopTrackRevisions` phương pháp:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Bước 3: Chèn văn bản chưa được xem xét

 Ngoài văn bản có theo dõi sửa đổi, chúng ta cũng có thể chèn văn bản chưa được sửa đổi bằng cách sử dụng`DocumentBuilder` sự vật. Ví dụ: để chèn văn bản "Văn bản" mà không cần sửa đổi, chúng ta có thể sử dụng`Write` phương pháp:

```csharp
builder.Write("Text");
```

## Bước 4: Sử dụng chức năng Bỏ qua văn bản bên trong Chèn bản sửa đổi

 Để bỏ qua văn bản bên trong, hãy chèn các bản sửa đổi vào các thao tác tiếp theo, chúng ta có thể sử dụng`FindReplaceOptions` đối tượng và thiết lập`IgnoreInserted`tài sản để`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Bước 5: Sử dụng biểu thức chính quy để tìm kiếm và thay thế

Để thực hiện các thao tác tìm kiếm và thay thế trên văn bản tài liệu, chúng ta sẽ sử dụng biểu thức chính quy. Trong ví dụ của chúng tôi, chúng tôi sẽ tìm kiếm tất cả các lần xuất hiện của chữ "e" và thay thế chúng bằng dấu hoa thị "* ". Chúng tôi sẽ sử dụng .NET`Regex` lớp học cho việc này:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Bước 6: Xem đầu ra tài liệu đã sửa đổi

 Sau khi áp dụng tìm kiếm và thay thế, chúng ta có thể hiển thị nội dung đã thay đổi của tài liệu bằng cách sử dụng`GetText` phương pháp:

```csharp
Console.WriteLine(doc.GetText());
```

## Bước 7: Thay đổi tùy chọn để bao gồm các bản sửa đổi

Nếu chúng ta muốn đưa văn bản bên trong các bản sửa đổi chèn vào kết quả đầu ra, chúng ta có thể thay đổi các tùy chọn để không bỏ qua các bản sửa đổi chèn. Đối với điều này, chúng tôi sẽ thiết lập`IgnoreInserted`tài sản để`false`:

```csharp
options.IgnoreInserted = false;
```

## Bước 8: Xem tài liệu đã sửa đổi có chèn bản sửa đổi

Sau khi thay đổi các tùy chọn, chúng ta có thể thực hiện tìm kiếm và thay thế lại để có kết quả bằng văn bản bên trong các bản sửa đổi chèn đi kèm:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Mã nguồn ví dụ cho Bỏ qua văn bản bên trong Chèn bản sửa đổi bằng Aspose.Words cho .NET

Đây là mã nguồn mẫu đầy đủ để minh họa cách sử dụng chức năng Bỏ qua văn bản bên trong Chèn bản sửa đổi với Aspose.Words cho .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Chèn văn bản với các sửa đổi theo dõi.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Chèn văn bản chưa được sửa đổi.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng chức năng Bỏ qua văn bản bên trong Chèn bản sửa đổi trong Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để tạo tài liệu, chèn văn bản có theo dõi các bản sửa đổi và văn bản chưa được sửa đổi, sử dụng chức năng Bỏ qua văn bản bên trong Chèn bản sửa đổi, thực hiện các thao tác tìm kiếm và thay thế bằng biểu thức thông thường và hiển thị tài liệu đã sửa đổi.

### Câu hỏi thường gặp

#### Câu hỏi: Tính năng "Bỏ qua văn bản bên trong Chèn bản sửa đổi" trong Aspose.Words dành cho .NET là gì?

Trả lời: Tính năng "Bỏ qua văn bản bên trong chèn bản sửa đổi" trong Aspose.Words for .NET cho phép bạn chỉ định xem có nên bỏ qua văn bản bên trong các bản sửa đổi chèn trong một số thao tác nhất định hay không, chẳng hạn như tìm và thay thế văn bản. Khi tính năng này được bật, văn bản bên trong các bản sửa đổi chèn sẽ không được xem xét trong quá trình hoạt động.

#### Câu hỏi: Làm cách nào tôi có thể tạo tài liệu mới bằng Aspose.Words cho .NET?

 Đáp: Để tạo một tài liệu mới bằng Aspose.Words cho .NET, bạn có thể khởi tạo một`Document` sự vật. Đây là một ví dụ về mã C# để tạo một tài liệu mới:

```csharp
Document doc = new Document();
```

#### Câu hỏi: Làm cách nào tôi có thể chèn văn bản có theo dõi sửa đổi trong Aspose.Words cho .NET?

Đáp: Sau khi có tài liệu, bạn có thể chèn văn bản có theo dõi sửa đổi bằng cách sử dụng`DocumentBuilder` sự vật. Ví dụ: để chèn văn bản "Đã chèn" với tính năng theo dõi sửa đổi, bạn có thể sử dụng`StartTrackRevisions`, `Writeln` , Và`StopTrackRevisions` phương pháp:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Câu hỏi: Làm cách nào tôi có thể chèn văn bản chưa được sửa đổi trong Aspose.Words cho .NET?

 Đáp: Ngoài văn bản có theo dõi sửa đổi, bạn cũng có thể chèn văn bản chưa được sửa đổi bằng cách sử dụng`DocumentBuilder` sự vật. Ví dụ: để chèn văn bản "Văn bản" mà không cần sửa đổi, bạn có thể sử dụng`Write` phương pháp:

```csharp
builder.Write("Text");
```

#### Câu hỏi: Làm cách nào tôi có thể bỏ qua văn bản bên trong các bản sửa đổi chèn trong Aspose.Words cho .NET?

 Đáp: Để bỏ qua văn bản bên trong, hãy chèn các bản sửa đổi trong các thao tác tiếp theo, bạn có thể sử dụng`FindReplaceOptions` đối tượng và thiết lập`IgnoreInserted`tài sản để`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### Câu hỏi: Làm cách nào tôi có thể thực hiện tìm kiếm và thay thế bằng cách sử dụng biểu thức thông thường trong Aspose.Words cho .NET?

 Trả lời: Để thực hiện các thao tác tìm kiếm và thay thế trên văn bản của tài liệu bằng cách sử dụng các biểu thức thông thường, bạn có thể sử dụng .NET`Regex` lớp học. Ví dụ: để tìm kiếm tất cả các lần xuất hiện của chữ "e" và thay thế chúng bằng dấu hoa thị "* ", bạn có thể tạo một`Regex` đối tượng và sử dụng nó với`Replace` phương pháp:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Câu hỏi: Làm cách nào tôi có thể xem kết quả đầu ra đã sửa đổi của tài liệu trong Aspose.Words cho .NET?

 Đáp: Sau khi áp dụng các thao tác tìm kiếm và thay thế, bạn có thể xem nội dung đã thay đổi của tài liệu bằng cách sử dụng`GetText` phương pháp:

```csharp
Console.WriteLine(doc.GetText());
```

#### Câu hỏi: Làm cách nào tôi có thể đưa các bản sửa đổi chèn vào kết quả đầu ra trong Aspose.Words cho .NET?

 Trả lời: Để đưa văn bản bên trong các bản sửa đổi chèn vào kết quả đầu ra, bạn có thể thay đổi các tùy chọn để không bỏ qua các bản sửa đổi chèn. Đối với điều này, bạn có thể thiết lập`IgnoreInserted` tài sản của`FindReplaceOptions` chủ đề`false`:

```csharp
options.IgnoreInserted = false;
```

#### Câu hỏi: Làm cách nào tôi có thể hiển thị tài liệu đã sửa đổi với các bản sửa đổi chèn trong Aspose.Words cho .NET?

Trả lời: Sau khi thay đổi các tùy chọn để bao gồm các bản sửa đổi chèn, bạn có thể thực hiện tìm kiếm và thay thế lại để nhận được kết quả bằng văn bản bên trong các bản sửa đổi chèn được bao gồm:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
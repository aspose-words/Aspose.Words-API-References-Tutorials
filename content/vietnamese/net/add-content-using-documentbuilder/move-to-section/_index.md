---
title: Di chuyển đến phần trong tài liệu Word
linktitle: Di chuyển đến phần trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước sử dụng tính năng Di chuyển đến Phần trong tài liệu word của Aspose.Words for .NET thao tác các phần và đoạn văn trong tài liệu Word.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/move-to-section/
---
Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách sử dụng tính năng Di chuyển đến Phần trong tài liệu word của Aspose.Words cho .NET từng bước bằng cách sử dụng mã nguồn C# được cung cấp. Tính năng này cho phép bạn điều hướng và thao tác các phần khác nhau trong tài liệu Word. Hãy làm theo các bước bên dưới để tích hợp chức năng này vào ứng dụng của bạn.

## Bước 1: Tạo một tài liệu mới và thêm một phần

Đầu tiên, chúng ta cần tạo một tài liệu mới và thêm một phần vào đó. Sử dụng đoạn mã sau để hoàn thành bước này:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Mã này tạo một tài liệu trống mới và thêm một phần vào tài liệu này.

## Bước 2: Di chuyển DocumentBuilder sang phần thứ hai và thêm văn bản

Tiếp theo, chúng ta cần di chuyển DocumentBuilder sang phần thứ hai của tài liệu và thêm một số văn bản vào đó. Sử dụng đoạn mã sau để thực hiện bước này:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Mã này tạo DocumentBuilder từ tài liệu hiện có, sau đó di chuyển con trỏ từ DocumentBuilder sang phần thứ hai của tài liệu. Cuối cùng, nó thêm văn bản được chỉ định vào phần này.

## Bước 3: Tải tài liệu với các đoạn văn hiện có

Nếu bạn muốn làm việc với một tài liệu hiện có chứa các đoạn văn, bạn có thể tải tài liệu này bằng mã sau:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Mã này tải tài liệu đã chỉ định (thay thế "MyDir +"Paragraphs.docx"" với đường dẫn thực tế tới tài liệu của bạn) và truy cập vào tập hợp các đoạn văn từ phần đầu tiên của tài liệu. Dòng`Assert.AreEqual(22, paragraphs.Count);` kiểm tra xem tài liệu có chứa 22 đoạn văn hay không.

## Bước 4: tạo DocumentBuilder cho tài liệu

Bạn có thể tạo con trỏ DocumentBuilder tới một đoạn văn cụ thể bằng cách sử dụng các chỉ mục vị trí.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Bước 5: Di chuyển con trỏ đến đoạn cụ thể


Bạn có thể di chuyển con trỏ DocumentBuilder đến một đoạn cụ thể bằng cách sử dụng các chỉ mục vị trí. Đây là cách thực hiện:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Mã này di chuyển con trỏ của DocumentBuilder đến đoạn thứ ba của phần thứ hai (đoạn ở chỉ số 2) và đến vị trí 10. Sau đó, nó thêm một đoạn văn mới với một số văn bản và kiểm tra xem con trỏ có được định vị đúng trên đoạn văn mới này hay không.

### Mã nguồn ví dụ cho Di chuyển để di chuyển đến phần bằng Aspose.Words cho .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Di chuyển DocumentBuilder sang phần thứ hai và thêm văn bản.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Tạo tài liệu với các đoạn văn.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// Theo mặc định, khi chúng tôi tạo DocumentBuilder cho một tài liệu, con trỏ của nó ở ngay đầu tài liệu,
// và mọi nội dung được DocumentBuilder thêm vào sẽ chỉ được thêm vào tài liệu.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//Bạn có thể di chuyển con trỏ đến bất kỳ vị trí nào trong đoạn văn.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Đó là tất cả ! Bây giờ bạn đã hiểu cách sử dụng chức năng di chuyển đến phần của Aspose.Words cho .NET bằng mã nguồn được cung cấp. Giờ đây, bạn có thể tích hợp chức năng này vào ứng dụng của riêng mình và thao tác các phần và đoạn văn trong tài liệu Word một cách linh hoạt.

## Phần kết luận

Trong ví dụ này, chúng tôi đã khám phá tính năng Di chuyển đến Phần của Aspose.Words dành cho .NET. Chúng tôi đã học cách tạo một tài liệu mới, thêm các phần vào đó và sử dụng lớp DocumentBuilder để điều hướng đến các phần và đoạn văn cụ thể trong tài liệu Word. Tính năng này cung cấp cho các nhà phát triển các công cụ mạnh mẽ để thao tác nội dung và cấu trúc của tài liệu Word theo chương trình bằng Aspose.Words for .NET.

### Câu hỏi thường gặp về chuyển đến phần trong tài liệu word

#### Câu hỏi: Mục đích của tính năng Di chuyển đến Phần trong Aspose.Words dành cho .NET là gì?

Trả lời: Tính năng Di chuyển đến Phần trong Aspose.Words dành cho .NET cho phép các nhà phát triển điều hướng đến và thao tác các phần khác nhau trong tài liệu Word theo chương trình. Nó cung cấp khả năng chèn, sửa đổi hoặc xóa nội dung tại các phần cụ thể của tài liệu.

#### Hỏi: Làm cách nào để di chuyển DocumentBuilder đến một phần cụ thể trong tài liệu Word?

Đáp: Để di chuyển DocumentBuilder đến một phần cụ thể trong tài liệu Word, bạn có thể sử dụng phương thức MoveToSection của lớp DocumentBuilder. Phương thức này lấy chỉ mục của phần đích làm tham số và đặt con trỏ ở đầu phần đó.

#### Hỏi: Tôi có thể thêm hoặc sửa đổi nội dung sau khi di chuyển đến một phần cụ thể bằng tính năng Di chuyển đến Phần không?

Đáp: Có, sau khi DocumentBuilder được định vị tại phần mong muốn bằng MoveToSection, bạn có thể sử dụng nhiều phương thức khác nhau của lớp DocumentBuilder, chẳng hạn như Writeln, Write hoặc InsertHtml, để thêm hoặc sửa đổi nội dung của phần đó.

#### Hỏi: Làm cách nào tôi có thể làm việc với các đoạn văn hiện có trong tài liệu bằng tính năng Di chuyển đến Phần?

Trả lời: Bạn có thể tải tài liệu hiện có chứa các đoạn văn bằng hàm tạo Tài liệu, sau đó truy cập vào tập hợp các đoạn văn từ phần mong muốn bằng thuộc tính FirstSection.Body.Paragraphs.

#### Câu hỏi: Tôi có thể di chuyển con trỏ DocumentBuilder đến một đoạn cụ thể trong một phần bằng tính năng Di chuyển đến Phần không?

Trả lời: Có, bạn có thể di chuyển con trỏ DocumentBuilder đến một đoạn cụ thể trong một phần bằng phương pháp MoveToParagraph. Phương pháp này lấy các chỉ số của đoạn đích và vị trí ký tự (offset) trong đoạn đó làm tham số.
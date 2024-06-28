---
title: Thay đổi khoảng cách và thụt lề đoạn văn châu Á trong tài liệu Word
linktitle: Thay đổi khoảng cách và thụt lề đoạn văn châu Á trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thay đổi khoảng cách đoạn văn và mức thụt lề kiểu Châu Á trong tài liệu word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thay đổi khoảng cách và mức thụt lề của một đoạn văn Châu Á bằng Aspose.Words cho .NET. Hãy làm theo các bước bên dưới để hiểu mã nguồn và áp dụng các thay đổi.

## Bước 1: Tải tài liệu

Để bắt đầu, hãy chỉ định thư mục cho tài liệu của bạn và tải tài liệu chứa kiểu chữ Châu Á vào đối tượng Tài liệu. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Bước 2: Thay đổi khoảng cách đoạn văn và thụt lề

Bây giờ chúng ta sẽ sửa đổi khoảng cách và thụt lề của đoạn đầu tiên của tài liệu Châu Á. Đây là cách thực hiện:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Cập nhật ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Cập nhật ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Cập nhật ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Cập nhật ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Cập nhật ParagraphFormat.SpaceAfter
```

## Bước 3: Lưu tài liệu

 Sau khi chèn trường biểu mẫu nhập văn bản, hãy lưu tài liệu vào vị trí mong muốn bằng cách sử dụng`Save` phương pháp. Đảm bảo cung cấp đường dẫn tệp thích hợp:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Mã nguồn ví dụ về Thay đổi khoảng cách và thụt lề đoạn văn châu Á bằng cách sử dụng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho tính năng Chỉnh sửa khoảng cách và thụt lề đoạn văn châu Á với Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent sẽ được cập nhật.
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent sẽ được cập nhật.
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent sẽ được cập nhật.
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore sẽ được cập nhật
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter sẽ được cập nhật

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Với mã này, bạn sẽ có thể thay đổi khoảng cách và mức thụt lề của một đoạn văn Châu Á bằng Aspose.Words for .NET.

## Phần kết luận

 Trong hướng dẫn này, chúng ta đã học cách thay đổi khoảng cách và mức thụt lề của một đoạn văn Châu Á bằng Aspose.Words cho .NET. Bằng cách sửa đổi các thuộc tính có liên quan của`ParagraphFormat`chúng ta có thể kiểm soát bố cục và hình thức của các đoạn văn Châu Á trong tài liệu Word. Tính năng này rất hữu ích để tùy chỉnh định dạng văn bản có ký tự châu Á và đạt được cách trình bày trực quan mong muốn trong các tài liệu có nội dung ngôn ngữ hỗn hợp.

### Câu hỏi thường gặp

#### Câu hỏi: Tính năng "Thay đổi khoảng cách và thụt lề đoạn văn châu Á" trong Aspose.Words for .NET làm gì?

Trả lời: Tính năng "Thay đổi khoảng cách và thụt lề đoạn văn châu Á" trong Aspose.Words for .NET cho phép bạn sửa đổi các thuộc tính giãn cách và thụt lề của một đoạn văn châu Á trong tài liệu Word. Bạn có thể điều chỉnh mức thụt lề trái và phải, thụt lề dòng đầu tiên, khoảng trắng trước và khoảng trắng sau các giá trị để kiểm soát bố cục và hình thức của đoạn văn.

#### Hỏi: Làm cách nào để thay đổi khoảng cách và mức thụt lề của một đoạn văn Châu Á bằng Aspose.Words cho .NET?

 Đáp: Để thay đổi khoảng cách và thụt lề của một đoạn văn Châu Á, bạn cần truy cập vào`ParagraphFormat`của đoạn mục tiêu và sửa đổi các thuộc tính có liên quan của nó. Trong mã ví dụ được cung cấp, chúng tôi truy cập đoạn đầu tiên của tài liệu và đặt`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , Và`LineUnitAfter` thuộc tính để điều chỉnh khoảng cách và thụt lề.

#### Hỏi: Tôi có thể áp dụng những thay đổi này cho các đoạn khác trong tài liệu không?

 Đáp: Có, bạn có thể áp dụng những thay đổi này cho các đoạn văn khác trong tài liệu bằng cách truy cập vào các đoạn tương ứng của chúng.`ParagraphFormat` các đối tượng. Mã ví dụ hướng đến đoạn đầu tiên của tài liệu, nhưng bạn có thể sửa đổi các đoạn khác bằng cách điều chỉnh chỉ mục trong phần`Paragraphs` sưu tập hoặc sử dụng các tiêu chí khác để chọn các đoạn văn mong muốn.
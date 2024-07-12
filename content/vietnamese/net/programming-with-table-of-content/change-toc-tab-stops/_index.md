---
title: Thay đổi điểm dừng tab Toc trong tài liệu Word
linktitle: Thay đổi điểm dừng tab Toc trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thay đổi tab mục lục trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, chỉnh sửa và thao tác các tài liệu Word trong ứng dụng C#. Trong số các chức năng do Aspose.Words cung cấp, có khả năng sửa đổi các tab được sử dụng trong mục lục của tài liệu Word. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# của Aspose.Words cho .NET để thay đổi các tab trong mục lục của tài liệu.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện phổ biến giúp việc Xử lý văn bản bằng tài liệu Word trở nên dễ dàng và hiệu quả. Nó cung cấp nhiều tính năng để tạo, chỉnh sửa và thao tác với tài liệu Word, bao gồm thay đổi tab mục lục.

## Đang tải tài liệu chứa mục lục

Bước đầu tiên là tải tài liệu Word chứa mục lục bạn muốn sửa đổi. Sử dụng lớp Tài liệu để tải tài liệu từ tệp nguồn. Đây là một ví dụ :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Trong ví dụ này, chúng tôi tải tài liệu "Mục lục.docx" nằm trong thư mục tài liệu.

## Thay đổi các tab trong mục lục

Sau khi tài liệu được tải, chúng tôi đi qua từng đoạn của tài liệu và kiểm tra xem nó có được định dạng bằng cách sử dụng kiểu kết quả Mục lục (TOC) hay không. Nếu vậy, chúng tôi sửa đổi các tab dùng để căn chỉnh số trang. Đây là cách thực hiện:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

Trong ví dụ này, chúng tôi sử dụng vòng lặp để lặp qua từng đoạn trong tài liệu. Sau đó, chúng tôi kiểm tra xem đoạn văn có được định dạng bằng cách sử dụng kiểu Kết quả Mục lục (TOC) hay không. Nếu vậy, chúng tôi truy cập tab đầu tiên được sử dụng trong đoạn này và sửa đổi nó bằng cách xóa tab cũ và thêm tab mới với vị trí đã sửa đổi.

## Lưu tài liệu đã sửa đổi

Khi bạn đã thực hiện những thay đổi cần thiết đối với các tab trong mục lục, bạn có thể lưu tài liệu đã sửa đổi bằng phương thức Lưu của lớp Tài liệu. Đây là một ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Trong ví dụ này, chúng tôi lưu tài liệu đã sửa đổi dưới dạng "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Mã nguồn mẫu cho tính năng "Chỉnh sửa tab mục lục" với Aspose.Words for .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu chứa mục lục
Document doc = new Document(dataDir + "Table of contents.docx");

// Sửa đổi các tab của mục lục
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Lưu tài liệu đã sửa đổi
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách sử dụng Aspose.Words cho .NET để thay đổi các tab trong mục lục của tài liệu Word bằng mã nguồn C# được cung cấp. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng tùy chỉnh các tab mục lục trong tài liệu Word trong ứng dụng C# của mình. Aspose.Words cung cấp tính linh hoạt và sức mạnh to lớn để làm việc với các kiểu và định dạng tài liệu của bạn, cho phép bạn tạo các tài liệu Word hấp dẫn và chuyên nghiệp.

### Câu hỏi thường gặp về thay đổi điểm dừng tab toc trong tài liệu word

#### Hỏi: Mục đích của chức năng "Thay đổi điểm dừng tab Toc trong tài liệu Word" trong Aspose.Words cho .NET là gì?

Trả lời: Chức năng "Thay đổi điểm dừng tab Toc trong tài liệu Word" trong Aspose.Words for .NET cho phép bạn sửa đổi các điểm dừng tab được sử dụng trong mục lục của tài liệu Word. Nó cho phép bạn tùy chỉnh việc căn chỉnh và định vị số trang cũng như các tiêu đề tương ứng trong mục lục.

#### Câu hỏi: Aspose.Words dành cho .NET là gì?

Trả lời: Aspose.Words for .NET là một thư viện mạnh mẽ được thiết kế để Xử lý văn bản bằng tài liệu Word trong các ứng dụng .NET. Nó cung cấp các tính năng toàn diện để tạo, chỉnh sửa, thao tác và chuyển đổi tài liệu Word theo chương trình bằng C# hoặc các ngôn ngữ .NET khác.

#### Câu hỏi: Làm cách nào để tải tài liệu Word chứa mục lục bằng Aspose.Words cho .NET?

 Trả lời: Để tải tài liệu Word chứa mục lục bằng Aspose.Words cho .NET, bạn có thể sử dụng`Document` lớp và hàm tạo của nó. Bằng cách cung cấp đường dẫn tệp của tài liệu, bạn có thể tải nó vào một`Document` sự vật. Đây là một ví dụ:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Đoạn mã này tải tài liệu "Bảng nội dung.docx" nằm trong thư mục được chỉ định.

#### Câu hỏi: Làm cách nào tôi có thể thay đổi các tab được sử dụng trong mục lục bằng Aspose.Words cho .NET?

 Đáp: Sau khi tài liệu được tải, bạn có thể duyệt qua từng đoạn của tài liệu và kiểm tra xem nó có được định dạng bằng cách sử dụng kiểu kết quả Mục lục (TOC) hay không. Nếu đoạn văn được định dạng theo kiểu TOC, bạn có thể sửa đổi các tab được sử dụng để căn chỉnh số trang. Trong Aspose.Words cho .NET, bạn có thể truy cập`ParagraphFormat` thuộc tính của mỗi đoạn văn để truy xuất và sửa đổi các điểm dừng tab. Đây là một ví dụ:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

Trong mã này, vòng lặp lặp qua từng đoạn trong tài liệu. Nếu một đoạn có kiểu TOC, nó sẽ truy cập điểm dừng tab đầu tiên được sử dụng trong đoạn đó, xóa nó và thêm điểm dừng tab mới với vị trí đã sửa đổi.

#### Câu hỏi: Tôi có thể thay đổi các tab cho nhiều cấp độ trong mục lục bằng Aspose.Words cho .NET không?

Trả lời: Có, bạn có thể thay đổi các tab cho nhiều cấp độ trong mục lục bằng Aspose.Words for .NET. Bằng cách lặp lại từng đoạn văn và kiểm tra kiểu TOC, bạn có thể sửa đổi các tab cho từng cấp độ riêng lẻ. Bạn có thể truy cập vào cấp độ mong muốn của mục lục và điều chỉnh các điểm dừng tab cho phù hợp.

#### Câu hỏi: Làm cách nào để lưu tài liệu đã sửa đổi sau khi thay đổi các tab trong mục lục bằng Aspose.Words cho .NET?

 Đáp: Sau khi thực hiện những thay đổi cần thiết đối với các tab trong mục lục, bạn có thể lưu tài liệu đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` lớp học. Cung cấp đường dẫn và tên tệp mong muốn cho tài liệu đầu ra dưới dạng tham số cho`Save` phương pháp. Đây là một ví dụ:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Mã này lưu tài liệu đã sửa đổi dưới dạng "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### Câu hỏi: Tôi có thể tùy chỉnh các khía cạnh khác của mục lục bằng Aspose.Words cho .NET không?

Đáp: Có, với Aspose.Words for .NET, bạn có thể tùy chỉnh các khía cạnh khác nhau của mục lục. Ngoài việc thay đổi các tab, bạn có thể sửa đổi kiểu phông chữ, kích thước, căn chỉnh và các thuộc tính định dạng khác của mục lục và số trang. Ngoài ra, bạn có thể điều chỉnh mức độ thụt lề, khoảng cách và định dạng của các tiêu đề tương ứng.

#### Hỏi:. Tôi có thể thay đổi căn chỉnh tab và ký tự đầu cho mục lục bằng Aspose.Words cho .NET không?

Đáp: Có, bạn có thể thay đổi cách căn chỉnh tab và ký tự đầu cho mục lục bằng Aspose.Words for .NET. Bằng cách truy cập các điểm dừng tab và điều chỉnh thuộc tính căn chỉnh và đường dẫn của chúng, bạn có thể kiểm soát việc căn chỉnh và hình thức trực quan của số trang và tiêu đề tương ứng trong mục lục.

#### Hỏi: Aspose.Words for .NET có hỗ trợ thay đổi các kiểu và định dạng khác trong tài liệu Word không?

Trả lời: Có, Aspose.Words for .NET cung cấp hỗ trợ rộng rãi để thay đổi nhiều kiểu và định dạng khác nhau trong tài liệu Word. Nó cho phép bạn sửa đổi kiểu cho các thành phần khác nhau như đoạn văn, tiêu đề, bảng, danh sách, v.v. Bạn có thể thay đổi phông chữ, màu sắc, căn chỉnh, thụt lề, khoảng cách và các khía cạnh định dạng khác theo yêu cầu của bạn.

#### Câu hỏi: Tôi có thể sửa đổi các tab trong mục lục trong tài liệu Word hiện có bằng Aspose.Words cho .NET không?

Trả lời: Có, bạn có thể sửa đổi các tab trong mục lục trong tài liệu Word hiện có bằng Aspose.Words cho .NET. Bằng cách tải tài liệu, duyệt qua các đoạn văn và thực hiện các thay đổi cần thiết đối với các điểm dừng tab, bạn có thể cập nhật các tab trong mục lục. Cuối cùng, lưu tài liệu để áp dụng các sửa đổi.
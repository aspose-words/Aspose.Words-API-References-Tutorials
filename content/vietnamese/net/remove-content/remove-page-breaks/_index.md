---
title: Xóa ngắt trang trong tài liệu Word
linktitle: Xóa ngắt trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xóa ngắt trang trong tài liệu word bằng Thư viện Aspose.Words cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có bố cục liền mạch.
type: docs
weight: 10
url: /vi/net/remove-content/remove-page-breaks/
---
Trong hướng dẫn này, chúng ta sẽ khám phá cách loại bỏ ngắt trang trong tài liệu word bằng thư viện Aspose.Words cho .NET. Ngắt trang đôi khi có thể ảnh hưởng đến định dạng và bố cục của tài liệu và có thể cần phải loại bỏ chúng theo chương trình. Chúng tôi sẽ cung cấp hướng dẫn từng bước để giúp bạn hiểu quy trình và triển khai nó trong các dự án C# của riêng bạn.

## Yêu cầu

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#
- Đã cài đặt thư viện Aspose.Words cho .NET
- Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác được thiết lập

## Bước 1: Thiết lập môi trường

Để bắt đầu, hãy tạo một dự án C# mới trong môi trường phát triển ưa thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu chính xác trong dự án của bạn.

## Bước 2: Tải tài liệu

Để loại bỏ ngắt trang khỏi tài liệu, trước tiên chúng ta cần tải tài liệu vào bộ nhớ. Đoạn mã sau minh họa cách tải tài liệu từ một thư mục cụ thể:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "your-document.docx");
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn.

## Bước 3: Xóa ngắt trang

Sau khi tài liệu được tải, chúng ta có thể bắt đầu xóa ngắt trang. Đoạn mã bên dưới minh họa cách lặp qua tất cả các đoạn trong tài liệu, kiểm tra ngắt trang và xóa chúng:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
     // Nếu trước đoạn văn có ngắt trang thì xóa đi
     if (para.ParagraphFormat.PageBreakBefore)
         para.ParagraphFormat.PageBreakBefore = false;

     // Kiểm tra tất cả các lần chạy trong đoạn văn để biết dấu ngắt trang và loại bỏ chúng
     foreach(Run run in para.Runs)
     {
         if (run.Text.Contains(ControlChar.PageBreak))
             run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
     }
}
```

Đoạn mã trên lặp qua tất cả các đoạn trong tài liệu và kiểm tra xem mỗi đoạn có ngắt trang trước nó hay không. Nếu phát hiện ngắt trang, nó sẽ bị xóa. Sau đó, nó kiểm tra từng lần chạy trong đoạn văn để tìm dấu ngắt trang và loại bỏ chúng.

## Bước 4: Lưu tài liệu đã sửa đổi

Sau khi loại bỏ các ngắt trang, chúng ta cần lưu tài liệu đã sửa đổi. Đoạn mã sau đây trình bày cách lưu tài liệu đã sửa đổi vào một vị trí cụ thể:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 Thay thế`"modified-document.docx"`với tên mong muốn cho tài liệu đã sửa đổi của bạn.

### Mã nguồn mẫu để Xóa ngắt trang bằng Aspose.Words cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Tải tài liệu
Document doc = new Document(dataDir + "your-document.docx");

NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
	// Nếu đoạn văn có dấu ngắt trang trước tập hợp thì hãy xóa nó.
	if (para.ParagraphFormat.PageBreakBefore)
		para.ParagraphFormat.PageBreakBefore = false;

	// Kiểm tra tất cả các lần chạy trong đoạn văn để biết dấu ngắt trang và loại bỏ chúng.
	foreach (Run run in para.Runs)
	{
		if (run.Text.Contains(ControlChar.PageBreak))
			run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
	}
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);        

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách xóa ngắt trang khỏi tài liệu bằng thư viện Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước, giờ đây bạn có thể triển khai chức năng này trong các dự án C# của riêng mình. Việc xóa ngắt trang có thể giúp bạn duy trì bố cục và định dạng nhất quán trong tài liệu của mình.

### Câu hỏi thường gặp

#### Hỏi: Tại sao tôi nên sử dụng Aspose.Words để xóa dấu ngắt trang trong tài liệu Word?

Trả lời: Aspose.Words là một thư viện lớp mạnh mẽ và linh hoạt để thao tác các tài liệu Word trong các ứng dụng .NET. Bằng cách sử dụng Aspose.Words, bạn sẽ có được giải pháp hiệu quả và dễ dàng để xóa dấu ngắt trang khỏi tài liệu của mình. Điều này cho phép bạn tùy chỉnh bố cục tài liệu của mình, loại bỏ các ngắt trang không mong muốn và duy trì bản trình bày nhất quán.

#### Câu hỏi: Làm cách nào để tải lên tài liệu trong Aspose.Words cho .NET?

Trả lời: Để xóa ngắt trang trong tài liệu Word, trước tiên bạn phải tải tài liệu vào bộ nhớ bằng phương thức Load() của Aspose.Words. Đây là mã mẫu để tải tài liệu từ một thư mục cụ thể:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "your-document.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn.

#### Hỏi: Làm cách nào để xóa ngắt trang trong tài liệu bằng Aspose.Words?

Đáp: Sau khi tài liệu được tải, bạn có thể bắt đầu xóa dấu ngắt trang. Sử dụng vòng lặp để lặp qua tất cả các đoạn trong tài liệu, kiểm tra xem chúng có chứa dấu ngắt trang hay không và xóa chúng nếu cần. Đây là một mã mẫu:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
      // Nếu đoạn văn trước đó có ngắt trang thì hãy bỏ đi
      if (para.ParagraphFormat.PageBreakBefore)
          para.ParagraphFormat.PageBreakBefore = false;

      // Kiểm tra tất cả các phần tử Run trong đoạn văn để biết ngắt trang và xóa chúng
      foreach(Run run in para.Runs)
      {
          if (run.Text.Contains(ControlChar.PageBreak))
              run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
      }
}
```

Mã này lặp qua tất cả các đoạn văn trong tài liệu, kiểm tra xem chúng có chứa dấu ngắt trang ở đầu hay không rồi xóa nó. Sau đó, nó sẽ kiểm tra từng phần tử Run trong đoạn văn để tìm dấu ngắt trang và loại bỏ chúng.

#### Hỏi: Làm cách nào để lưu tài liệu đã chỉnh sửa trong Aspose.Words cho .NET?

Đáp: Sau khi loại bỏ ngắt trang, bạn cần lưu tài liệu đã sửa đổi. Sử dụng phương thức Save() để lưu tài liệu đã sửa đổi vào một vị trí cụ thể. Đây là một mã mẫu:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 Thay thế`"modified-document.docx"`với tên mong muốn cho tài liệu đã sửa đổi của bạn.
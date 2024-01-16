---
title: Sử dụng nguồn cảnh báo
linktitle: Sử dụng nguồn cảnh báo
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng nguồn cảnh báo với Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/use-warning-source/
---

Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách sử dụng nguồn cảnh báo với Aspose.Words cho .NET. Nguồn cảnh báo cho biết nguồn gốc của cảnh báo khi sử dụng chức năng gọi lại.

## Bước 1: Tải tài liệu

 Chúng tôi sẽ tải một tài liệu hiện có chứa các cảnh báo bằng cách sử dụng`Load` phương pháp của`Document` lớp học.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Bước 3: Sử dụng nguồn cảnh báo

 Chúng tôi sẽ sử dụng nguồn cảnh báo bằng cách đặt tài liệu`WarningCallback` tài sản vào một bộ sưu tập`WarningInfo` các đối tượng.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Bước 4: Lưu tài liệu

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng mong muốn.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Mã nguồn mẫu để sử dụng nguồn cảnh báo với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng nguồn cảnh báo với Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Hỏi: Chúng tôi có thể tùy chỉnh giao diện của thẻ "Cảnh báo" không?

 Đáp: Định dạng của thẻ "Cảnh báo" tùy thuộc vào trình kết xuất Markdown được sử dụng. Trong hầu hết các trường hợp, bạn có thể tùy chỉnh giao diện bằng cách sử dụng CSS để nhắm mục tiêu`blockquote` gắn thẻ trong tài liệu của bạn.

#### Câu hỏi: Có thể thêm biểu tượng vào thẻ "Cảnh báo" không?

Đáp: Có, bạn có thể thêm biểu tượng vào thẻ "Cảnh báo" bằng mã HTML trong tài liệu Markdown của mình. Bạn có thể chèn một`span` gắn thẻ với lớp thích hợp để hiển thị biểu tượng bên cạnh văn bản cảnh báo.

#### Câu hỏi: Thẻ "Cảnh báo" có tương thích với tất cả trình đọc Markdown không?

 Trả lời: Khả năng tương thích của thẻ "Cảnh báo" phụ thuộc vào kết xuất Markdown được sử dụng. Hầu hết người đọc Markdown sẽ ủng hộ`blockquote` để hiển thị văn bản được đánh dấu nhưng hình thức chính xác có thể khác nhau.
---
title: Đặt dấu nhấn mạnh phông chữ
linktitle: Đặt dấu nhấn mạnh phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt kiểu nhấn mạnh phông chữ trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-font-emphasis-mark/
---

Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách đặt kiểu nhấn mạnh phông chữ trong tài liệu Word bằng Aspose.Words cho .NET. Nhấn mạnh phông chữ được sử dụng để làm nổi bật các từ hoặc cụm từ nhất định trong văn bản.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn

## Bước 1: Xác định thư mục tài liệu
 Bắt đầu bằng cách đặt đường dẫn thư mục đến vị trí tài liệu Word của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo và tùy chỉnh tài liệu
 Tạo một thể hiện của`Document` lớp và một liên quan`DocumentBuilder` để xây dựng nội dung tài liệu. Sử dụng`Font.EmphasisMark` thuộc tính để đặt kiểu nhấn mạnh phông chữ thành`EmphasisMark.UnderSolidCircle` . Sau đó sử dụng`Write` Và`Writeln` các phương pháp của`DocumentBuilder` để thêm văn bản với điểm nhấn phông chữ được chỉ định.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Bước 3: Lưu tài liệu
 Lưu tài liệu bằng cách sử dụng`Save` phương pháp của`Document` với đường dẫn và tên file thích hợp.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Mã nguồn mẫu cho Đặt dấu nhấn mạnh phông chữ bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách đặt kiểu nhấn mạnh phông chữ trong tài liệu Word bằng Aspose.Words cho .NET. Thử nghiệm các kiểu nhấn mạnh khác nhau và sử dụng tính năng này để đánh dấu các từ hoặc cụm từ trong tài liệu của bạn.

### Câu hỏi thường gặp

#### Hỏi: Làm cách nào tôi có thể thêm dấu trọng âm vào một phông chữ cụ thể trong tài liệu Word bằng Aspose.Words?

Trả lời: Để thêm dấu trọng âm vào một phông chữ cụ thể trong tài liệu Word bằng Aspose.Words, bạn có thể sử dụng API để điều hướng đến phông chữ mong muốn và áp dụng các dấu trọng âm thích hợp. Điều này sẽ thêm dấu nhấn vào văn bản với phông chữ đã chọn.

#### Hỏi: Có thể thay đổi kiểu dấu trọng âm trong tài liệu Word bằng Aspose.Words không?

Đáp: Có, với Aspose.Words, bạn có thể thay đổi kiểu dấu trọng âm trong tài liệu Word. API cho phép bạn điều chỉnh các thuộc tính kiểu như màu sắc, kích thước, kiểu đường, v.v., để tùy chỉnh giao diện của dấu nhấn.

#### Câu hỏi: Làm cách nào tôi có thể xóa tất cả dấu trọng âm khỏi tài liệu Word bằng Aspose.Words?

Trả lời: Để xóa tất cả các dấu trọng âm khỏi tài liệu Word bằng Aspose.Words, bạn có thể sử dụng API để duyệt tài liệu, phát hiện các dấu trọng âm hiện có và xóa chúng bằng các phương pháp thích hợp. Điều này sẽ loại bỏ tất cả các dấu nhấn mạnh khỏi tài liệu.

#### Hỏi: Tôi có thể thêm dấu trọng âm vào một phần văn bản cụ thể trong tài liệu Word không?

Trả lời: Có, bạn có thể thêm dấu trọng âm vào một phần văn bản cụ thể trong tài liệu Word bằng Aspose.Words. Bạn có thể chọn phạm vi văn bản mong muốn bằng API và thêm các dấu nhấn thích hợp vào phần văn bản đó.

#### Hỏi: Dấu trọng âm có thể được tùy chỉnh theo nhu cầu của tôi không?

Đáp: Có, dấu trọng âm có thể được tùy chỉnh theo nhu cầu của bạn bằng Aspose.Words. Bạn có thể điều chỉnh các thuộc tính kiểu của dấu trọng âm, chẳng hạn như màu sắc, kích thước, kiểu đường, v.v. để phù hợp với tùy chọn định dạng của bạn.
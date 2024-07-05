---
title: Gạch nối từ của ngôn ngữ
linktitle: Gạch nối từ của ngôn ngữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách gạch nối các từ ở các ngôn ngữ khác nhau trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-hyphenation/hyphenate-words-of-languages/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách gạch nối các từ ở các ngôn ngữ khác nhau trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

Để bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa có, hãy tải xuống và cài đặt thư viện từ trang web chính thức.

## Bước 1: Khởi tạo đối tượng tài liệu

 Đầu tiên, khởi tạo`Document` đối tượng bằng cách chỉ định đường dẫn đến tài liệu nguồn chứa văn bản bằng các ngôn ngữ khác nhau:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Bước 2: Lưu từ điển gạch nối

Tiếp theo, lưu từ điển gạch nối cho các ngôn ngữ khác nhau mà bạn muốn xử lý. Trong ví dụ này, chúng tôi đăng ký từ điển cho tiếng Anh Mỹ và tiếng Đức Thụy Sĩ:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Đảm bảo bạn có các tệp từ điển thích hợp trong thư mục dữ liệu của mình.

## Bước 3: Xử lý từ bằng dấu gạch nối

Bây giờ bạn có thể sử dụng tính năng gạch nối để xử lý các từ trong các ngôn ngữ khác nhau. Bạn có thể sử dụng các phương pháp khác nhau để`Document` hoặc`DocumentBuilder` tùy thuộc vào nhu cầu cụ thể của bạn.

```csharp
// Ví dụ: Sử dụng phương thức Hyphenate của DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Bước 4: Lưu tài liệu

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Vì thế ! Bạn đã xử lý thành công các từ bằng cách gạch nối chúng bằng các ngôn ngữ khác nhau trong tài liệu Word bằng Aspose.Words for .NET.

### Mã nguồn mẫu để gạch nối từ bằng Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó cho phù hợp với nhu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể phát âm một từ trong một ngôn ngữ cụ thể bằng Aspose.Words?

 Đáp: Để phát âm một từ trong một ngôn ngữ cụ thể bằng Aspose.Words, bạn có thể sử dụng`Hyphenation` lớp học và`Hyphenate()` phương pháp. Tạo một thể hiện của`Hyphenation` lớp chỉ định ngôn ngữ mong muốn, sau đó gọi`Hyphenate()` phương thức truyền từ để phân âm tiết làm đối số. Điều này sẽ cung cấp cho bạn các âm tiết của từ trong ngôn ngữ được chỉ định.

#### Câu hỏi: Tôi nên sử dụng mã ngôn ngữ nào để chỉ định ngôn ngữ âm tiết trong Aspose.Words?

Trả lời: Để chỉ định ngôn ngữ âm tiết trong Aspose.Words, bạn phải sử dụng mã ngôn ngữ thích hợp. Ví dụ: bạn có thể sử dụng "en" cho tiếng Anh, "fr" cho tiếng Pháp, "es" cho tiếng Tây Ban Nha, "de" cho tiếng Đức, v.v. Xem tài liệu Aspose.Words để biết danh sách đầy đủ các mã ngôn ngữ được hỗ trợ.

#### Câu hỏi: Việc sắp xếp âm tiết có hoạt động với tất cả các ngôn ngữ trong Aspose.Words không?

Trả lời: Âm tiết trong Aspose.Words phụ thuộc vào quy tắc âm tiết dành riêng cho ngôn ngữ. Mặc dù Aspose.Words hỗ trợ nhiều ngôn ngữ nhưng một số ngôn ngữ có thể không được hỗ trợ hoặc âm tiết có thể không có sẵn cho chúng. Kiểm tra tài liệu Aspose.Words để tìm hiểu ngôn ngữ nào được hỗ trợ cho việc sắp xếp âm tiết.
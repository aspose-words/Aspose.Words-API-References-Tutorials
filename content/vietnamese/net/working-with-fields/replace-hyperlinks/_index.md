---
title: Thay thế siêu liên kết
linktitle: Thay thế siêu liên kết
second_title: API xử lý tài liệu Aspose.Words
description: Thay thế siêu liên kết trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước để thay thế siêu liên kết.
type: docs
weight: 10
url: /vi/net/working-with-fields/replace-hyperlinks/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# sau đây để thay thế siêu liên kết bằng chức năng Aspose.Words cho .NET. Đảm bảo bạn đã đưa thư viện Aspose.Words vào dự án của mình trước khi sử dụng mã này.

## Bước 1: Đặt đường dẫn thư mục tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Hãy chắc chắn chỉ định đường dẫn chính xác tới thư mục tài liệu của bạn có chứa`Hyperlinks.docx` tài liệu.

## Bước 2: Tải tài liệu chứa siêu liên kết

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Ở đây chúng ta đang tạo một thể hiện của`Document` lớp từ tệp được chỉ định.

## Bước 3: Duyệt qua các trường để tìm siêu liên kết

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Một số siêu liên kết có thể là cục bộ (liên kết đến dấu trang bên trong tài liệu), chúng tôi bỏ qua chúng.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Vòng lặp này đi qua tất cả các trường trong tài liệu để tìm kiếm các trường thuộc loại`FieldType.FieldHyperlink` . Khi tìm thấy trường thuộc loại này, chúng tôi sẽ kiểm tra xem đó có phải là liên kết cục bộ hay không bằng cách kiểm tra`SubAddress` tài sản. Nếu không, chúng tôi thay thế địa chỉ liên kết bằng`"http://www.aspose.com"` và kết quả với`"Aspose - The .NET & Java Component Editor"`.

## Bước 4: Lưu tài liệu đã sửa đổi

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Cuối cùng, chúng tôi lưu tài liệu đã sửa đổi cùng với các siêu liên kết được thay thế vào một tệp được chỉ định.

### Mã nguồn ví dụ để thay thế siêu liên kết bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Một số siêu liên kết có thể là cục bộ (liên kết đến dấu trang bên trong tài liệu), chúng tôi bỏ qua chúng.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Đây là mã nguồn mẫu để thay thế các siêu liên kết trong tài liệu bằng Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể thay thế siêu liên kết trong tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để thay thế các siêu liên kết trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng`Document.Range.Replace`phương pháp chỉ định văn bản cần tìm kiếm và văn bản thay thế. Đảm bảo sử dụng các tùy chọn thích hợp để đặt tham số tìm kiếm và thay thế.

#### Câu hỏi: Có thể chỉ thay thế một số siêu liên kết nhất định trong tài liệu Word bằng Aspose.Words cho .NET không?

Trả lời: Có, chỉ có thể thay thế một số siêu liên kết nhất định trong tài liệu Word bằng Aspose.Words cho .NET. Bạn có thể lọc các siêu liên kết cần thay thế bằng tiêu chí cụ thể, chẳng hạn như URL liên kết, văn bản liên kết hoặc bất kỳ thuộc tính liên quan nào khác. Sau đó, bạn chỉ có thể áp dụng thay thế cho các siêu liên kết phù hợp.

#### Câu hỏi: Làm cách nào tôi có thể bỏ qua các siêu liên kết trong đầu trang, chân trang hoặc chú thích cuối trang khi thay thế bằng Aspose.Words cho .NET?

Trả lời: Để bỏ qua các siêu liên kết trong đầu trang, chân trang hoặc chú thích cuối trang khi thay thế bằng Aspose.Words cho .NET, bạn có thể sử dụng các tùy chọn tìm kiếm nâng cao và chỉ định giới hạn tìm kiếm thích hợp. Ví dụ: bạn có thể giới hạn tìm kiếm trong các phần chính của tài liệu và loại trừ đầu trang, chân trang hoặc chú thích cuối trang.

#### Hỏi: Có thể thay thế siêu liên kết bằng liên kết nội bộ đến các phần khác của tài liệu không?

 Trả lời: Có, có thể thay thế các siêu liên kết bằng các liên kết nội bộ đến các phần khác của tài liệu bằng Aspose.Words for .NET. Bạn có thể sử dụng các neo hoặc id văn bản để tạo các liên kết nội bộ và sau đó thay thế chúng bằng cách sử dụng`Document.Range.Replace` bằng các phương án thích hợp.

#### Câu hỏi: Việc thay thế siêu liên kết bằng Aspose.Words cho .NET có giữ nguyên các thuộc tính liên kết, chẳng hạn như màu sắc hoặc kiểu không?

Trả lời: Có, khi thay thế siêu liên kết bằng Aspose.Words cho .NET, các thuộc tính liên kết như màu sắc hoặc kiểu sẽ được giữ lại. Bạn có thể chỉ định các thuộc tính định dạng tương tự trong văn bản thay thế để đạt được kết quả nhất quán.
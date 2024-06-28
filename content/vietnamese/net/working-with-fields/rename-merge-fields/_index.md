---
title: Đổi tên các trường hợp nhất
linktitle: Đổi tên các trường hợp nhất
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, bạn sẽ tìm hiểu cách đổi tên các trường hợp nhất trong tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/rename-merge-fields/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới sử dụng tính năng đổi tên trường hợp nhất của Aspose.Words cho .NET. Thực hiện cẩn thận từng bước để có được kết quả mong muốn.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã được cung cấp, bạn phải chỉ định thư mục tài liệu của mình. Thay thế giá trị "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo tài liệu và chèn các trường phối

Chúng ta bắt đầu bằng cách tạo một tài liệu mới và sử dụng một`DocumentBuilder` để chèn các trường hợp nhất.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Bước 3: Đổi tên các trường hợp nhất

Chúng tôi lặp qua từng trường trong phạm vi tài liệu và nếu đó là trường hợp nhất, chúng tôi đổi tên trường bằng cách thêm "_Đã đổi tên" hậu tố.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Bước 4: Lưu tài liệu

 Cuối cùng, chúng tôi gọi`Save()` phương pháp lưu tài liệu đã sửa đổi.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Ví dụ về mã nguồn để đổi tên các trường hợp nhất bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và chèn các trường hợp nhất.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Đổi tên các trường hợp nhất.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Lưu tài liệu.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Hãy làm theo các bước sau để đổi tên các trường hợp nhất trong tài liệu của bạn bằng Aspose.Words for .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể đổi tên các trường đã hợp nhất trong tài liệu Word bằng Aspose.Words cho .NET?

 Đáp: Để đổi tên các trường đã hợp nhất trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể lặp qua các trường trong tài liệu bằng cách sử dụng lệnh`FieldMergingArgs` lớp và sử dụng`FieldMergingArgs.FieldName` phương pháp đổi tên các trường.

#### Câu hỏi: Có thể chỉ đổi tên một số trường đã hợp nhất nhất định trong tài liệu Word bằng Aspose.Words cho .NET không?

Trả lời: Có, chỉ có thể đổi tên một số trường đã hợp nhất nhất định trong tài liệu Word bằng Aspose.Words cho .NET. Bạn có thể lọc những trường cần đổi tên bằng tiêu chí cụ thể, chẳng hạn như tên trường hoặc các thuộc tính liên quan khác. Sau đó, bạn có thể đổi tên các trường tương ứng bằng cách sử dụng`FieldMergingArgs.FieldName` phương pháp.

#### Câu hỏi: Làm cách nào để kiểm tra xem trường đã hợp nhất có được đổi tên thành công trong tài liệu Word bằng Aspose.Words cho .NET hay không?

 Đáp: Để kiểm tra xem trường đã hợp nhất có được đổi tên thành công trong tài liệu Word bằng Aspose.Words cho .NET hay không, bạn có thể sử dụng hàm`FieldMergedArgs` lớp và truy cập`FieldMergedArgs.IsMerged` thuộc tính để xác định xem trường có được đổi tên bằng hit hay không.

#### Câu hỏi: Hậu quả của việc đổi tên trường đã hợp nhất trong tài liệu Word bằng Aspose.Words cho .NET là gì?

Trả lời: Khi bạn đổi tên trường đã hợp nhất trong tài liệu Word bằng Aspose.Words cho .NET, nó sẽ thay đổi tên của trường trong tài liệu, điều này có thể ảnh hưởng đến chức năng hoặc quy trình khác phụ thuộc vào tên trường. Hãy nhớ cân nhắc những hậu quả tiềm ẩn này trước khi đổi tên các trường đã hợp nhất.

#### Câu hỏi: Có thể khôi phục tên ban đầu của trường đã hợp nhất sau khi đổi tên nó bằng Aspose.Words cho .NET không?

Trả lời: Có, có thể khôi phục tên ban đầu của trường đã hợp nhất sau khi đổi tên nó bằng Aspose.Words cho .NET. Bạn có thể lưu trữ tên ban đầu của trường trong một biến hoặc danh sách, sau đó sử dụng thông tin đó để khôi phục tên ban đầu nếu cần.
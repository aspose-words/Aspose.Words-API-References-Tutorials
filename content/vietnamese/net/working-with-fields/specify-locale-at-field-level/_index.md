---
title: Chỉ định ngôn ngữ ở cấp trường
linktitle: Chỉ định ngôn ngữ ở cấp trường
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chỉ định bản địa hóa cấp trường trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/specify-locale-at-field-level/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# sau đây cho phép chỉ định bản địa hóa ở cấp trường bằng tính năng Aspose.Words for .NET. Đảm bảo bạn đã đưa thư viện Aspose.Words vào dự án của mình trước khi sử dụng mã này.

## Bước 1: Đặt đường dẫn thư mục tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu của bạn nơi tài liệu đã chỉnh sửa sẽ được lưu.

## Bước 2: Tạo trình tạo tài liệu

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Ở đây chúng ta đang tạo một thể hiện của`DocumentBuilder` class sẽ cho phép chúng ta thêm các trường vào tài liệu.

## Bước 3: Chèn trường ngày với vị trí cụ thể

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 Chúng tôi sử dụng trình tạo tài liệu để chèn một trường loại`FieldType.FieldDate` vào tài liệu. Bằng cách thiết lập`LocaleId`tài sản để`1049`, chúng tôi chỉ định bản địa hóa tiếng Nga cho trường này.

## Bước 4: Lưu tài liệu đã sửa đổi

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Cuối cùng, chúng tôi lưu tài liệu đã sửa đổi với vị trí đã chỉ định vào một tệp được chỉ định.

### Mã nguồn mẫu để chỉ định bản địa hóa cấp trường với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Đây là mã nguồn mẫu để chỉ định bản địa hóa ở cấp trường trong tài liệu bằng Aspose.Words cho .NET. Bạn có thể sử dụng mã này để chèn các trường ngày ở các vị trí cụ thể trong tài liệu Word của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể chỉ định ngôn ngữ cấp trường trong Aspose.Words cho .NET?

 Trả lời: Để chỉ định ngôn ngữ ở cấp trường trong Aspose.Words cho .NET, bạn có thể sử dụng`FieldOptions` lớp học và nó`FieldLocale` thuộc tính để đặt ngôn ngữ mong muốn. Ví dụ, bạn có thể sử dụng`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` để chỉ định ngôn ngữ tiếng Pháp (Pháp).

#### Câu hỏi: Có thể chỉ định một ngôn ngữ khác cho từng trường trong Aspose.Words cho .NET không?

 Trả lời: Có, có thể chỉ định một ngôn ngữ khác cho từng trường trong Aspose.Words for .NET. Bạn có thể dùng`FieldOptions.FieldLocale` thuộc tính trước khi tạo hoặc cập nhật một trường cụ thể để gán cho nó một ngôn ngữ khác.

#### Câu hỏi: Làm cách nào tôi có thể lấy ngôn ngữ hiện đang được sử dụng cho một trường trong Aspose.Words cho .NET?

 Đáp: Để lấy ngôn ngữ hiện đang được sử dụng cho một trường trong Aspose.Words cho .NET, bạn có thể sử dụng ngôn ngữ của trường đó`Field.LocaleId` tài sản. Điều này sẽ cho phép bạn lấy mã định danh miền địa phương được liên kết với trường.
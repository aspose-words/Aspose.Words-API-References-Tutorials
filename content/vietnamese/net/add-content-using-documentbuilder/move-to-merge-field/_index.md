---
title: Di chuyển để hợp nhất trường trong tài liệu Word
linktitle: Di chuyển để hợp nhất trường trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách triển khai tính năng Di chuyển để Hợp nhất Trường trong tài liệu word của Aspose.Words cho .NET bằng hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/move-to-merge-field/
---
Trong ví dụ này, chúng ta sẽ khám phá tính năng Di chuyển để Hợp nhất Trường trong tài liệu word của Aspose.Words cho .NET. Aspose.Words là một thư viện thao tác tài liệu mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi tài liệu Word theo chương trình. Tính năng Move To Merge Field cho phép chúng ta điều hướng để hợp nhất các trường trong tài liệu và thực hiện các thao tác khác nhau trên chúng.


## Giải thích mã nguồn từng bước

Chúng ta hãy xem mã nguồn từng bước một để hiểu cách sử dụng tính năng Move To Merge Field bằng Aspose.Words cho .NET.

## Bước 1: Khởi tạo tài liệu và trình tạo tài liệu

Đầu tiên, khởi tạo các đối tượng Document và DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2 Chèn trường phối và thêm văn bản sau trường đó

Sử dụng phương thức InsertField của lớp DocumentBuilder để chèn trường hợp nhất, sau đó thêm văn bản vào sau trường đó:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Bước 3: Con trỏ của trình tạo hiện ở cuối tài liệu.

```csharp
Assert.Null(builder.CurrentNode);
```
## Bước 4: Di chuyển con trỏ của trình tạo tài liệu đến trường hợp nhất

Để di chuyển con trỏ của trình tạo tài liệu đến trường hợp nhất, hãy sử dụng phương thức MoveToField của lớp DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Thêm văn bản ngay sau trường hợp nhất

Khi con trỏ của trình tạo tài liệu nằm trong trường hợp nhất, bạn có thể thêm văn bản ngay sau nó bằng phương pháp Viết:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Mã nguồn ví dụ cho Di chuyển để hợp nhất trường bằng Aspose.Words cho .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn một trường bằng DocumentBuilder và thêm một dòng văn bản sau trường đó.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Con trỏ của trình tạo hiện đang ở cuối tài liệu.
Assert.Null(builder.CurrentNode);
// Chúng ta có thể di chuyển trình tạo đến một trường như thế này, đặt con trỏ ở ngay sau trường đó.
builder.MoveToField(field, true);

// Lưu ý rằng con trỏ ở vị trí phía sau nút FieldEnd của trường, nghĩa là chúng ta không thực sự ở bên trong trường.
// Nếu chúng ta muốn di chuyển DocumentBuilder vào bên trong một trường,
// chúng ta sẽ cần di chuyển nó đến nút FieldStart hoặc FieldSeparator của một trường bằng phương thức DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Phần kết luận

chúng tôi đã khám phá tính năng Move To Merge Field của Aspose.Words cho .NET. Chúng tôi đã học cách điều hướng để hợp nhất các trường trong tài liệu bằng cách sử dụng lớp DocumentBuilder và thực hiện các thao tác trên chúng. Tính năng này hữu ích khi xử lý từ theo chương trình bằng cách hợp nhất

### Câu hỏi thường gặp về di chuyển sang trường hợp nhất trong tài liệu word

#### Câu hỏi: Mục đích của tính năng Move To Merge Field trong Aspose.Words dành cho .NET là gì?

Trả lời: Tính năng Move To Merge Field trong Aspose.Words for .NET cho phép các nhà phát triển điều hướng để hợp nhất các trường trong tài liệu Word và thực hiện các thao tác khác nhau trên chúng theo chương trình. Trường phối là các phần giữ chỗ đặc biệt được sử dụng trong tài liệu Word cho các hoạt động phối thư.

#### Câu hỏi: Làm cách nào tôi có thể chèn trường phối vào tài liệu Word bằng Aspose.Words cho .NET?

Đáp: Bạn có thể sử dụng phương thức InsertField của lớp DocumentBuilder để chèn trường hợp nhất vào tài liệu. Sau khi chèn trường phối, bạn có thể thêm nội dung, chẳng hạn như văn bản, vào trước hoặc sau trường bằng phương pháp Viết.

#### Câu hỏi: Làm cách nào để di chuyển con trỏ của trình tạo tài liệu đến một trường phối cụ thể?

Đáp: Để di chuyển con trỏ của trình tạo tài liệu đến một trường hợp nhất cụ thể, hãy sử dụng phương thức MoveToField của lớp DocumentBuilder và chuyển trường đó làm tham số. Điều này sẽ đặt con trỏ ngay sau trường hợp nhất.

#### Câu hỏi: Tôi có thể thêm văn bản vào trường hợp nhất bằng tính năng Di chuyển để hợp nhất trường không?

Trả lời: Không, tính năng Di chuyển để Hợp nhất Trường đặt con trỏ của trình tạo tài liệu ngay sau trường hợp nhất. Để thêm văn bản bên trong trường hợp nhất, bạn có thể sử dụng phương thức DocumentBuilder.MoveTo để di chuyển con trỏ đến nút FieldStart hoặc FieldSeparator của trường hợp nhất.

#### Câu hỏi: Làm cách nào tôi có thể thực hiện các thao tác trộn thư bằng Aspose.Words cho .NET?

Đáp: Aspose.Words for .NET cung cấp hỗ trợ rộng rãi cho các hoạt động trộn thư. Bạn có thể sử dụng lớp MailMerge để thực hiện trộn thư bằng cách sử dụng dữ liệu từ nhiều nguồn khác nhau như mảng, tập dữ liệu hoặc nguồn dữ liệu tùy chỉnh.
---
title: Mã nội tuyến
linktitle: Mã nội tuyến
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách viết mã nội tuyến với Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/inline-code/
---

Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách sử dụng tính năng mã nội tuyến với Aspose.Words cho .NET. Mã nội tuyến được sử dụng để thể hiện trực quan các đoạn mã bên trong một đoạn văn.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Thêm kiểu cho mã nội tuyến

 Chúng tôi sẽ thêm kiểu tùy chỉnh cho mã nội tuyến bằng cách sử dụng`Styles.Add` phương pháp của`Document` sự vật. Trong ví dụ này, chúng tôi đang tạo một kiểu có tên là "InlineCode" cho mã nội tuyến có dấu gạch ngược mặc định.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Bước 3: Thêm mã nội tuyến

Bây giờ chúng ta có thể thêm mã nội tuyến bằng kiểu tùy chỉnh "InlineCode". Trong ví dụ này, chúng tôi thêm hai đoạn văn bản có số dấu gạch chéo ngược khác nhau.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Mã nguồn ví dụ cho Mã nội tuyến với Aspose.Words cho .NET

```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Số dấu tích ngược bị bỏ sót, một dấu tích ngược sẽ được sử dụng theo mặc định.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Sẽ có 3 backticks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng chức năng mã nội tuyến với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể sử dụng mã nội tuyến trong Aspose.Words?

 Trả lời: Để sử dụng mã nội tuyến trong Aspose.Words, bạn có thể sử dụng các thẻ thích hợp để bao quanh văn bản cần định dạng dưới dạng mã nội tuyến. Ví dụ: bạn có thể sử dụng`<code>` hoặc`<kbd>` thẻ để bao quanh văn bản được định dạng dưới dạng mã nội tuyến.

#### Câu hỏi: Có thể chỉ định phông chữ hoặc màu mã nội tuyến trong Aspose.Words không?

 Đáp: Có, bạn có thể chỉ định phông chữ hoặc màu sắc của mã nội tuyến trong Aspose.Words. Bạn có thể dùng`Font.Name` Và`Font.Color` thuộc tính của`Run` đối tượng để đặt phông chữ và màu sắc của mã nội tuyến. Ví dụ, bạn có thể sử dụng`run.Font.Name = "Courier New"` để chỉ định phông chữ cho mã nội tuyến và`run.Font.Color = Color.Blue`để chỉ định màu sắc.

#### Hỏi: Tôi có thể sử dụng mã nội tuyến trong đoạn văn có chứa các thành phần văn bản khác không?

 Đáp: Có, bạn có thể sử dụng mã nội tuyến trong đoạn văn có chứa các thành phần văn bản khác. Bạn có thể tạo nhiều`Run` các đối tượng đại diện cho các phần khác nhau của đoạn văn, sau đó sử dụng thẻ mã nội tuyến để chỉ định dạng các phần cụ thể dưới dạng mã nội tuyến. Sau đó, bạn có thể thêm chúng vào đoạn văn bằng cách sử dụng`Paragraph.AppendChild(run)` phương pháp.
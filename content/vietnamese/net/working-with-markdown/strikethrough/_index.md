---
title: Gạch ngang
linktitle: Gạch ngang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách áp dụng kiểu văn bản gạch ngang với Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/strikethrough/
---


Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách áp dụng kiểu văn bản gạch ngang bằng Aspose.Words cho .NET. Văn bản gạch ngang được sử dụng để chỉ ra rằng văn bản đã bị xóa hoặc không còn hợp lệ.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Áp dụng kiểu văn bản gạch ngang

 Chúng tôi sẽ kích hoạt kiểu văn bản gạch ngang bằng cách đặt`StrikeThrough` tài sản của`Font` chủ đề`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Bước 3: Thêm văn bản gạch ngang

 Bây giờ chúng ta có thể thêm văn bản gạch ngang bằng cách sử dụng trình tạo tài liệu`Writeln` phương pháp.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Mã nguồn mẫu cho văn bản gạch ngang bằng Aspose.Words for .NET

```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Tạo văn bản gạch ngang.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Xin chúc mừng! Bây giờ bạn đã học cách áp dụng kiểu văn bản gạch ngang với Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể thêm văn bản gạch ngang trong Aspose.Words?

 Đáp: Để thêm văn bản gạch ngang trong Aspose.Words, bạn có thể sử dụng`Font.StrikeThrough` tài sản của`Run` sự vật. Bạn có thể đặt thuộc tính này thành`true` để thêm văn bản gạch ngang vào văn bản cụ thể. Ví dụ, bạn có thể sử dụng`run.Font.StrikeThrough=true` để thêm văn bản gạch ngang vào`Run` sự vật.

#### Hỏi: Có thể thêm văn bản gạch ngang vào nhiều đoạn văn bản trong cùng một đoạn không?

 Đáp: Có, bạn có thể thêm văn bản gạch ngang vào nhiều phần văn bản trong một đoạn văn bằng cách sử dụng nhiều`Run` các đối tượng. Bạn có thể tạo nhiều`Run` các đối tượng và thiết lập`Font.StrikeThrough`tài sản để`true` để mỗi đối tượng thêm văn bản gạch ngang vào các phần văn bản mong muốn. Sau đó, bạn có thể thêm chúng vào đoạn văn bằng cách sử dụng`Paragraph.AppendChild(run)` phương pháp.

#### Câu hỏi: Tôi có thể thêm văn bản gạch ngang vào văn bản trong bảng hoặc ô trong Aspose.Words không?

 Đáp: Có, bạn có thể thêm văn bản gạch ngang vào văn bản trong bảng hoặc ô trong Aspose.Words. Bạn có thể chuyển đến ô hoặc đoạn văn bạn muốn bằng các phương pháp thích hợp rồi áp dụng định dạng văn bản gạch ngang bằng cách sử dụng`Font.StrikeThrough` tài sản của`Run` hoặc`Paragraph` sự vật.
---
title: Chữ in đậm
linktitle: Chữ in đậm
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách in đậm văn bản với Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/bold-text/
---

Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách in đậm văn bản bằng Aspose.Words cho .NET. Văn bản in đậm làm cho văn bản hiển thị rõ hơn và nổi bật hơn.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: In đậm văn bản

 Chúng ta có thể in đậm văn bản bằng cách đặt trình tạo tài liệu`Font.Bold`tài sản để`true`.

```csharp
builder.Font.Bold = true;
```

## Bước 3: Thêm nội dung vào tài liệu

 Bây giờ chúng ta có thể thêm nội dung vào tài liệu bằng các phương pháp của trình tạo tài liệu, chẳng hạn như`Writeln`, trong đó thêm một dòng văn bản.

```csharp
builder.Writeln("This text will be bold");
```

## Mã nguồn ví dụ cho văn bản in đậm bằng Aspose.Words cho .NET


```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Làm đậm văn bản.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Xin chúc mừng! Bây giờ bạn đã học cách in đậm văn bản bằng Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để in đậm văn bản trong Aspose.Words?

 Đáp: Để in đậm văn bản trong Aspose.Words, bạn có thể sử dụng`Font.Bold` tài sản của`Run` sự vật. Bạn có thể đặt thuộc tính này thành`true` để in đậm văn bản cụ thể. Ví dụ, bạn có thể sử dụng`run.Font.Bold=true` để in đậm văn bản bên trong`Run` sự vật.

#### Hỏi: Có thể in đậm nhiều đoạn văn bản trong cùng một đoạn văn không?

 Đáp: Có, bạn có thể in đậm nhiều đoạn văn bản trong một đoạn văn bằng cách sử dụng nhiều`Run` các đối tượng. Bạn có thể tạo nhiều`Run` các đối tượng và thiết lập`Font.Bold`tài sản để`true` để mỗi đối tượng in đậm những phần văn bản mong muốn. Sau đó, bạn có thể thêm chúng vào đoạn văn bằng cách sử dụng`Paragraph.AppendChild(run)` phương pháp.

#### Câu hỏi: Tôi có thể in đậm văn bản trong bảng hoặc ô trong Aspose.Words không?

 Đáp: Có, bạn có thể in đậm văn bản trong bảng hoặc ô trong Aspose.Words. Bạn có thể điều hướng đến ô hoặc đoạn văn bạn muốn bằng các phương pháp thích hợp rồi áp dụng định dạng in đậm bằng cách sử dụng`Font.Bold` tài sản của`Run` hoặc`Paragraph` sự vật.
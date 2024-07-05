---
title: Phá vỡ liên kết chuyển tiếp trong tài liệu Word
linktitle: Phá vỡ liên kết chuyển tiếp trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách ngắt liên kết chuyển tiếp trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET là một thư viện mạnh mẽ cung cấp nhiều tính năng khác nhau để Xử lý Từ bằng tài liệu Microsoft Word theo chương trình. Một trong những tính năng hữu ích của nó là khả năng ngắt các liên kết chuyển tiếp trong tài liệu word. Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn trong C# trình bày cách ngắt liên kết chuyển tiếp trong tài liệu word bằng Aspose.Words cho .NET.

## Bước 1: Xem trước mã nguồn C#

Mã nguồn C# được cung cấp tập trung vào tính năng "Break A Link" của Aspose.Words for .NET. Nó cho thấy cách ngắt liên kết ở dạng TextBox bên trong tài liệu. Mã trình bày các tình huống khác nhau để phá vỡ liên kết và cung cấp hướng dẫn rõ ràng về cách đạt được kết quả mong muốn.

## Bước 2: Thiết lập tài liệu và tạo hình TextBox

 Để bắt đầu, chúng ta cần thiết lập tài liệu và tạo hình dạng TextBox. Đoạn mã sau khởi tạo một phiên bản mới của`Document` lớp và tạo hình dạng hộp văn bản:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Bước 3: Ngắt liên kết chuyển tiếp trong TextBox

 Để ngắt một liên kết chuyển tiếp trong TextBox, chúng ta có thể sử dụng`BreakForwardLink()` phương pháp. Phương pháp này phá vỡ liên kết đến hình tiếp theo trong chuỗi. Đoạn mã sau đây cho thấy cách ngắt liên kết chuyển tiếp:

```csharp
textBox.BreakForwardLink();
```

## Bước 4: Phá vỡ liên kết chuyển tiếp bằng cách đặt giá trị null

 Ngoài ra, chúng ta có thể ngắt liên kết chuyển tiếp bằng cách đặt thuộc tính của TextBox`Next`tài sản để`null`. Điều này có hiệu quả loại bỏ kết nối với hình dạng tiếp theo. Đoạn mã sau đây thể hiện cách tiếp cận này:

```csharp
textBox. Next = null;
```

## Bước 5: Phá vỡ liên kết dẫn đến TextBox

 Trong một số trường hợp, chúng ta cần ngắt liên kết dẫn đến hình dạng TextBox. Chúng ta có thể đạt được điều này bằng cách gọi`BreakForwardLink()` phương pháp trên`Previous` biểu mẫu sẽ phá vỡ liên kết đến TextBox. Đây là một ví dụ về cách phá vỡ một liên kết như vậy:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Mã nguồn mẫu để ngắt liên kết với Aspose.Words cho .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Phá vỡ liên kết chuyển tiếp.
textBox.BreakForwardLink();

// Phá vỡ liên kết chuyển tiếp bằng cách đặt giá trị null.
textBox. Next = null;

// Phá vỡ một liên kết dẫn đến hộp văn bản này.
textBox.Previous?.BreakForwardLink();
```

## Phần kết luận

Xin chúc mừng! Bây giờ bạn đã học cách ngắt các liên kết chuyển hướng trong tài liệu Word bằng thư viện Aspose.Words cho .NET. Bằng cách làm theo các bước trong hướng dẫn này, bạn có thể thiết lập tài liệu, tạo hình dạng TextBox và ngắt các liên kết chuyển hướng bằng các phương pháp khác nhau.

### Câu hỏi thường gặp về liên kết chuyển tiếp trong tài liệu word

#### Câu hỏi: Thư viện nào được sử dụng để ngắt các liên kết chuyển hướng trong tài liệu Word bằng Aspose.Words cho .NET?

Đáp: Để ngắt các liên kết chuyển hướng trong tài liệu Word bằng Aspose.Words cho .NET, thư viện được sử dụng là Aspose.Words cho .NET.

#### Hỏi: Làm cách nào để ngắt liên kết chuyển hướng trong TextBox?

 Trả lời: Để ngắt liên kết chuyển tiếp trong TextBox, bạn có thể sử dụng`BreakForwardLink()` phương pháp. Phương pháp này phá vỡ liên kết đến hình tiếp theo trong chuỗi.

#### Hỏi: Làm cách nào để phá vỡ liên kết chuyển hướng bằng cách đặt giá trị null?

Đáp: Ngoài ra, bạn có thể ngắt liên kết chuyển hướng bằng cách đặt`Next` thuộc tính của TextBox để`null`. Điều này có hiệu quả loại bỏ kết nối với hình dạng tiếp theo.

#### Hỏi: Làm cách nào để ngắt liên kết dẫn đến TextBox?

 Trả lời: Trong một số trường hợp, bạn cần ngắt liên kết dẫn đến TextBox. Bạn có thể đạt được điều này bằng cách gọi`BreakForwardLink()` phương pháp trên`Previous` biểu mẫu sẽ phá vỡ liên kết đến TextBox.

#### Câu hỏi: Chúng tôi có thể ngắt liên kết chuyển hướng trên các phần tử không phải là TextBox không?

Trả lời: Có, với Aspose.Words cho .NET, bạn có thể ngắt liên kết chuyển hướng trên các thành phần khác nhau như đoạn văn, bảng, hình ảnh, v.v. Quá trình này có thể khác nhau tùy thuộc vào mục cụ thể mà bạn muốn ngắt liên kết.
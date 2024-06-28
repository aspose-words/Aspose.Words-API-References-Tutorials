---
title: Hiển thị ẩn nội dung được đánh dấu trong tài liệu Word
linktitle: Hiển thị ẩn nội dung được đánh dấu trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tự động hiển thị hoặc ẩn nội dung được đánh dấu trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước toàn diện này.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Giới thiệu

Này! Bạn đã bao giờ muốn kiểm soát khả năng hiển thị của nội dung cụ thể trong tài liệu Word dựa trên các điều kiện nhất định chưa? Với Aspose.Words for .NET, bạn có thể tự động hiển thị hoặc ẩn nội dung được đánh dấu trang chỉ bằng một vài dòng mã. Trong hướng dẫn này, tôi sẽ hướng dẫn bạn từng bước trong quy trình, đảm bảo bạn hiểu từng phần của mã. Cuối cùng, bạn sẽ thành thạo trong việc thao tác đánh dấu trang trong tài liệu Word. Bắt đầu nào!

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có mọi thứ mình cần:

1. Kiến thức cơ bản về C#: Bạn nên thành thạo với cú pháp và khái niệm C#.
2.  Aspose.Words cho .NET: Tải xuống[đây](https://releases.aspose.com/words/net/) . Nếu bạn chưa sẵn sàng mua hàng, bạn có thể bắt đầu bằng[dùng thử miễn phí](https://releases.aspose.com/).
3. Visual Studio: Mọi phiên bản gần đây đều có thể hoạt động nhưng bạn nên sử dụng phiên bản mới nhất.
4. .NET Framework: Đảm bảo nó được cài đặt trên máy của bạn.

Sẵn sàng để bắt đầu? Tuyệt vời! Hãy bắt đầu bằng cách nhập các không gian tên cần thiết.

## Nhập không gian tên

Để sử dụng Aspose.Words cho .NET, chúng ta cần nhập các không gian tên được yêu cầu. Bước này đảm bảo chúng ta có quyền truy cập vào tất cả các lớp và phương thức mà chúng ta sẽ sử dụng.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Các không gian tên này rất quan trọng để làm việc với tài liệu Word và thao tác với nội dung của chúng.

## Bước 1: Thiết lập tài liệu

Trước tiên, hãy tạo một tài liệu Word mới và trình tạo tài liệu. Trình tạo tài liệu giúp chúng ta dễ dàng thêm và thao tác nội dung trong tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Trong bước này, chúng tôi khởi tạo một tài liệu mới và trình tạo tài liệu. Điều này thiết lập môi trường của chúng tôi cho các hoạt động tiếp theo.

## Bước 2: Thêm nội dung được đánh dấu

Tiếp theo, chúng ta sẽ thêm một số nội dung vào tài liệu và tạo dấu trang xung quanh nó. Dấu trang này sẽ giúp chúng ta xác định và thao tác với nội dung.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Ở đây, chúng ta thêm một số văn bản trước và sau nội dung được đánh dấu. Các`StartBookmark` Và`EndBookmark` các phương thức xác định ranh giới của dấu trang.

## Bước 3: Chèn trường có điều kiện

Để kiểm soát khả năng hiển thị của nội dung được đánh dấu, chúng tôi sẽ sử dụng trường có điều kiện. Trường này sẽ kiểm tra một điều kiện và hiển thị hoặc ẩn nội dung tương ứng.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

Trong bước này, chúng tôi chèn trường IF để kiểm tra giá trị của dấu trang. Nếu giá trị là "true", nó sẽ hiển thị "Hiển thị"; nếu không nó sẽ hiển thị "Ẩn".

## Bước 4: Sắp xếp lại các nút

Tiếp theo, chúng ta cần sắp xếp lại các nút để đảm bảo logic có điều kiện được áp dụng chính xác cho nội dung được đánh dấu.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Ở đây, chúng tôi di chuyển các nút xung quanh để đảm bảo điều kiện bao gồm đúng nội dung được đánh dấu.

## Bước 5: Thực hiện trộn thư

Cuối cùng, chúng tôi sẽ thực hiện trộn thư để đặt giá trị của dấu trang và xác định xem nội dung sẽ được hiển thị hay ẩn.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Bước này đặt giá trị dấu trang thành "true", điều này sẽ hiển thị nội dung dựa trên điều kiện của chúng tôi.

## Bước 6: Lưu tài liệu

Sau tất cả các thao tác, bước cuối cùng là lưu tài liệu đã sửa đổi.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Ở đây, chúng tôi lưu tài liệu với tên tệp mô tả để chỉ ra những thay đổi.

## Phần kết luận

 Và thế là xong! Bạn đã học thành công cách hiển thị hoặc ẩn nội dung được đánh dấu trong tài liệu Word bằng Aspose.Words for .NET. Hướng dẫn này đề cập đến việc tạo tài liệu, thêm dấu trang, chèn các trường có điều kiện, sắp xếp lại các nút và thực hiện phối thư. Aspose.Words cung cấp rất nhiều tính năng, vì vậy đừng ngần ngại khám phá[Tài liệu API](https://reference.aspose.com/words/net/) để có những khả năng nâng cao hơn.

## Câu hỏi thường gặp

### 1. Aspose.Words cho .NET là gì?

Aspose.Words for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi tài liệu Word theo chương trình. Nó được sử dụng rộng rãi cho các nhiệm vụ tự động hóa tài liệu.

### 2. Tôi có thể sử dụng Aspose.Words cho .NET miễn phí không?

 Bạn có thể thử Aspose.Words cho .NET bằng cách sử dụng[dùng thử miễn phí](https://releases.aspose.com/). Để sử dụng lâu dài, bạn sẽ cần phải mua giấy phép.

### 3. Làm cách nào để sửa đổi các thuộc tính khác của dấu trang?

 Aspose.Words cho phép bạn thao tác các thuộc tính khác nhau của dấu trang, chẳng hạn như văn bản và vị trí của dấu trang. Tham khảo đến[Tài liệu API](https://reference.aspose.com/words/net/) để được hướng dẫn chi tiết.

### 4. Làm cách nào để nhận được hỗ trợ cho Aspose.Words cho .NET?

Bạn có thể nhận được hỗ trợ bằng cách truy cập[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/words/8).

### 5. Tôi có thể xử lý các loại nội dung khác bằng Aspose.Words cho .NET không?

Có, Aspose.Words for .NET hỗ trợ nhiều loại thao tác nội dung khác nhau, bao gồm văn bản, hình ảnh, bảng, v.v.
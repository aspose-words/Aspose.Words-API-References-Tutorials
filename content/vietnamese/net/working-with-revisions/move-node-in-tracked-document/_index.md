---
title: Di chuyển nút trong tài liệu được theo dõi
linktitle: Di chuyển nút trong tài liệu được theo dõi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách di chuyển các nút trong tài liệu Word được theo dõi bằng Aspose.Words cho .NET với hướng dẫn từng bước chi tiết của chúng tôi. Hoàn hảo cho các nhà phát triển.
type: docs
weight: 10
url: /vi/net/working-with-revisions/move-node-in-tracked-document/
---
## Giới thiệu

Xin chào những người đam mê Aspose.Words! Nếu bạn cần di chuyển một nút trong tài liệu Word trong khi theo dõi các bản sửa đổi thì bạn đã đến đúng nơi. Hôm nay, chúng ta sẽ đi sâu vào cách đạt được điều này bằng Aspose.Words for .NET. Bạn không chỉ tìm hiểu quy trình từng bước mà còn học được một số mẹo và thủ thuật để giúp thao tác tài liệu của bạn trơn tru và hiệu quả.

## Điều kiện tiên quyết

Trước khi bắt tay vào làm một số mã, hãy đảm bảo rằng bạn có mọi thứ mình cần:

-  Aspose.Words cho .NET: Tải xuống[đây](https://releases.aspose.com/words/net/).
- Môi trường .NET: Đảm bảo bạn đã thiết lập môi trường phát triển .NET tương thích.
- Kiến thức cơ bản về C#: Hướng dẫn này giả sử bạn có hiểu biết cơ bản về C#.

Có mọi thứ? Tuyệt vời! Hãy chuyển sang các không gian tên mà chúng ta cần nhập.

## Nhập không gian tên

Trước tiên, chúng ta cần nhập các không gian tên cần thiết. Đây là những điều cần thiết để làm việc với Aspose.Words và xử lý các nút tài liệu.

```csharp
using Aspose.Words;
using System;
```

Được rồi, hãy chia quy trình thành các bước có thể quản lý được. Mỗi bước sẽ được giải thích chi tiết để đảm bảo bạn hiểu điều gì đang xảy ra ở mọi thời điểm.

## Bước 1: Khởi tạo tài liệu

 Để bắt đầu, chúng ta cần khởi tạo một tài liệu mới và sử dụng một`DocumentBuilder` để thêm một số đoạn văn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bổ sung một số đoạn văn
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// Kiểm tra số đoạn văn ban đầu
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Bước 2: Bắt đầu theo dõi các bản sửa đổi

Tiếp theo, chúng ta cần bắt đầu theo dõi các sửa đổi. Điều này rất quan trọng vì nó cho phép chúng ta xem những thay đổi được thực hiện đối với tài liệu.

```csharp
// Bắt đầu theo dõi các sửa đổi
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Bước 3: Di chuyển nút

Bây giờ đến phần cốt lõi của nhiệm vụ của chúng ta: di chuyển một nút từ vị trí này sang vị trí khác. Chúng ta sẽ di chuyển đoạn thứ ba và đặt nó trước đoạn đầu tiên.

```csharp
// Xác định nút cần di chuyển và phạm vi kết thúc của nó
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// Di chuyển các nút trong phạm vi xác định
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## Bước 4: Dừng theo dõi các bản sửa đổi

Khi chúng tôi đã di chuyển các nút, chúng tôi cần ngừng theo dõi các bản sửa đổi.

```csharp
// Dừng theo dõi các bản sửa đổi
doc.StopTrackRevisions();
```

## Bước 5: Lưu tài liệu

Cuối cùng, hãy lưu tài liệu đã sửa đổi của chúng ta vào thư mục đã chỉ định.

```csharp
// Lưu tài liệu đã sửa đổi
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// Xuất số đoạn văn cuối cùng
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Phần kết luận

Và bạn có nó! Bạn đã di chuyển thành công một nút trong tài liệu được theo dõi bằng Aspose.Words for .NET. Thư viện mạnh mẽ này giúp bạn dễ dàng thao tác các tài liệu Word theo chương trình. Cho dù bạn đang tạo, chỉnh sửa hay theo dõi các thay đổi, Aspose.Words đều có thể hỗ trợ bạn. Vì vậy, hãy tiếp tục và thử xem. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?

Aspose.Words for .NET là một thư viện lớp để làm việc với các tài liệu Word theo chương trình. Nó cho phép các nhà phát triển tạo, chỉnh sửa, chuyển đổi và in tài liệu Word trong các ứng dụng .NET.

### Làm cách nào để theo dõi các bản sửa đổi trong tài liệu Word bằng Aspose.Words?

 Để theo dõi các sửa đổi, hãy sử dụng`StartTrackRevisions` phương pháp trên`Document` sự vật. Điều này sẽ cho phép theo dõi sửa đổi, hiển thị mọi thay đổi được thực hiện đối với tài liệu.

### Tôi có thể di chuyển nhiều nút trong Aspose.Words không?

Có, bạn có thể di chuyển nhiều nút bằng cách lặp lại chúng và sử dụng các phương thức như`InsertBefore` hoặc`InsertAfter` để đặt chúng vào vị trí mong muốn.

### Làm cách nào để ngừng theo dõi các bản sửa đổi trong Aspose.Words?

 Sử dụng`StopTrackRevisions` phương pháp trên`Document` phản đối việc ngừng theo dõi các phiên bản.

### Tôi có thể tìm thêm tài liệu về Aspose.Words cho .NET ở đâu?

 Bạn có thể tìm tài liệu chi tiết[đây](https://reference.aspose.com/words/net/).
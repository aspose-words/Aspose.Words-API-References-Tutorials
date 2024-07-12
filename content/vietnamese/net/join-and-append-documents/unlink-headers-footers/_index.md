---
title: Bỏ liên kết đầu trang chân trang
linktitle: Bỏ liên kết đầu trang chân trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hủy liên kết đầu trang và chân trang trong tài liệu Word bằng Aspose.Words cho .NET. Hãy làm theo hướng dẫn chi tiết từng bước của chúng tôi để nắm vững thao tác tài liệu.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/unlink-headers-footers/
---
## Giới thiệu

Trong thế giới xử lý tài liệu, việc giữ cho đầu trang và chân trang nhất quán đôi khi có thể là một thách thức. Cho dù bạn đang hợp nhất các tài liệu hay chỉ muốn có các đầu trang và chân trang khác nhau cho các phần khác nhau thì việc biết cách hủy liên kết chúng là điều cần thiết. Hôm nay, chúng ta sẽ đi sâu vào cách bạn có thể đạt được điều này bằng cách sử dụng Aspose.Words for .NET. Chúng tôi sẽ chia nhỏ từng bước để bạn có thể dễ dàng theo dõi. Sẵn sàng để làm chủ thao tác tài liệu? Bắt đầu nào!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào chi tiết, có một số điều bạn cần:

-  Aspose.Words for .NET Library: Bạn có thể tải xuống từ[Trang phát hành Aspose](https://releases.aspose.com/words/net/).
- .NET Framework: Đảm bảo bạn đã cài đặt .NET framework tương thích.
- IDE: Visual Studio hoặc bất kỳ Môi trường phát triển tích hợp tương thích .NET nào khác.
- Hiểu biết cơ bản về C#: Bạn sẽ cần hiểu biết cơ bản về ngôn ngữ lập trình C#.

## Nhập không gian tên

Để bắt đầu, hãy đảm bảo nhập các không gian tên cần thiết vào dự án của bạn. Điều này sẽ cho phép bạn truy cập thư viện Aspose.Words và các tính năng của nó.

```csharp
using Aspose.Words;
```

Hãy chia nhỏ quy trình thành các bước có thể quản lý để giúp bạn hủy liên kết đầu trang và chân trang trong tài liệu Word của mình.

## Bước 1: Thiết lập dự án của bạn

Trước tiên, bạn sẽ cần thiết lập môi trường dự án của mình. Mở IDE của bạn và tạo một dự án .NET mới. Thêm tham chiếu vào thư viện Aspose.Words mà bạn đã tải xuống trước đó.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu nguồn

Tiếp theo, bạn cần tải tài liệu nguồn mà bạn muốn sửa đổi. Tài liệu này sẽ không được liên kết với đầu trang và chân trang.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Bước 3: Tải tài liệu đích

Bây giờ, hãy tải tài liệu đích nơi bạn sẽ nối thêm tài liệu nguồn sau khi hủy liên kết đầu trang và chân trang của nó.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 4: Hủy liên kết đầu trang và chân trang

 Bước này rất quan trọng. Để hủy liên kết đầu trang và chân trang của tài liệu nguồn khỏi tài liệu đích, bạn sẽ sử dụng`LinkToPrevious` phương pháp. Phương pháp này đảm bảo rằng đầu trang và chân trang không chuyển sang tài liệu được nối thêm.

```csharp
// Hủy liên kết đầu trang và chân trang trong tài liệu nguồn để dừng việc này
//tiếp tục đầu trang và chân trang của tài liệu đích.
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Bước 5: Nối tài liệu nguồn

 Sau khi hủy liên kết đầu trang và chân trang, bạn có thể nối tài liệu nguồn vào tài liệu đích. Sử dụng`AppendDocument` phương thức và đặt chế độ định dạng nhập thành`KeepSourceFormatting` để duy trì định dạng ban đầu của tài liệu nguồn.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 6: Lưu tài liệu cuối cùng

Cuối cùng, lưu tài liệu vừa tạo. Tài liệu này sẽ có nội dung của tài liệu nguồn được nối vào tài liệu đích, với đầu trang và chân trang không được liên kết.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

## Phần kết luận

Và bạn có nó rồi đấy! Bằng cách làm theo các bước này, bạn đã hủy liên kết thành công đầu trang và chân trang trong tài liệu nguồn của mình và nối nó vào tài liệu đích bằng Aspose.Words for .NET. Kỹ thuật này có thể đặc biệt hữu ích khi bạn làm việc với các tài liệu phức tạp yêu cầu các đầu trang và chân trang khác nhau cho các phần khác nhau. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?  
Aspose.Words for .NET là một thư viện mạnh mẽ để làm việc với các tài liệu Word trong các ứng dụng .NET. Nó cho phép các nhà phát triển tạo, sửa đổi, chuyển đổi và in tài liệu theo chương trình.

### Tôi có thể hủy liên kết đầu trang và chân trang chỉ cho các phần cụ thể không?  
 Có, bạn có thể hủy liên kết đầu trang và chân trang cho các phần cụ thể bằng cách truy cập`HeadersFooters` thuộc tính của phần mong muốn và sử dụng`LinkToPrevious` phương pháp.

### Có thể giữ nguyên định dạng gốc của tài liệu nguồn không?  
 Có, khi nối thêm tài liệu nguồn, hãy sử dụng`ImportFormatMode.KeepSourceFormatting` tùy chọn để giữ lại định dạng ban đầu.

### Tôi có thể sử dụng Aspose.Words cho .NET với các ngôn ngữ .NET khác ngoài C# không?  
Tuyệt đối! Aspose.Words for .NET có thể được sử dụng với bất kỳ ngôn ngữ .NET nào, bao gồm VB.NET và F#.

### Tôi có thể tìm thêm tài liệu và hỗ trợ cho Aspose.Words cho .NET ở đâu?  
 Bạn có thể tìm thấy tài liệu đầy đủ về[Trang tài liệu Aspose.Words cho .NET](https://reference.aspose.com/words/net/) , và hỗ trợ có sẵn trên[diễn đàn giả định](https://forum.aspose.com/c/words/8).

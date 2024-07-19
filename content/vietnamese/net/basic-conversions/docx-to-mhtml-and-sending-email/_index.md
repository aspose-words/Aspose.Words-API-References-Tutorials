---
title: Chuyển đổi Docx sang Mhtml và gửi email
linktitle: Chuyển đổi Docx sang Mhtml và gửi email
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi DOCX sang MHTML và gửi email bằng Aspose.Words cho .NET trong hướng dẫn từng bước này. Tăng năng suất của bạn với tự động hóa dễ dàng.
type: docs
weight: 10
url: /vi/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Giới thiệu

Trong thời đại kỹ thuật số ngày nay, việc chuyển đổi tài liệu từ định dạng này sang định dạng khác và gửi qua email là một công việc phổ biến. Bài viết này sẽ hướng dẫn bạn quy trình chuyển đổi tệp DOCX sang định dạng MHTML, sau đó gửi tệp đó dưới dạng email bằng Aspose.Words cho .NET. Chúng tôi sẽ chia nhỏ từng bước thành hướng dẫn chi tiết, dễ làm theo, đảm bảo bạn hiểu rõ quy trình từ đầu đến cuối. Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Aspose.Words for .NET: Tải xuống và cài đặt thư viện Aspose.Words for .NET từ[Trang phát hành Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email for .NET: Tải xuống và cài đặt thư viện Aspose.Email for .NET từ[Trang phát hành Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework trên máy của mình.
4. Máy chủ SMTP: Bạn cần truy cập vào máy chủ SMTP để gửi email.

## Nhập không gian tên

Để sử dụng Aspose.Words và Aspose.Email trong dự án của bạn, bạn cần nhập các không gian tên cần thiết. Thêm các lệnh sử dụng sau vào đầu tệp C# của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Hãy chia nhỏ quy trình thành nhiều bước để đảm bảo bạn hiểu rõ từng phần.

## Bước 1: Tải tài liệu DOCX

 Trước tiên, bạn cần tải tài liệu DOCX mà bạn muốn chuyển đổi. Sử dụng`Document` class từ Aspose.Words để tải tệp DOCX của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Bước 2: Lưu tài liệu dưới dạng MHTML

 Tiếp theo, lưu tài liệu đã tải dưới dạng tệp MHTML. Việc này được thực hiện bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Tua lại luồng về đầu để Aspose.Email có thể đọc được.
stream.Position = 0;
```

## Bước 3: Tạo tin nhắn email

Bây giờ, hãy tạo một email từ luồng MHTML bằng Aspose.Email. Bạn sẽ sử dụng`MailMessage` lớp cho mục đích này.

```csharp
// Tạo một thông báo email Aspose.Email MIME từ luồng.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Bước 4: Gửi Email

 Cuối cùng, gửi email bằng ứng dụng khách SMTP. Định cấu hình máy khách SMTP với chi tiết máy chủ SMTP của bạn và sử dụng`Send` phương pháp gửi tin nhắn.

```csharp
// Gửi tin nhắn bằng Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Phần kết luận

Chúc mừng! Bạn đã chuyển đổi thành công tài liệu DOCX sang MHTML và gửi tài liệu đó qua email bằng Aspose.Words for .NET. Quá trình này bao gồm việc tải tài liệu, chuyển đổi nó sang MHTML, tạo thư email và gửi nó bằng ứng dụng khách SMTP. Với các bước này, bạn có thể dễ dàng tự động hóa việc chuyển đổi và gửi tài liệu qua email trong ứng dụng của mình.

## Câu hỏi thường gặp

### Tôi có thể sử dụng phương pháp này để chuyển đổi các định dạng tài liệu khác không?
Có, Aspose.Words hỗ trợ nhiều định dạng khác nhau và bạn có thể chuyển đổi các tài liệu như DOC, DOCX, RTF, v.v. sang MHTML.

### Làm cách nào để thêm tệp đính kèm vào email?
 Bạn có thể dùng`Attachments` tài sản của`MailMessage`class để thêm tệp đính kèm vào email của bạn.

### Aspose.Words có tương thích với .NET Core không?
Có, Aspose.Words tương thích với .NET Core. Bạn cũng có thể sử dụng nó trong các ứng dụng .NET Core.

### Tôi có cần giấy phép cho Aspose.Words và Aspose.Email không?
 Có, cả hai thư viện đều yêu cầu giấy phép. Bạn có thể nhận được giấy phép tạm thời từ[Trang mua hàng](https://purchase.aspose.com/temporary-license/) cho mục đích đánh giá.

### Tôi có thể tìm thêm tài liệu ở đâu?
 Bạn có thể tìm tài liệu chi tiết về Aspose.Words[đây](https://reference.aspose.com/words/net/) và cho Aspose.Email[đây](https://reference.aspose.com/email/net/).

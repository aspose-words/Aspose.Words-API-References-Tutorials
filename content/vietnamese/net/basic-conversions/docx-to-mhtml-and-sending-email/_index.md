---
title: Chuyển đổi Docx sang Mhtml và gửi email
linktitle: Chuyển đổi Docx sang Mhtml và gửi email
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi tài liệu Word từ Docx sang MHTML và gửi chúng dưới dạng email bằng Aspose.Words và Aspose.Email. Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng Aspose.Words cho .NET để chuyển đổi tài liệu Word ở định dạng Docx sang MHTML và gửi dưới dạng email bằng Aspose.Email. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo rằng bạn đã cài đặt và thiết lập cả thư viện Aspose.Words for .NET và Aspose.Email trong môi trường phát triển của mình. Nếu bạn chưa làm như vậy, hãy tải xuống và cài đặt các thư viện từ[Aspose.Rereleases](https://releases.aspose.com/words/net/).

## Bước 1: Khởi tạo đối tượng tài liệu

 Đầu tiên, khởi tạo`Document`đối tượng bằng đường dẫn đến tài liệu nguồn của bạn ở định dạng Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Bước 2: Lưu tài liệu ở định dạng MHTML

 Tiếp theo, lưu tài liệu vào`Stream` đối tượng ở định dạng MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Bước 3: Tua lại luồng

Vì Aspose.Email cần đọc luồng từ đầu, hãy tua lại luồng về đầu:

```csharp
stream.Position = 0;
```

## Bước 4: Tạo tin nhắn Aspose.Email MIME

 Tạo một`MailMessage` đối tượng từ luồng bằng cách sử dụng`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Vui lòng tùy chỉnh các thuộc tính của tin nhắn như người gửi, người nhận và chủ đề.

## Bước 5: Gửi Email

 Sử dụng Aspose.Email`SmtpClient` để gửi email:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Đảm bảo rằng bạn cung cấp địa chỉ máy chủ máy chủ SMTP chính xác.

Đó là nó! Bạn đã chuyển đổi thành công tài liệu Word ở định dạng Docx sang MHTML và gửi nó dưới dạng email bằng Aspose.Words cho .NET và Aspose.Email.

### Mã nguồn ví dụ cho Docx To Mhtml và gửi Email bằng Aspose.Words cho .NET

```csharp

	// Tài liệu doc = Tài liệu mới (MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Tua lại luồng về đầu để Aspose.Email có thể đọc được.
	stream.Position = 0;

	// Tạo một thông báo email Aspose.Email MIME từ luồng.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Gửi tin nhắn bằng Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó theo yêu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Làm cách nào để chuyển đổi tệp DOCX sang MHTML?

Để chuyển đổi tệp DOCX sang MHTML, bạn có thể sử dụng các công cụ phần mềm hoặc thư viện cung cấp chức năng này. Aspose.Words for .NET là một lựa chọn đáng tin cậy cho việc chuyển đổi này. Bạn có thể sử dụng API thư viện để tải tệp DOCX và lưu nó ở định dạng MHTML.

#### Làm cách nào để gửi email có tệp đính kèm MHTML?

Để gửi email có tệp MHTML dưới dạng tệp đính kèm, bạn có thể sử dụng các thư viện hoặc công cụ dành riêng cho việc gửi email, chẳng hạn như System.Net.Mail trong .NET. Bạn phải tạo một email, chỉ định người nhận, chủ đề và nội dung, sau đó thêm tệp MHTML dưới dạng tệp đính kèm vào thư trước khi gửi.

#### Những hạn chế của quá trình chuyển đổi và gửi email là gì?

Những hạn chế của quá trình chuyển đổi và gửi email phụ thuộc vào các công cụ cụ thể mà bạn đang sử dụng. Một số công cụ có thể có các hạn chế liên quan đến kích thước tệp, cài đặt bảo mật hoặc giao thức email được hỗ trợ. Điều quan trọng là chọn công cụ phù hợp với nhu cầu của bạn và cân nhắc những hạn chế này khi triển khai.

#### Aspose có phải là công cụ đáng tin cậy để chuyển đổi DOCX sang MHTML và gửi email không?

Có, Aspose.Words for .NET là một công cụ đáng tin cậy để chuyển đổi DOCX sang MHTML và gửi email. Nó được sử dụng rộng rãi bởi các nhà phát triển và chuyên gia vì hiệu suất và chất lượng của nó. Công cụ này cung cấp tài liệu toàn diện, các tính năng nâng cao và hỗ trợ kỹ thuật chuyên dụng, khiến công cụ này trở thành lựa chọn được đề xuất cho những tác vụ này.
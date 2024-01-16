---
title: Ký tài liệu Word được mã hóa
linktitle: Ký tài liệu Word được mã hóa
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách ký điện tử vào tài liệu từ được mã hóa bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/signing-encrypted-document/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước sử dụng tính năng ký tài liệu từ được mã hóa bằng Aspose.Words cho .NET. Tính năng này cho phép bạn ký điện tử vào tài liệu Word được mã hóa bằng mật khẩu giải mã. Làm theo các bước dưới đây:

## Bước 1: Đặt tùy chọn chữ ký

Tạo một thể hiện của lớp SignOptions và đặt mật khẩu giải mã:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Đảm bảo chỉ định mật khẩu giải mã chính xác cho tài liệu được mã hóa của bạn.

## Bước 2: Tải chứng chỉ

Bắt đầu bằng cách tải chứng chỉ ký bằng lớp Chứng chỉHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Hãy đảm bảo chỉ định đường dẫn chính xác tới chứng chỉ và mật khẩu liên quan của bạn.

## Bước 3: Ký tài liệu được mã hóa

Sử dụng lớp DigitalSignatureUtil để ký tài liệu được mã hóa:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Đảm bảo chỉ định đường dẫn chính xác cho tài liệu được mã hóa, tài liệu đã ký và chứng chỉ.

### Mã nguồn ví dụ để ký tài liệu được mã hóa bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để ký một tài liệu được mã hóa bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Bằng cách làm theo các bước này, bạn có thể dễ dàng ký tài liệu Word được mã hóa bằng Aspose.Words cho .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá quy trình ký một tài liệu Word được mã hóa bằng Aspose.Words cho .NET. Bằng cách cung cấp mật khẩu giải mã và chứng chỉ ký, chúng ta có thể thêm chữ ký số vào tài liệu được mã hóa. Việc ký các tài liệu được mã hóa đảm bảo tính xác thực và tính toàn vẹn của chúng, cung cấp thêm một lớp bảo mật. Aspose.Words for .NET cho phép bạn ký các tài liệu được mã hóa và duy trì tính bảo mật cũng như độ tin cậy của các tệp Word của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Việc ký tài liệu trong Aspose.Words dành cho .NET là gì?

Trả lời: Ký tài liệu trong Aspose.Words cho .NET đề cập đến quá trình ký điện tử một tài liệu Word để đảm bảo tính xác thực, tính toàn vẹn và không thể chối bỏ của tài liệu đó. Nó liên quan đến việc thêm chữ ký số vào tài liệu bằng chứng chỉ.

#### Hỏi: Tài liệu Word được mã hóa là gì?

Trả lời: Tài liệu Word được mã hóa là tài liệu đã được mã hóa bằng mật khẩu. Mã hóa là một biện pháp bảo mật nhằm bảo vệ nội dung của tài liệu bằng cách xáo trộn nó và làm cho nó không thể đọc được nếu không có mật khẩu giải mã chính xác.

#### Hỏi: Làm cách nào tôi có thể ký tài liệu Word được mã hóa bằng Aspose.Words cho .NET?

Trả lời: Để ký tài liệu Word được mã hóa bằng Aspose.Words cho .NET, bạn cần cung cấp mật khẩu giải mã cùng với chứng chỉ ký. Thực hiện theo các bước sau:
1.  Đặt mật khẩu giải mã trong`SignOptions` sự vật.
2.  Tải chứng chỉ ký bằng cách sử dụng`CertificateHolder` lớp học.
3.  Sử dụng`DigitalSignatureUtil.Sign` phương pháp ký vào tài liệu được mã hóa, cung cấp các tham số cần thiết.

#### Hỏi: Mục đích của việc ký một tài liệu được mã hóa là gì?

Trả lời: Ký một tài liệu được mã hóa bằng Aspose.Words for .NET cho phép bạn thêm chữ ký điện tử vào tài liệu ngay cả khi nó được mã hóa. Điều này cung cấp một lớp bảo mật bổ sung và đảm bảo tính xác thực và tính toàn vẹn của nội dung được mã hóa. Nó cho phép người nhận xác minh nguồn gốc của tài liệu và phát hiện mọi hành vi giả mạo.

#### Hỏi: Tôi có thể ký một tài liệu được mã hóa mà không cần cung cấp mật khẩu giải mã không?

Trả lời: Không, để ký một tài liệu được mã hóa, bạn phải cung cấp đúng mật khẩu giải mã. Cần có mật khẩu giải mã để truy cập và sửa đổi nội dung được mã hóa của tài liệu trước khi áp dụng chữ ký số.

#### Hỏi: Tôi có thể ký tài liệu Word được mã hóa bằng bất kỳ chứng chỉ nào không?

Trả lời: Để ký tài liệu Word được mã hóa bằng Aspose.Words cho .NET, bạn cần có chứng chỉ X.509 hợp lệ. Chứng chỉ có thể được lấy từ cơ quan cấp chứng chỉ đáng tin cậy (CA) hoặc chứng chỉ tự ký có thể được sử dụng cho mục đích thử nghiệm.

#### Hỏi: Tôi có thể ký nhiều tài liệu Word được mã hóa bằng cùng một chứng chỉ không?

 Đáp: Có, bạn có thể ký nhiều tài liệu Word được mã hóa bằng cùng một chứng chỉ. Khi bạn đã tải chứng chỉ bằng cách sử dụng`CertificateHolder` class, bạn có thể sử dụng lại nó để ký nhiều tài liệu được mã hóa.

#### Câu hỏi: Tôi có thể xác minh chữ ký số của tài liệu được mã hóa đã ký không?

 Trả lời: Có, Aspose.Words for .NET cung cấp chức năng xác minh chữ ký số của tài liệu được mã hóa đã ký. Bạn có thể dùng`DigitalSignatureUtil.Verify` phương pháp kiểm tra tính hợp lệ và xác thực của chữ ký số.

#### Câu hỏi: Aspose.Words for .NET hỗ trợ định dạng tệp nào để ký các tài liệu được mã hóa?

 Trả lời: Aspose.Words for .NET hỗ trợ ký các tài liệu Word được mã hóa ở định dạng tệp DOCX. Bạn có thể ký các tệp DOCX được mã hóa bằng cách sử dụng`DigitalSignatureUtil.Sign` phương pháp cùng với mật khẩu và chứng chỉ giải mã cần thiết.

#### Câu hỏi: Việc ký một tài liệu được mã hóa ảnh hưởng đến việc mã hóa như thế nào?

Trả lời: Việc ký một tài liệu được mã hóa bằng Aspose.Words cho .NET không ảnh hưởng đến việc mã hóa tài liệu. Mã hóa vẫn còn nguyên và chữ ký số được thêm vào nội dung được mã hóa. Chữ ký số cung cấp tính bảo mật và xác minh bổ sung mà không ảnh hưởng đến mã hóa được áp dụng cho tài liệu.
---
title: Ký tài liệu Word
linktitle: Ký tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách ký điện tử vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/sign-document/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng ký tài liệu với Aspose.Words dành cho .NET. Tính năng này cho phép bạn ký điện tử vào tài liệu Word bằng chứng chỉ. Làm theo các bước dưới đây:

## Bước 1: Tải chứng chỉ

Bắt đầu bằng cách tải chứng chỉ ký bằng lớp Chứng chỉHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Hãy đảm bảo chỉ định đường dẫn chính xác tới chứng chỉ và mật khẩu liên quan của bạn.

## Bước 2: Ký văn bản

Sử dụng lớp DigitalSignatureUtil để ký tài liệu:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Đảm bảo chỉ định đường dẫn chính xác cho tài liệu nguồn và tài liệu đã ký.

### Mã nguồn mẫu cho Tài liệu ký bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để ký một tài liệu bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng ký vào tài liệu Word bằng Aspose.Words cho .NET.

## Phần kết luận

 Trong hướng dẫn này, chúng ta đã khám phá tính năng ký tài liệu trong Aspose.Words dành cho .NET. Bằng cách tải chứng chỉ ký và sử dụng`DigitalSignatureUtil.Sign` phương pháp này, chúng ta có thể ký điện tử vào một tài liệu Word. Việc ký tài liệu cung cấp khả năng xác thực và đảm bảo tính toàn vẹn của nội dung tài liệu, khiến nó trở thành một tính năng có giá trị để quản lý tài liệu an toàn và đáng tin cậy.

### Câu hỏi thường gặp về tài liệu ký hiệu

#### Câu hỏi: Việc ký tài liệu trong Aspose.Words dành cho .NET là gì?

Trả lời: Ký tài liệu trong Aspose.Words cho .NET đề cập đến quá trình ký điện tử vào tài liệu Word bằng chứng chỉ. Tính năng này thêm chữ ký số vào tài liệu, cung cấp tính xác thực, tính toàn vẹn và không thể chối bỏ nội dung của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể tải chứng chỉ ký trong Aspose.Words cho .NET?

 Trả lời: Để tải chứng chỉ ký trong Aspose.Words cho .NET, bạn có thể sử dụng`CertificateHolder` lớp học. Tạo một thể hiện của`CertificateHolder` bằng cách cung cấp đường dẫn đến tệp chứng chỉ và mật khẩu liên quan. Đây là một ví dụ:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Đảm bảo cung cấp đường dẫn chính xác đến chứng chỉ của bạn và mật khẩu liên quan.

#### Hỏi: Làm cách nào để tôi ký tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để ký tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng`DigitalSignatureUtil` lớp học. Gọi`Sign` phương thức, cung cấp đường dẫn đến tài liệu nguồn, đường dẫn đến tài liệu đã ký (đầu ra) và`CertificateHolder` sự vật. Đây là một ví dụ:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Đảm bảo rằng bạn cung cấp đường dẫn chính xác cho tài liệu nguồn và tài liệu đã ký (đầu ra).

#### Hỏi: Mục đích của việc ký văn bản là gì?

Trả lời: Việc ký tài liệu đóng vai trò như một phương pháp đảm bảo tính xác thực và tính toàn vẹn của tài liệu. Bằng cách ký điện tử một tài liệu, bạn có thể cung cấp bằng chứng về nguồn gốc của nó, xác minh nội dung của nó không bị thay đổi và thiết lập tính chống chối bỏ. Ký tài liệu thường được sử dụng cho các tài liệu pháp lý, tài chính và nhạy cảm.

#### Câu hỏi: Tôi có thể sử dụng bất kỳ chứng chỉ nào để ký tài liệu trong Aspose.Words cho .NET không?

Trả lời: Để ký tài liệu trong Aspose.Words cho .NET, bạn cần sử dụng chứng chỉ X.509 hợp lệ. Chứng chỉ này có thể được lấy từ cơ quan cấp chứng chỉ đáng tin cậy (CA) hoặc chứng chỉ tự ký có thể được sử dụng cho mục đích thử nghiệm.

#### Câu hỏi: Aspose.Words for .NET hỗ trợ ký tài liệu ở định dạng tệp nào?

 Trả lời: Aspose.Words for .NET hỗ trợ ký tài liệu cho tài liệu Word ở định dạng tệp DOCX. Bạn có thể ký các tệp DOCX bằng cách sử dụng`DigitalSignatureUtil` lớp và chứng chỉ phù hợp.

#### Hỏi: Tôi có thể ký nhiều tài liệu Word bằng cùng một chứng chỉ không?

Đáp: Có, bạn có thể ký nhiều tài liệu Word bằng cùng một chứng chỉ. Khi bạn đã tải chứng chỉ bằng cách sử dụng`CertificateHolder` lớp, bạn có thể sử dụng lại nó để ký nhiều tài liệu bằng cách gọi lớp`DigitalSignatureUtil.Sign` phương thức với các đường dẫn tài liệu nguồn và đã ký khác nhau.

#### Hỏi: Việc ký tài liệu có làm thay đổi tài liệu gốc không?

Trả lời: Việc ký tài liệu bằng Aspose.Words cho .NET không sửa đổi tài liệu gốc. Thay vào đó, nó tạo ra một bản sao tài liệu được ký điện tử, giữ nguyên tài liệu gốc. Bản sao được ký điện tử có chứa chữ ký số được bổ sung, đảm bảo tính toàn vẹn của nội dung tài liệu.

#### Câu hỏi: Tôi có thể xác minh chữ ký điện tử của tài liệu đã ký bằng Aspose.Words cho .NET không?

 Trả lời: Có, Aspose.Words for .NET cung cấp chức năng xác minh chữ ký số của tài liệu đã ký. Bạn có thể dùng`DigitalSignatureUtil.Verify` phương pháp kiểm tra tính hợp lệ và xác thực của chữ ký số.
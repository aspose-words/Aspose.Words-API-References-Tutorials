---
title: Tạo dòng chữ ký mới và đặt Id nhà cung cấp
linktitle: Tạo dòng chữ ký mới và đặt Id nhà cung cấp
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo dòng chữ ký mới và đặt ID nhà cung cấp trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng Tạo dòng chữ ký mới và Đặt ID nhà cung cấp với Aspose.Words cho .NET. Tính năng này cho phép bạn chèn dòng chữ ký vào tài liệu Word, đặt các tùy chọn tùy chỉnh và ký tên vào tài liệu. Làm theo các bước dưới đây:

## Bước 1: Tạo tài liệu và trình tạo

Bắt đầu bằng cách tạo một thể hiện của lớp Document và đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Đặt tùy chọn dòng chữ ký

Tạo một thể hiện của lớp SignatureLineOptions và đặt các tùy chọn mong muốn:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Bước 3: Chèn dòng chữ ký

Sử dụng phương thức InsertSignatureLine() của đối tượng DocumentBuilder để chèn dòng chữ ký vào tài liệu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Bước 4: Đặt ID nhà cung cấp

Đặt ID nhà cung cấp cho dòng chữ ký bằng thuộc tính ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Hãy đảm bảo chỉ định ID nhà cung cấp chính xác cho trường hợp sử dụng của bạn.

## Bước 5: Lưu tài liệu

Lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp để lưu tài liệu.

## Bước 6: Ký văn bản

Để ký tài liệu, bạn cần đặt các tùy chọn chữ ký và sử dụng lớp DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Đảm bảo chỉ định đường dẫn chính xác cho tài liệu, chứng chỉ và tài liệu đã ký.

### Mã nguồn ví dụ để Tạo dòng chữ ký mới và đặt Id nhà cung cấp bằng cách sử dụng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để tạo dòng chữ ký mới và đặt ID nhà cung cấp bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng tạo dòng chữ ký mới và đặt ID nhà cung cấp trong tài liệu Word của mình bằng Aspose.Words cho .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá tính năng tạo dòng chữ ký mới và đặt ID nhà cung cấp trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng chèn dòng chữ ký bằng các tùy chọn tùy chỉnh và liên kết nó với một nhà cung cấp cụ thể bằng ID nhà cung cấp. Việc thêm dòng chữ ký và tùy chỉnh thông tin nhà cung cấp sẽ nâng cao tính xác thực và độ tin cậy cho tài liệu của bạn. Aspose.Words for .NET cung cấp API mạnh mẽ để Xử lý văn bản với các dòng chữ ký và chứng chỉ kỹ thuật số trong tài liệu Word, cho phép bạn tự động hóa quy trình ký và đảm bảo tính hợp lệ của tài liệu của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: ID nhà cung cấp trong dòng chữ ký là gì?

Trả lời: ID nhà cung cấp trong dòng chữ ký là mã định danh duy nhất đại diện cho nhà cung cấp chữ ký số. Nó giúp xác định nguồn hoặc tổ chức chịu trách nhiệm về chữ ký.

#### Câu hỏi: Làm cách nào tôi có thể tạo dòng chữ ký mới trong tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Để tạo dòng chữ ký mới trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tạo một thể hiện của`Document` lớp học và một`DocumentBuilder` sự vật.
2.  Tạo một thể hiện của`SignatureLineOptions` class và đặt các tùy chọn dòng chữ ký mong muốn.
3.  Sử dụng`InsertSignatureLine` phương pháp của`DocumentBuilder` đối tượng chèn dòng chữ ký vào tài liệu.

#### Hỏi: Tôi có thể tùy chỉnh các tùy chọn của dòng chữ ký như tên người ký, chức danh và hướng dẫn không?

 A: Có, bạn có thể tùy chỉnh các tùy chọn của dòng chữ ký. Các`SignatureLineOptions` lớp cung cấp các thuộc tính để thiết lập các tùy chọn mong muốn, chẳng hạn như`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, v.v. Bạn có thể sửa đổi các thuộc tính này trước khi chèn dòng chữ ký.

#### Câu hỏi: Mục đích của việc đặt ID nhà cung cấp cho dòng chữ ký là gì?

Trả lời: Việc đặt ID nhà cung cấp cho dòng chữ ký giúp xác định nguồn hoặc tổ chức chịu trách nhiệm về chữ ký số. Nó cho phép bạn liên kết chữ ký với một nhà cung cấp hoặc tổ chức cụ thể, cung cấp thông tin bổ sung về nguồn gốc và độ tin cậy của chữ ký.

#### Câu hỏi: Làm cách nào tôi có thể đặt ID nhà cung cấp cho dòng chữ ký bằng Aspose.Words cho .NET?

Trả lời: Để đặt ID nhà cung cấp cho dòng chữ ký bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Sau khi chèn dòng chữ ký, truy cập vào`ProviderId` tài sản của`SignatureLine` sự vật.
2.  Đặt`ProviderId` thuộc tính thành giá trị ID nhà cung cấp mong muốn bằng cách sử dụng`Guid` loại dữ liệu.

#### Hỏi: Tôi có thể ký tài liệu sau khi tạo dòng chữ ký mới và đặt ID nhà cung cấp không?

 Trả lời: Có, sau khi tạo dòng chữ ký mới và đặt ID nhà cung cấp, bạn có thể ký vào tài liệu. Để ký vào tài liệu, bạn cần thiết lập các tùy chọn chữ ký, bao gồm ID dòng chữ ký, ID nhà cung cấp, nhận xét và thời gian ký. Sau đó, sử dụng`DigitalSignatureUtil.Sign` phương pháp ký tài liệu bằng chứng chỉ kỹ thuật số.

#### Câu hỏi: Tôi có thể chỉ định ID nhà cung cấp cụ thể cho từng dòng chữ ký trong tài liệu Word không?

Trả lời: Có, bạn có thể chỉ định ID nhà cung cấp cụ thể cho từng dòng chữ ký trong tài liệu Word. Sau khi chèn từng dòng chữ ký, bạn có thể đặt ID nhà cung cấp cho dòng chữ ký cụ thể đó bằng cách truy cập vào`ProviderId` tài sản tương ứng`SignatureLine` sự vật.

#### Câu hỏi: Làm cách nào tôi có thể lưu tài liệu đã sửa đổi sau khi tạo dòng chữ ký mới và đặt ID nhà cung cấp?

 Trả lời: Để lưu tài liệu đã sửa đổi sau khi tạo dòng chữ ký mới và đặt ID nhà cung cấp, bạn có thể sử dụng`Save` phương pháp của`Document` sự vật. Chỉ định đường dẫn và tên tệp chính xác để lưu tài liệu.

#### Câu hỏi: Aspose.Words for .NET hỗ trợ định dạng tệp nào để tạo và ký các dòng chữ ký?

Trả lời: Aspose.Words for .NET hỗ trợ tạo và ký các dòng chữ ký ở định dạng tệp DOCX. Bạn có thể tạo và ký các dòng chữ ký trong tệp DOCX bằng các phương thức và lớp được cung cấp.

#### Câu hỏi: Tôi có thể sửa đổi ID nhà cung cấp hoặc các tùy chọn khác của dòng chữ ký sau khi đã được ký không?

Trả lời: Khi dòng chữ ký đã được ký, nó sẽ trở thành một phần nội dung của tài liệu và không thể sửa đổi riêng lẻ. Mọi sửa đổi đối với dòng chữ ký, chẳng hạn như thay đổi ID nhà cung cấp hoặc các tùy chọn khác, sẽ yêu cầu xóa chữ ký hiện có và tạo dòng chữ ký mới.
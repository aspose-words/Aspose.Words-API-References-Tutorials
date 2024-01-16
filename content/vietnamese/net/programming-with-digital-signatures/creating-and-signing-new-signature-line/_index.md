---
title: Tạo và ký dòng chữ ký mới
linktitle: Tạo và ký dòng chữ ký mới
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo và ký dòng chữ ký mới trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng tạo và ký dòng chữ ký mới với Aspose.Words cho .NET. Tính năng này cho phép bạn chèn dòng chữ ký vào tài liệu Word, đặt các tùy chọn tùy chỉnh và ký tên vào tài liệu. Làm theo các bước dưới đây:

## Bước 1: Tạo tài liệu và trình tạo

Bắt đầu bằng cách tạo một thể hiện của lớp Document và đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn dòng chữ ký

Sử dụng phương thức InsertSignatureLine() của đối tượng DocumentBuilder để chèn một dòng chữ ký mới vào tài liệu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Bước 3: Lưu tài liệu

Lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp để lưu tài liệu.

## Bước 4: Ký văn bản

Để ký tài liệu, bạn cần đặt các tùy chọn chữ ký và sử dụng lớp DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Đảm bảo chỉ định đường dẫn chính xác cho tài liệu, hình ảnh dòng chữ ký và tài liệu đã ký.

### Mã nguồn mẫu để tạo và ký dòng chữ ký mới bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để tạo và ký một dòng chữ ký mới với Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Bằng cách làm theo các bước này, bạn sẽ có thể dễ dàng tạo và ký dòng chữ ký mới trong tài liệu Word của mình bằng Aspose.Words for .NET.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách tạo và ký một dòng chữ ký mới trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng chèn dòng chữ ký vào tài liệu của mình, tùy chỉnh các tùy chọn của nó và ký vào tài liệu bằng chứng chỉ kỹ thuật số. Việc thêm dòng chữ ký và chữ ký điện tử vào tài liệu của bạn sẽ nâng cao tính xác thực và tính toàn vẹn của chúng, giúp chúng an toàn và đáng tin cậy hơn. Aspose.Words for .NET cung cấp API mạnh mẽ để Xử lý văn bản với chữ ký và chứng chỉ kỹ thuật số trong tài liệu Word, cho phép bạn tự động hóa quy trình ký và đảm bảo tính hợp lệ của tài liệu của bạn.

### Câu hỏi thường gặp

#### Hỏi: Dòng chữ ký trong tài liệu Word là gì?

Trả lời: Dòng chữ ký trong tài liệu Word là phần giữ chỗ cho biết vị trí cần đặt chữ ký. Nó thường bao gồm tên, chức danh, ngày tháng và cung cấp không gian cho chữ ký viết tay hoặc chữ ký số.

#### Câu hỏi: Làm cách nào tôi có thể tạo dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Để tạo dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tạo một thể hiện của`Document` lớp học và một`DocumentBuilder` sự vật.
2.  Sử dụng`InsertSignatureLine` phương pháp của`DocumentBuilder` đối tượng để chèn một dòng chữ ký mới vào tài liệu.
3. Lưu tài liệu đã sửa đổi.

#### Câu hỏi: Tôi có thể tùy chỉnh các tùy chọn dòng chữ ký, chẳng hạn như tên, chức danh và ngày tháng không?

 Trả lời: Có, bạn có thể tùy chỉnh các tùy chọn dòng chữ ký. Các`SignatureLineOptions` lớp cung cấp các thuộc tính để thiết lập các tùy chọn mong muốn, chẳng hạn như`Signer`, `SignerTitle`, `ShowDate`, v.v. Bạn có thể sửa đổi các thuộc tính này trước khi chèn dòng chữ ký.

#### Hỏi: Làm cách nào để ký vào tài liệu sau khi tạo dòng chữ ký?

 Trả lời: Để ký tài liệu sau khi tạo dòng chữ ký, bạn cần đặt các tùy chọn chữ ký và sử dụng`DigitalSignatureUtil` lớp học. Dưới đây là các bước:
1.  Đặt`SignatureLineId` tài sản ở`SignOptions` phản đối ID của dòng chữ ký.
2.  Đặt`SignatureLineImage` tài sản ở`SignOptions` phản đối hình ảnh chữ ký bạn muốn sử dụng.
3.  Tải chứng chỉ ký bằng cách sử dụng`CertificateHolder` lớp học.
4.  Sử dụng`DigitalSignatureUtil.Sign` phương pháp ký văn bản, cung cấp các thông số cần thiết.

#### Hỏi: Tôi có thể sử dụng hình ảnh chữ ký số để ký vào tài liệu không?

 Đáp: Có, bạn có thể sử dụng hình ảnh chữ ký số để ký vào tài liệu. Để làm điều này, bạn cần cung cấp tệp hình ảnh trong`SignOptions` đối tượng sử dụng`SignatureLineImage`tài sản. Hình ảnh có thể ở bất kỳ định dạng hình ảnh được hỗ trợ nào, chẳng hạn như JPEG, PNG hoặc EMF.

#### Hỏi: Mục đích của việc tạo và ký dòng chữ ký mới trong văn bản Word là gì?

Trả lời: Tạo và ký một dòng chữ ký mới trong tài liệu Word bằng Aspose.Words for .NET cho phép bạn thêm phần giữ chỗ cho chữ ký và sau đó ký vào tài liệu bằng chứng chỉ kỹ thuật số. Quá trình này đảm bảo tính xác thực và toàn vẹn của tài liệu, cung cấp bằng chứng về sự chấp thuận hoặc thỏa thuận.

#### Câu hỏi: Tôi có thể tạo và ký nhiều dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET không?

Trả lời: Có, bạn có thể tạo và ký nhiều dòng chữ ký trong tài liệu Word bằng Aspose.Words for .NET. Mỗi dòng chữ ký có thể có ID và tùy chọn riêng. Bạn có thể lặp lại các bước để tạo và ký thêm dòng chữ ký trong tài liệu.

#### Hỏi: Sau khi ký xong tôi có thể sửa đổi dòng chữ ký hoặc thêm thông tin bổ sung được không?

Trả lời: Khi dòng chữ ký đã được ký, nó sẽ trở thành một phần nội dung của tài liệu và không thể sửa đổi riêng lẻ. Tuy nhiên, bạn có thể thêm thông tin hoặc nội dung bổ sung sau dòng chữ ký đã ký.

#### Hỏi: Tôi có thể xác minh chữ ký số của tài liệu có dòng chữ ký không?

 Trả lời: Có, Aspose.Words for .NET cung cấp chức năng xác minh chữ ký số của tài liệu có chứa dòng chữ ký. Bạn có thể dùng`DigitalSignatureUtil.Verify` phương pháp kiểm tra tính hợp lệ và xác thực của chữ ký số.

#### Câu hỏi: Aspose.Words for .NET hỗ trợ định dạng tệp nào để tạo và ký các dòng chữ ký?

Trả lời: Aspose.Words for .NET hỗ trợ tạo và ký các dòng chữ ký ở định dạng tệp DOCX. Bạn có thể tạo và ký các dòng chữ ký trong tệp DOCX bằng các phương thức và lớp được cung cấp.
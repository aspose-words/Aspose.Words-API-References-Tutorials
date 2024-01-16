---
title: Đặt Id nhà cung cấp chữ ký trong tài liệu Word
linktitle: Đặt Id nhà cung cấp chữ ký trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt ID nhà cung cấp chữ ký trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/set-signature-provider-id/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng Đặt ID nhà cung cấp chữ ký với Aspose.Words cho .NET. Tính năng này cho phép bạn chỉ định ID nhà cung cấp chữ ký cho dòng chữ ký trong tài liệu Word. Làm theo các bước dưới đây:

## Bước 1: Load tài liệu và truy cập dòng chữ ký

Bắt đầu bằng cách tải lên tài liệu có chứa dòng chữ ký:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Bước 2: Đặt tùy chọn chữ ký

Tạo một phiên bản của lớp SignOptions và đặt các tùy chọn ký, bao gồm ID nhà cung cấp:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Bước 3: Ký văn bản

Để ký tài liệu, bạn phải sử dụng lớp DigitalSignatureUtil và chỉ định chứng chỉ ký:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Đảm bảo chỉ định đường dẫn chính xác cho tài liệu, chứng chỉ và tài liệu đã ký.

### Mã nguồn mẫu cho Đặt Id nhà cung cấp chữ ký bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để đặt ID nhà cung cấp chữ ký bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Hoàn tất ID nhà cung cấp chữ ký trong tài liệu Word của bạn bằng Aspose.Words for .NET.


## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt ID nhà cung cấp chữ ký cho dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng tải tài liệu, truy cập dòng chữ ký, đặt ID nhà cung cấp và ký vào tài liệu. Khả năng đặt ID nhà cung cấp chữ ký giúp thiết lập danh tính và độ tin cậy của người ký, nâng cao tính bảo mật và tính toàn vẹn của tài liệu Word của bạn. Aspose.Words for .NET cung cấp API mạnh mẽ để Xử lý từ bằng chữ ký số, cho phép bạn tùy chỉnh và quản lý quy trình chữ ký một cách dễ dàng.

### Câu hỏi thường gặp về đặt id nhà cung cấp chữ ký trong tài liệu word

#### Hỏi: ID nhà cung cấp chữ ký trong tài liệu Word là gì?

Trả lời: ID nhà cung cấp chữ ký trong tài liệu Word là mã định danh duy nhất chỉ định nhà cung cấp chữ ký điện tử. Nó giúp xác định thực thể hoặc tổ chức chịu trách nhiệm tạo và quản lý chữ ký số.

#### Câu hỏi: Làm cách nào tôi có thể đặt ID nhà cung cấp chữ ký cho dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Để đặt ID nhà cung cấp chữ ký cho dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tải tài liệu bằng cách sử dụng`Document` class và chỉ định đường dẫn đến tệp tài liệu.
2.  Truy cập dòng chữ ký bằng phương pháp hoặc thuộc tính thích hợp. Ví dụ, bạn có thể sử dụng`GetChild` phương pháp để lấy hình dạng dòng chữ ký.
3. Lấy ID nhà cung cấp từ dòng chữ ký.
4.  Tạo một thể hiện của`SignOptions` lớp và thiết lập`ProviderId` thuộc tính vào ID nhà cung cấp được truy xuất.
5.  Sử dụng`DigitalSignatureUtil.Sign` phương pháp ký tài liệu, cung cấp các tham số cần thiết bao gồm`SignOptions` sự vật.

#### Câu hỏi: Làm cách nào để truy cập dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để truy cập dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng phương pháp hoặc thuộc tính thích hợp để truy xuất hình dạng dòng chữ ký từ cấu trúc của tài liệu. Ví dụ: bạn có thể sử dụng`GetChild` phương pháp với các tham số thích hợp để có được hình dạng dòng chữ ký mong muốn.

#### Câu hỏi: Tôi có thể đặt ID nhà cung cấp chữ ký cho nhiều dòng chữ ký trong tài liệu Word không?

 Trả lời: Có, bạn có thể đặt ID nhà cung cấp chữ ký cho nhiều dòng chữ ký trong tài liệu Word. Bạn có thể lặp qua bộ sưu tập các dòng chữ ký trong tài liệu và đặt ID nhà cung cấp cho từng dòng chữ ký riêng lẻ bằng cách sử dụng`SignOptions.ProviderId` tài sản.

#### Câu hỏi: Mục đích của ID nhà cung cấp chữ ký trong tài liệu Word là gì?

Trả lời: ID nhà cung cấp chữ ký trong tài liệu Word phục vụ mục đích xác định thực thể hoặc tổ chức chịu trách nhiệm tạo và quản lý chữ ký số. Nó giúp thiết lập tính xác thực và độ tin cậy của chữ ký số bằng cách liên kết nó với một nhà cung cấp cụ thể.

#### Câu hỏi: Loại chứng chỉ kỹ thuật số nào có thể được sử dụng để đặt ID nhà cung cấp chữ ký trong tài liệu Word?

Trả lời: Bạn có thể sử dụng chứng chỉ kỹ thuật số X.509 với thông tin nhà cung cấp phù hợp để đặt ID nhà cung cấp chữ ký trong tài liệu Word. Chứng chỉ kỹ thuật số phải được cấp bởi cơ quan cấp chứng chỉ đáng tin cậy (CA) và chứa siêu dữ liệu cần thiết để xác định nhà cung cấp.
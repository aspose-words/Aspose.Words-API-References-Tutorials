---
title: Ký dòng chữ ký hiện có trong tài liệu Word
linktitle: Ký dòng chữ ký hiện có trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách ký dòng chữ ký hiện có trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng chữ ký của dòng chữ ký hiện có với Aspose.Words cho .NET. Tính năng này cho phép bạn ký điện tử vào dòng chữ ký đã có trong tài liệu Word. Làm theo các bước dưới đây:

## Bước 1: Load tài liệu và truy cập dòng chữ ký

Bắt đầu bằng cách tải lên tài liệu chứa dòng chữ ký hiện có:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Bước 2: Đặt tùy chọn chữ ký

Tạo một thể hiện của lớp SignOptions và đặt các tùy chọn chữ ký, bao gồm ID dòng chữ ký và hình ảnh dòng chữ ký:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Đảm bảo chỉ định đường dẫn chính xác đến hình ảnh dòng chữ ký.

## Bước 3: Tải chứng chỉ

Bắt đầu bằng cách tải chứng chỉ ký bằng lớp Chứng chỉHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Hãy đảm bảo chỉ định đường dẫn chính xác tới chứng chỉ và mật khẩu liên quan của bạn.

## Bước 4: Ký dòng chữ ký hiện có

Sử dụng lớp DigitalSignatureUtil để ký dòng chữ ký hiện có:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Đảm bảo chỉ định đường dẫn chính xác cho tài liệu nguồn, tài liệu đã ký và chứng chỉ.

### Mã nguồn ví dụ để ký dòng chữ ký hiện có bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để ký một dòng chữ ký hiện có với Aspose.Words cho .NET:


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng ký dòng chữ ký hiện có trong tài liệu Word bằng Aspose.Words for .NET.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách ký một dòng chữ ký hiện có trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng tải tài liệu, truy cập dòng chữ ký hiện có, đặt tùy chọn ký và ký vào tài liệu. Khả năng ký dòng chữ ký hiện có cung cấp một cách thuận tiện để thêm chữ ký điện tử vào các khu vực được xác định trước trong tài liệu Word của bạn, đảm bảo tính toàn vẹn và xác thực của tài liệu. Aspose.Words for .NET cung cấp API mạnh mẽ để Xử lý văn bản bằng chữ ký điện tử, cho phép bạn tùy chỉnh quy trình ký và nâng cao tính bảo mật cho tài liệu Word của mình.

### Câu hỏi thường gặp

#### Hỏi: Dòng chữ ký hiện có trong tài liệu Word là gì?

Trả lời: Dòng chữ ký hiện có trong tài liệu Word là khu vực được xác định trước để có thể đặt chữ ký. Nó thường được thể hiện bằng một hình dạng hoặc đối tượng trong tài liệu và đóng vai trò là không gian được chỉ định để người ký thêm chữ ký điện tử của họ.

#### Câu hỏi: Làm cách nào tôi có thể ký dòng chữ ký hiện có trong tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Để ký dòng chữ ký hiện có trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tải tài liệu bằng cách sử dụng`Document` class và chỉ định đường dẫn đến tệp tài liệu.
2.  Truy cập dòng chữ ký hiện có bằng phương pháp hoặc thuộc tính thích hợp. Ví dụ, bạn có thể sử dụng`GetChild` phương pháp để lấy hình dạng dòng chữ ký.
3.  Tạo một thể hiện của`SignOptions` lớp và thiết lập`SignatureLineId` thuộc tính vào ID của dòng chữ ký hiện có.
4.  Đặt`SignatureLineImage` tài sản của`SignOptions` lớp vào hình ảnh đại diện cho chữ ký số.
5.  Tải chứng chỉ ký bằng cách sử dụng`CertificateHolder` class và cung cấp chứng chỉ và mật khẩu cần thiết.
6.  Sử dụng`DigitalSignatureUtil.Sign` phương pháp ký tài liệu, cung cấp các tham số cần thiết bao gồm`SignOptions` sự vật.

#### Câu hỏi: Làm cách nào để truy cập dòng chữ ký hiện có trong tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để truy cập dòng chữ ký hiện có trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng phương pháp hoặc thuộc tính thích hợp để truy xuất hình dạng dòng chữ ký từ cấu trúc của tài liệu. Ví dụ: bạn có thể sử dụng`GetChild` phương pháp với các tham số thích hợp để có được hình dạng dòng chữ ký mong muốn.

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của chữ ký số trong dòng chữ ký hiện có không?

Trả lời: Có, bạn có thể tùy chỉnh hình thức của chữ ký số trong dòng chữ ký hiện có bằng cách cung cấp tệp hình ảnh đại diện cho chữ ký. Hình ảnh có thể là biểu tượng, chữ ký viết tay hoặc bất kỳ hình thức thể hiện đồ họa nào khác của chữ ký. Bạn có thể thiết lập`SignatureLineImage` tài sản của`SignOptions` class thành byte của tệp hình ảnh.

#### Hỏi: Tôi có thể ký nhiều dòng chữ ký hiện có trong tài liệu Word không?
 Trả lời: Có, bạn có thể ký nhiều dòng chữ ký hiện có trong tài liệu Word. Bạn cần làm theo các bước cho từng dòng chữ ký riêng biệt, thiết lập phù hợp`SignatureLineId` Và`SignatureLineImage` các giá trị trong`SignOptions` đối tượng cho mỗi dòng chữ ký.

#### Câu hỏi: Tệp hình ảnh nên có định dạng nào cho chữ ký số trong dòng chữ ký hiện có?

 Đáp: Tệp hình ảnh cho chữ ký số trong dòng chữ ký hiện có có thể ở nhiều định dạng khác nhau, chẳng hạn như PNG, JPEG, BMP hoặc GIF. Bạn có thể chỉ định đường dẫn tệp hoặc đọc byte của tệp hình ảnh và gán nó cho`SignatureLineImage` tài sản của`SignOptions` lớp học.

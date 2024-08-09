---
title: Đặt Id nhà cung cấp chữ ký trong tài liệu Word
linktitle: Đặt Id nhà cung cấp chữ ký trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Đặt ID nhà cung cấp chữ ký một cách an toàn trong tài liệu Word bằng Aspose.Words cho .NET. Hãy làm theo hướng dẫn chi tiết gồm 2000 từ của chúng tôi để ký điện tử vào tài liệu của bạn.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/set-signature-provider-id/
---
## Giới thiệu

Này! Vậy là bạn đã có tài liệu Word tuyệt vời cần chữ ký điện tử này rồi phải không? Nhưng không chỉ bất kỳ chữ ký nào—bạn cần đặt ID Nhà cung cấp Chữ ký cụ thể. Cho dù bạn đang xử lý các tài liệu pháp lý, hợp đồng hay bất kỳ thủ tục giấy tờ nào, việc thêm chữ ký điện tử an toàn là rất quan trọng. Trong hướng dẫn này, tôi sẽ hướng dẫn bạn toàn bộ quá trình thiết lập ID Nhà cung cấp Chữ ký trong tài liệu Word bằng Aspose.Words cho .NET. Sẵn sàng? Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Aspose.Words for .NET Library: Nếu bạn chưa có,[tải nó ở đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ IDE tương thích C# nào.
3. Tài liệu Word: Một tài liệu có dòng chữ ký (`Signature line.docx`).
4.  Chứng chỉ số: A`.pfx` tập tin chứng chỉ (ví dụ,`morzal.pfx`).
5. Kiến thức cơ bản về C#: Chỉ là kiến thức cơ bản—đừng lo lắng, chúng tôi sẵn sàng trợ giúp!

Bây giờ chúng ta hãy bắt tay vào hành động!

## Nhập không gian tên

Trước tiên, hãy đảm bảo bạn bao gồm các không gian tên cần thiết trong dự án của mình. Điều này là cần thiết để truy cập thư viện Aspose.Words và các lớp liên quan.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.DigitalSignatures;
```

Được rồi, hãy chia điều này thành các bước đơn giản, dễ hiểu.

## Bước 1: Tải tài liệu Word của bạn

Bước đầu tiên là tải tài liệu Word có chứa dòng chữ ký. Tài liệu này sẽ được sửa đổi để bao gồm chữ ký số với ID Nhà cung cấp Chữ ký được chỉ định.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");
```

 Ở đây, chúng tôi chỉ định thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn.

## Bước 2: Truy cập dòng chữ ký

Tiếp theo, chúng ta cần truy cập dòng chữ ký trong tài liệu. Dòng chữ ký được nhúng dưới dạng đối tượng hình dạng trong tài liệu Word.

```csharp
SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

 Dòng mã này lấy hình dạng đầu tiên trong phần thân của phần đầu tiên của tài liệu và chuyển nó thành một`SignatureLine` sự vật.

## Bước 3: Thiết lập tùy chọn đăng nhập

Bây giờ, chúng tôi tạo các tùy chọn ký hiệu, bao gồm ID nhà cung cấp và ID dòng chữ ký từ dòng chữ ký được truy cập.

```csharp
SignOptions signOptions = new SignOptions
{
    ProviderId = signatureLine.ProviderId,
    SignatureLineId = signatureLine.Id
};
```

Các tùy chọn này sẽ được sử dụng khi ký tài liệu để đảm bảo ID Nhà cung cấp Chữ ký được đặt chính xác.

## Bước 4: Tải chứng chỉ

 Để ký tài liệu bằng kỹ thuật số, bạn cần có chứng chỉ. Đây là cách bạn tải`.pfx` tài liệu:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Thay thế`"aw"` bằng mật khẩu cho tệp chứng chỉ của bạn nếu có.

## Bước 5: Ký vào tài liệu

 Cuối cùng, đã đến lúc ký tài liệu bằng cách sử dụng`DigitalSignatureUtil.Sign` phương pháp.

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
    dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

 Việc này sẽ ký vào tài liệu của bạn và lưu nó dưới dạng một tệp mới,`Digitally signed.docx`.

## Phần kết luận

Và bạn có nó! Bạn đã đặt thành công ID nhà cung cấp chữ ký trong tài liệu Word bằng Aspose.Words cho .NET. Quá trình này không chỉ bảo mật tài liệu của bạn mà còn đảm bảo chúng tuân thủ các tiêu chuẩn chữ ký số. Bây giờ, hãy tiếp tục và thử nó với tài liệu của bạn. Bạn có câu hỏi nào không? Hãy xem phần Câu hỏi thường gặp bên dưới hoặc nhấn vào[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/words/8).

## Câu hỏi thường gặp

### ID Nhà cung cấp Chữ ký là gì?

ID nhà cung cấp chữ ký xác định duy nhất nhà cung cấp chữ ký số, đảm bảo tính xác thực và bảo mật.

### Tôi có thể sử dụng bất kỳ tệp .pfx nào để ký không?

Có, miễn là đó là chứng chỉ kỹ thuật số hợp lệ. Đảm bảo bạn có mật khẩu chính xác nếu nó được bảo vệ.

### Làm cách nào để có được tệp .pfx?

Bạn có thể lấy tệp .pfx từ Cơ quan cấp chứng chỉ (CA) hoặc tạo tệp bằng các công cụ như OpenSSL.

### Tôi có thể ký nhiều tài liệu cùng một lúc không?

Có, bạn có thể lặp qua nhiều tài liệu và áp dụng cùng một quy trình ký cho từng tài liệu.

### Nếu tôi không có dòng chữ ký trong tài liệu của mình thì sao?

Trước tiên, bạn cần chèn dòng chữ ký. Aspose.Words cung cấp các phương thức để thêm dòng chữ ký theo chương trình.

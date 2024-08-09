---
title: Tạo dòng chữ ký mới và đặt Id nhà cung cấp
linktitle: Tạo dòng chữ ký mới và đặt Id nhà cung cấp
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo dòng chữ ký mới và đặt ID nhà cung cấp trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Giới thiệu

Này, những người đam mê công nghệ! Bạn đã bao giờ tự hỏi làm cách nào để thêm dòng chữ ký vào tài liệu Word của mình theo chương trình chưa? Chà, hôm nay chúng ta sẽ đi sâu vào vấn đề đó bằng cách sử dụng Aspose.Words cho .NET. Hướng dẫn này sẽ hướng dẫn bạn từng bước, giúp việc tạo dòng chữ ký mới và đặt ID nhà cung cấp trong tài liệu Word của bạn trở nên dễ dàng như ăn bánh. Cho dù bạn đang tự động hóa quá trình xử lý tài liệu hay chỉ muốn hợp lý hóa quy trình làm việc của mình thì hướng dẫn này sẽ giúp bạn.

## Điều kiện tiên quyết

Trước khi bắt tay vào việc, hãy đảm bảo rằng chúng ta có mọi thứ mình cần:

1.  Aspose.Words for .NET: Nếu bạn chưa có, hãy tải xuống[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác.
3. .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework.
4. Chứng chỉ PFX: Để ký tài liệu, bạn sẽ cần chứng chỉ PFX. Bạn có thể lấy một cái từ một cơ quan cấp chứng chỉ đáng tin cậy.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết vào dự án C# của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Được rồi, hãy đi vào vấn đề chính. Dưới đây là bảng phân tích chi tiết từng bước để tạo dòng chữ ký mới và đặt ID nhà cung cấp.

## Bước 1: Tạo một tài liệu mới

Để bắt đầu, chúng ta cần tạo một tài liệu Word mới. Đây sẽ là canvas cho dòng chữ ký của chúng tôi.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Trong đoạn mã này, chúng tôi đang khởi tạo một`Document` và một`DocumentBuilder` . các`DocumentBuilder` giúp chúng ta thêm các phần tử vào tài liệu của mình.

## Bước 2: Xác định các tùy chọn dòng chữ ký

Tiếp theo, chúng tôi xác định các tùy chọn cho dòng chữ ký của mình. Điều này bao gồm tên, chức danh, email và các chi tiết khác của người ký.

```csharp
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
```

Các tùy chọn này cá nhân hóa dòng chữ ký, làm cho nó rõ ràng và chuyên nghiệp.

## Bước 3: Chèn dòng chữ ký

Với các tùy chọn đã được đặt, giờ đây chúng ta có thể chèn dòng chữ ký vào tài liệu.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Ở đây,`InsertSignatureLine` phương thức thêm dòng chữ ký và chúng tôi chỉ định ID nhà cung cấp duy nhất cho nó.

## Bước 4: Lưu tài liệu

Sau khi chèn dòng chữ ký xong chúng ta hãy lưu tài liệu lại.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Thao tác này sẽ lưu tài liệu của bạn với dòng chữ ký mới được thêm vào.

## Bước 5: Thiết lập tùy chọn đăng nhập

Bây giờ, chúng ta cần thiết lập các tùy chọn để ký tài liệu. Điều này bao gồm ID dòng chữ ký, ID nhà cung cấp, nhận xét và thời gian ký.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Các tùy chọn này đảm bảo tài liệu được ký với các chi tiết chính xác.

## Bước 6: Tạo chủ sở hữu chứng chỉ

Để ký tài liệu, chúng tôi sẽ sử dụng chứng chỉ PFX. Hãy tạo một chủ sở hữu chứng chỉ cho nó.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Đảm bảo thay thế`"morzal.pfx"` với tệp chứng chỉ thực tế của bạn và`"aw"` bằng mật khẩu chứng chỉ của bạn.

## Bước 7: Ký tài liệu

Cuối cùng chúng ta ký văn bản bằng tiện ích chữ ký số.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Việc này sẽ ký vào tài liệu và lưu nó dưới dạng một tệp mới.

## Phần kết luận

Và bạn có nó! Bạn đã tạo thành công dòng chữ ký mới và đặt ID nhà cung cấp trong tài liệu Word bằng Aspose.Words cho .NET. Thư viện mạnh mẽ này giúp việc quản lý và tự động hóa các tác vụ xử lý tài liệu trở nên cực kỳ dễ dàng. Hãy dùng thử và xem nó có thể hợp lý hóa quy trình làm việc của bạn như thế nào.

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh hình thức của dòng chữ ký không?
Tuyệt đối! Bạn có thể điều chỉnh các tùy chọn khác nhau trong`SignatureLineOptions` để phù hợp với nhu cầu của bạn.

### Nếu tôi không có chứng chỉ PFX thì sao?
Bạn sẽ cần phải có được một chứng chỉ từ cơ quan cấp chứng chỉ đáng tin cậy. Nó rất cần thiết cho việc ký các tài liệu kỹ thuật số.

### Tôi có thể thêm nhiều dòng chữ ký vào một tài liệu không?
Có, bạn có thể thêm bao nhiêu dòng chữ ký nếu cần bằng cách lặp lại quá trình chèn với các tùy chọn khác nhau.

### Aspose.Words cho .NET có tương thích với .NET Core không?
Có, Aspose.Words for .NET hỗ trợ .NET Core, khiến nó trở nên linh hoạt cho các môi trường phát triển khác nhau.

### Chữ ký số an toàn đến mức nào?
Chữ ký số được tạo bằng Aspose.Words có độ bảo mật cao, miễn là bạn sử dụng chứng chỉ hợp lệ và đáng tin cậy.
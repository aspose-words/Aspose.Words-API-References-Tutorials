---
title: Tạo và ký dòng chữ ký mới
linktitle: Tạo và ký dòng chữ ký mới
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo và ký điện tử dòng chữ ký trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước này. Hoàn hảo cho việc tự động hóa tài liệu.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Giới thiệu

Này! Như vậy, bạn đã có một tài liệu Word và bạn cần thêm dòng chữ ký rồi ký điện tử. Nghe có vẻ phức tạp? Không có gì! Nhờ Aspose.Words dành cho .NET, bạn có thể đạt được điều này một cách liền mạch chỉ với một vài dòng mã. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn toàn bộ quá trình từ thiết lập môi trường đến lưu tài liệu của bạn bằng chữ ký mới sáng bóng. Sẵn sàng? Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng ta chuyển sang mã, hãy đảm bảo bạn có mọi thứ mình cần:
1.  Aspose.Words cho .NET - Bạn có thể[tải về tại đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển .NET - Visual Studio rất được khuyến khích.
3. Tài liệu cần ký - Tạo một tài liệu Word đơn giản hoặc sử dụng tài liệu hiện có.
4.  Tệp chứng chỉ - Điều này cần thiết cho chữ ký số. Bạn có thể sử dụng một`.pfx` tài liệu.
5. Hình ảnh cho dòng chữ ký - Tùy chọn, tệp hình ảnh cho chữ ký.

## Nhập không gian tên

Đầu tiên, chúng ta cần nhập các không gian tên cần thiết. Bước này rất quan trọng vì nó thiết lập môi trường để sử dụng các chức năng của Aspose.Words.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Bước 1: Thiết lập thư mục tài liệu

Mọi dự án đều cần có sự khởi đầu tốt đẹp. Hãy thiết lập đường dẫn đến thư mục tài liệu của bạn. Đây là nơi tài liệu của bạn sẽ được lưu và lấy ra.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo một tài liệu mới

Bây giờ, hãy tạo một tài liệu Word mới bằng Aspose.Words. Đây sẽ là canvas nơi chúng tôi thêm dòng chữ ký.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn dòng chữ ký

 Đây là nơi phép thuật xảy ra. Chúng tôi chèn một dòng chữ ký vào tài liệu của mình bằng cách sử dụng`DocumentBuilder` lớp học.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Bước 4: Lưu tài liệu bằng dòng chữ ký

Sau khi đã có dòng chữ ký, chúng ta cần lưu tài liệu. Đây là bước trung gian trước khi chúng ta tiến hành ký kết.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Bước 5: Thiết lập tùy chọn đăng nhập

Bây giờ, hãy thiết lập các tùy chọn để ký tài liệu. Điều này bao gồm việc chỉ định ID dòng chữ ký và hình ảnh sẽ được sử dụng.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Bước 6: Tải chứng chỉ

Chữ ký số yêu cầu phải có chứng chỉ. Ở đây, chúng tôi tải tệp chứng chỉ sẽ được sử dụng để ký tài liệu.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Bước 7: Ký tài liệu

 Đây là bước cuối cùng. Chúng tôi sử dụng`DigitalSignatureUtil`lớp để ký tài liệu. Tài liệu đã ký được lưu với tên mới.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Phần kết luận

Và bạn có nó rồi đấy! Với các bước này, bạn đã tạo thành công tài liệu Word mới, thêm dòng chữ ký và ký tên kỹ thuật số bằng Aspose.Words cho .NET. Đó là một công cụ mạnh mẽ giúp việc tự động hóa tài liệu trở nên dễ dàng. Cho dù bạn đang xử lý các hợp đồng, thỏa thuận hay bất kỳ tài liệu chính thức nào, phương pháp này đều đảm bảo chúng được ký và xác thực một cách an toàn.

## Câu hỏi thường gặp

### Tôi có thể sử dụng định dạng hình ảnh khác cho dòng chữ ký được không?
Có, bạn có thể sử dụng nhiều định dạng hình ảnh khác nhau như PNG, JPG, BMP, v.v.

###  Có cần thiết phải sử dụng một`.pfx` file for the certificate?
 Vâng, một`.pfx` file là một định dạng phổ biến để lưu trữ thông tin mật mã bao gồm chứng chỉ và khóa riêng.

### Tôi có thể thêm nhiều dòng chữ ký vào một tài liệu không?
Tuyệt đối! Bạn có thể chèn nhiều dòng chữ ký bằng cách lặp lại bước chèn cho từng dòng chữ ký.

### Nếu tôi không có chứng chỉ kỹ thuật số thì sao?
Bạn sẽ cần lấy chứng chỉ kỹ thuật số từ cơ quan cấp chứng chỉ đáng tin cậy hoặc tạo chứng chỉ bằng cách sử dụng các công cụ như OpenSSL.

### Làm cách nào để xác minh chữ ký số trong tài liệu?
Bạn có thể mở tài liệu đã ký trong Word và đi đến chi tiết chữ ký để xác minh tính xác thực và tính toàn vẹn của chữ ký.
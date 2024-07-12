---
title: Ký tài liệu Word
linktitle: Ký tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách ký tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước này. Bảo mật tài liệu của bạn một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/sign-document/
---
## Giới thiệu

Trong thế giới kỹ thuật số ngày nay, việc bảo mật tài liệu của bạn trở nên quan trọng hơn bao giờ hết. Chữ ký số cung cấp một cách để đảm bảo tính xác thực và tính toàn vẹn của tài liệu của bạn. Nếu bạn đang muốn ký một tài liệu Word theo chương trình bằng Aspose.Words cho .NET thì bạn đã đến đúng nơi. Hướng dẫn này sẽ hướng dẫn bạn toàn bộ quá trình, từng bước một, một cách đơn giản và hấp dẫn.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, có một số điều bạn cần chuẩn bị sẵn:

1.  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt phiên bản Aspose.Words for .NET mới nhất. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/words/net/).
2. Môi trường .NET: Đảm bảo bạn đã thiết lập môi trường phát triển .NET (ví dụ: Visual Studio).
3. Chứng chỉ kỹ thuật số: Lấy chứng chỉ kỹ thuật số (ví dụ: tệp .pfx) để ký tài liệu.
4. Tài liệu cần ký: Chuẩn bị sẵn tài liệu Word mà bạn muốn ký.

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết. Thêm các lệnh sử dụng sau vào dự án của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.Security.Cryptography.X509Certificates;
```

Bây giờ, hãy chia quy trình thành các bước có thể quản lý được.

## Bước 1: Tải chứng chỉ số

Bước đầu tiên là tải chứng chỉ số từ tệp. Giấy chứng nhận này sẽ được sử dụng để ký tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tải chứng chỉ kỹ thuật số.
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

### Giải trình

- `dataDir`: Đây là thư mục lưu trữ chứng chỉ và tài liệu của bạn.
- `CertificateHolder.Create` : Phương thức này tải chứng chỉ từ đường dẫn đã chỉ định. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục của bạn và`"morzal.pfx"` với tên của tệp chứng chỉ của bạn. Các`"aw"` là mật khẩu cho chứng chỉ.

## Bước 2: Tải tài liệu Word

Tiếp theo, tải tài liệu Word bạn muốn ký.

```csharp
// Tải tài liệu cần được ký.
Document doc = new Document(dataDir + "Digitally signed.docx");
```

### Giải trình

- `Document` : Lớp này đại diện cho tài liệu Word. Thay thế`"Digitally signed.docx"`với tên tài liệu của bạn.

## Bước 3: Ký vào tài liệu

 Bây giờ, hãy sử dụng`DigitalSignatureUtil.Sign` phương thức ký văn bản.

```csharp
// Ký tài liệu.
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx", certHolder);
```

### Giải trình

- `DigitalSignatureUtil.Sign`: Phương pháp này ký tài liệu bằng chứng chỉ đã tải. Tham số đầu tiên là đường dẫn đến tài liệu gốc, tham số thứ hai là đường dẫn đến tài liệu đã ký và tham số thứ ba là chủ sở hữu chứng chỉ.

## Bước 4: Lưu tài liệu đã ký

Cuối cùng, lưu tài liệu đã ký vào vị trí đã chỉ định.

```csharp
// Lưu tài liệu đã ký.
doc.Save(dataDir + "Document.Signed.docx");
```

### Giải trình

- `doc.Save` : Phương pháp này lưu tài liệu đã ký. Thay thế`"Document.Signed.docx"` với tên mong muốn của tài liệu đã ký của bạn.

## Phần kết luận

Và bạn có nó rồi đấy! Bạn đã ký thành công tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước đơn giản này, bạn có thể đảm bảo tài liệu của mình được ký và xác thực an toàn. Hãy nhớ rằng, chữ ký điện tử là một công cụ mạnh mẽ trong việc bảo vệ tính toàn vẹn của tài liệu của bạn, vì vậy hãy sử dụng chúng bất cứ khi nào cần thiết.

## Câu hỏi thường gặp

### Chữ ký số là gì?
Chữ ký số là một dạng chữ ký điện tử có thể được sử dụng để xác thực danh tính của người ký và đảm bảo rằng tài liệu không bị thay đổi.

### Tại sao tôi cần chứng chỉ kỹ thuật số?
Cần có chứng chỉ số để tạo chữ ký số. Nó chứa khóa công khai và danh tính của chủ sở hữu chứng chỉ, cung cấp phương tiện để xác minh chữ ký.

### Tôi có thể sử dụng bất kỳ tệp .pfx nào để ký không?
Có, miễn là tệp .pfx chứa chứng chỉ kỹ thuật số hợp lệ và bạn có mật khẩu để truy cập nó.

### Aspose.Words cho .NET có được sử dụng miễn phí không?
 Aspose.Words for .NET là một thư viện thương mại. Bạn có thể tải về dùng thử miễn phí[đây](https://releases.aspose.com/) , nhưng bạn sẽ cần phải mua giấy phép để có đầy đủ chức năng. Bạn có thể mua nó[đây](https://purchase.aspose.com/buy).

### Tôi có thể tìm thêm thông tin về Aspose.Words cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu toàn diện[đây](https://reference.aspose.com/words/net/) và hỗ trợ[đây](https://forum.aspose.com/c/words/8).
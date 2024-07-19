---
title: Ký tài liệu Word được mã hóa
linktitle: Ký tài liệu Word được mã hóa
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách ký các tài liệu Word được mã hóa bằng Aspose.Words cho .NET với hướng dẫn từng bước chi tiết này. Hoàn hảo cho các nhà phát triển.
type: docs
weight: 10
url: /vi/net/programming-with-digital-signatures/signing-encrypted-document/
---
## Giới thiệu

Bạn đã bao giờ tự hỏi làm thế nào để ký một tài liệu Word được mã hóa chưa? Hôm nay, chúng ta sẽ hướng dẫn quy trình này bằng Aspose.Words cho .NET. Hãy thắt dây an toàn và sẵn sàng cho phần hướng dẫn chi tiết, hấp dẫn và thú vị!

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có mọi thứ bạn cần:

1.  Aspose.Words for .NET: Tải xuống và cài đặt từ[đây](https://releases.aspose.com/words/net/).
2. Visual Studio: Đảm bảo bạn đã cài đặt nó.
3. Chứng chỉ hợp lệ: Bạn sẽ cần tệp chứng chỉ .pfx.
4. Kiến thức C# cơ bản: Hiểu những điều cơ bản sẽ giúp hướng dẫn này trôi chảy hơn.

## Nhập không gian tên

Đầu tiên, hãy nhập các không gian tên cần thiết. Đây là những điều rất quan trọng để truy cập các chức năng của Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Words.DigitalSignatures;
```

Bây giờ, hãy chia quy trình thành các bước đơn giản, dễ quản lý.

## Bước 1: Thiết lập dự án của bạn

Trước tiên, hãy thiết lập dự án Visual Studio của bạn. Mở Visual Studio và tạo Ứng dụng bảng điều khiển C# mới. Đặt tên nó mang tính mô tả như "SignEncryptedWordDoc".

## Bước 2: Thêm Aspose.Words vào dự án của bạn

Tiếp theo, chúng ta cần thêm Aspose.Words vào dự án của bạn. Có một số cách để thực hiện việc này nhưng sử dụng NuGet là cách đơn giản nhất. 

1. Mở Bảng điều khiển quản lý gói NuGet từ Công cụ > Trình quản lý gói NuGet > Bảng điều khiển quản lý gói.
2. Chạy lệnh sau:

```powershell
Install-Package Aspose.Words
```

## Bước 3: Chuẩn bị thư mục tài liệu

Bạn sẽ cần một thư mục để lưu trữ tài liệu và chứng chỉ Word của mình. Hãy tạo một cái.

1. Tạo một thư mục trên máy tính của bạn. Để đơn giản, hãy gọi nó là "DocumentDirectory".
2. Đặt tài liệu Word của bạn (ví dụ: "Document.docx") và chứng chỉ .pfx của bạn (ví dụ: "morzal.pfx") trong thư mục này.

## Bước 4: Viết mã

 Bây giờ, hãy đi sâu vào mã. Mở của bạn`Program.cs` tập tin và bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn và khởi tạo`SignOptions` với mật khẩu giải mã.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };
```

## Bước 5: Tải chứng chỉ

 Tiếp theo, tải chứng chỉ của bạn bằng cách sử dụng`CertificateHolder`lớp học. Điều này sẽ yêu cầu đường dẫn đến tệp .pfx của bạn và mật khẩu của chứng chỉ.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Bước 6: Ký tài liệu

 Cuối cùng, sử dụng`DigitalSignatureUtil.Sign` phương pháp ký tài liệu Word được mã hóa của bạn. Phương pháp này yêu cầu tệp đầu vào, tệp đầu ra, chủ sở hữu chứng chỉ và tùy chọn ký hiệu.

```csharp
DigitalSignatureUtil.Sign(
    dataDir + "Document.docx",
    dataDir + "DigitallySignedDocument.docx",
    certHolder,
    signOptions);
```

## Bước 7: Chạy mã

Lưu tập tin của bạn và chạy dự án. Nếu mọi thứ được thiết lập chính xác, bạn sẽ thấy tài liệu đã ký của mình trong thư mục được chỉ định.

## Phần kết luận

Và bạn có nó rồi đấy! Bạn đã ký thành công tài liệu Word được mã hóa bằng Aspose.Words cho .NET. Với thư viện mạnh mẽ này, việc ký kỹ thuật số trở nên dễ dàng, ngay cả đối với các tệp được mã hóa. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Tôi có thể sử dụng loại chứng chỉ khác không?
Có, Aspose.Words hỗ trợ nhiều loại chứng chỉ khác nhau, miễn là chúng ở đúng định dạng.

### Có thể ký nhiều văn bản cùng một lúc được không?
Tuyệt đối! Bạn có thể lặp qua một bộ sưu tập tài liệu và ký từng tài liệu theo chương trình.

### Nếu tôi quên mật khẩu giải mã thì sao?
Thật không may, nếu không có mật khẩu giải mã, bạn sẽ không thể ký vào tài liệu.

### Tôi có thể thêm chữ ký hiển thị vào tài liệu không?
Có, Aspose.Words cũng cho phép bạn thêm chữ ký điện tử hiển thị.

### Có cách nào để xác minh chữ ký?
 Có, bạn có thể sử dụng`DigitalSignatureUtil.Verify` phương pháp xác minh chữ ký.
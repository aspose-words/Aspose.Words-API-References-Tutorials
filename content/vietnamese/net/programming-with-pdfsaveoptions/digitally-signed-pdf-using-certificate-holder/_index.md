---
title: Thêm chữ ký số vào PDF bằng Người giữ chứng chỉ
linktitle: Thêm chữ ký số vào PDF bằng Người giữ chứng chỉ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm Chữ ký số vào PDF bằng cách sử dụng Người giữ chứng chỉ với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để thêm chữ ký điện tử vào PDF bằng cách sử dụng chủ sở hữu chứng chỉ với Aspose.Words cho .NET. Chữ ký số bổ sung thêm một lớp bảo mật và tính toàn vẹn cho tài liệu PDF. Làm theo các bước dưới đây:

## Bước 1: Tạo tài liệu và thêm nội dung

Bắt đầu bằng cách tạo một thể hiện của lớp Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Thêm nội dung vào tài liệu

 Sau đó sử dụng`DocumentBuilder`để thêm nội dung vào tài liệu. Ví dụ: để thêm một đoạn có chứa văn bản "PDF đã ký thử", hãy sử dụng`Writeln` phương pháp:

```csharp
builder.Writeln("Test Signed PDF.");
```

Bạn có thể thêm các mục nội dung khác nếu cần.

## Bước 3: Đặt tùy chọn lưu PDF

Tạo một thể hiện của lớp PdfSaveOptions và chỉ định chi tiết chữ ký số:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Hãy đảm bảo chỉ định đường dẫn chính xác tới chứng chỉ và mật khẩu liên quan của bạn. Bạn cũng có thể tùy chỉnh lý do và vị trí chữ ký.

## Bước 4: Lưu tài liệu dưới dạng PDF được ký điện tử

 Sử dụng`Save` phương pháp lưu tài liệu dưới dạng PDF bằng cách chỉ định các tùy chọn lưu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Đảm bảo chỉ định đường dẫn chính xác để lưu tệp PDF được ký điện tử.

Bằng cách làm theo các bước này, bạn có thể dễ dàng tạo tệp PDF được ký điện tử có chứng chỉ bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Pdf được ký điện tử bằng cách sử dụng Người giữ chứng chỉ bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho Pdf được ký điện tử bằng cách sử dụng chủ sở hữu chứng chỉ từ một tài liệu sử dụng Aspose.Words cho .NET:

```csharp

            // Đường dẫn đến thư mục tài liệu.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá các bước để thêm chữ ký điện tử vào tài liệu PDF bằng chứng chỉ có Aspose.Words cho .NET. Chữ ký số bổ sung thêm một lớp bảo mật và tính toàn vẹn cho tài liệu, do đó đảm bảo tính xác thực của nó và giúp phát hiện bất kỳ sửa đổi nào sau đó. Bằng cách làm theo các bước đã cho, bạn có thể dễ dàng tạo tệp PDF được ký điện tử bằng chứng chỉ với Aspose.Words cho .NET.

### Các câu hỏi thường gặp

#### Hỏi: Chữ ký điện tử là gì và tại sao nó lại quan trọng trong tài liệu PDF?
Đáp: Chữ ký số là một kỹ thuật bảo mật giúp đảm bảo tính xác thực, tính toàn vẹn và không thể chối bỏ của tài liệu điện tử, chẳng hạn như tệp PDF. Nó sử dụng chứng chỉ kỹ thuật số để thêm một lớp bảo mật cho tài liệu, giúp xác minh danh tính của tác giả và phát hiện mọi thay đổi tiếp theo đối với nội dung.

#### Câu hỏi: Làm cách nào tôi có thể thêm chữ ký điện tử vào tài liệu PDF bằng chứng chỉ với Aspose.Words cho .NET?
Trả lời: Để thêm chữ ký điện tử vào tài liệu PDF bằng chứng chỉ có Aspose.Words cho .NET, hãy làm theo các bước sau:

 Tạo một thể hiện của`Document` lớp để đại diện cho tài liệu.

 Sử dụng`DocumentBuilder` class để thêm nội dung mong muốn vào tài liệu.

 Tạo một thể hiện của`PdfSaveOptions` lớp và chỉ định chi tiết chữ ký số bằng cách sử dụng`PdfDigitalSignatureDetails` lớp học. Bạn sẽ cần cung cấp đường dẫn đến chứng chỉ (`CertificateHolder.Create`), mật khẩu liên quan cũng như lý do và vị trí ký.

 Sử dụng`Save` phương pháp lưu tài liệu ở định dạng PDF chỉ định các tùy chọn lưu.

#### Câu hỏi: Làm cách nào để có được chứng chỉ để thêm chữ ký điện tử vào tài liệu PDF?
Đáp: Để có được chứng chỉ nhằm thêm chữ ký điện tử vào tài liệu PDF, bạn thường có thể liên hệ với cơ quan cấp chứng chỉ (CA) hoặc nhà cung cấp dịch vụ ủy thác. Các tổ chức này cấp chứng chỉ kỹ thuật số sau khi xác minh danh tính của bạn và xác thực yêu cầu của bạn. Sau khi nhận được chứng chỉ, bạn có thể sử dụng nó trong ứng dụng của mình để thêm chữ ký điện tử vào tài liệu PDF.

#### Hỏi: Có thể tùy chỉnh các chi tiết của chữ ký số như lý do và vị trí không?
 Trả lời: Có, bạn có thể tùy chỉnh chi tiết chữ ký số bằng cách chỉ định lý do và vị trí của chữ ký. Trong mã ví dụ được cung cấp, bạn có thể sửa đổi các giá trị của`reason`Và`location` các thông số khi tạo`PdfDigitalSignatureDetails` sự vật. Đảm bảo cung cấp thông tin phù hợp cho từng tham số để phản ánh lý do và vị trí của chữ ký trong tài liệu PDF của bạn.
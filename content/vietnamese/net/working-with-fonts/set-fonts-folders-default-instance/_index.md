---
title: Đặt phiên bản mặc định của thư mục phông chữ
linktitle: Đặt phiên bản mặc định của thư mục phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt thư mục phông chữ cho phiên bản mặc định trong Aspose.Words cho .NET bằng hướng dẫn từng bước này. Tùy chỉnh tài liệu Word của bạn một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folders-default-instance/
---
## Giới thiệu

Này, anh bạn lập trình viên! Nếu bạn đang làm việc với tài liệu Word trong .NET, có thể bạn biết tầm quan trọng của việc có phông chữ phù hợp. Hôm nay, chúng ta sẽ đi sâu vào cách đặt thư mục phông chữ cho phiên bản mặc định bằng Aspose.Words cho .NET. Hãy tưởng tượng bạn có tất cả các phông chữ tùy chỉnh trong tầm tay, làm cho tài liệu của bạn trông giống hệt như cách bạn hình dung về chúng. Nghe có vẻ tuyệt vời phải không? Hãy bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào chi tiết quan trọng, hãy đảm bảo bạn có mọi thứ bạn cần:
-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện. Nếu không, bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ IDE tương thích .NET nào khác.
- Kiến thức cơ bản về C#: Bạn nên thành thạo lập trình C#.
- Thư mục Phông chữ: Một thư mục chứa các phông chữ tùy chỉnh của bạn.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Điều này giúp truy cập các lớp và phương thức cần thiết để thiết lập thư mục phông chữ.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Hãy chia nhỏ quy trình thành các bước đơn giản, dễ hiểu.

## Bước 1: Xác định thư mục dữ liệu

Mọi hành trình tuyệt vời đều bắt đầu bằng một bước duy nhất và hành trình của chúng tôi bắt đầu bằng việc xác định thư mục nơi tài liệu của bạn được lưu trữ. Đây là nơi Aspose.Words sẽ tìm tài liệu Word của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ở đây thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn. Đây là nơi đặt tài liệu nguồn của bạn và nơi lưu kết quả đầu ra.

## Bước 2: Đặt thư mục phông chữ

 Bây giờ, hãy cho Aspose.Words biết nơi tìm phông chữ tùy chỉnh của bạn. Điều này được thực hiện bằng cách thiết lập thư mục phông chữ bằng cách sử dụng`FontSettings.DefaultInstance.SetFontsFolder` phương pháp.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

 Trong dòng này,`"C:\\MyFonts\\"` là đường dẫn đến thư mục phông chữ tùy chỉnh của bạn. Tham số thứ hai,`true`, cho biết các phông chữ trong thư mục này phải được quét đệ quy.

## Bước 3: Tải tài liệu của bạn

 Với thư mục phông chữ đã được đặt, bước tiếp theo là tải tài liệu Word của bạn vào Aspose.Words. Việc này được thực hiện bằng cách sử dụng`Document` lớp học.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Đây,`dataDir + "Rendering.docx"` đề cập đến đường dẫn đầy đủ của tài liệu Word của bạn. Đảm bảo tài liệu của bạn nằm trong thư mục được chỉ định.

## Bước 4: Lưu tài liệu

Bước cuối cùng là lưu tài liệu của bạn sau khi thiết lập thư mục phông chữ. Điều này đảm bảo rằng phông chữ tùy chỉnh của bạn được áp dụng chính xác trong đầu ra.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

Dòng này lưu tài liệu của bạn dưới dạng PDF với các phông chữ tùy chỉnh được áp dụng. Tệp đầu ra sẽ nằm trong cùng thư mục với tài liệu nguồn của bạn.

## Phần kết luận

Và bạn có nó! Việc đặt thư mục phông chữ cho phiên bản mặc định trong Aspose.Words cho .NET thật dễ dàng khi bạn chia nó thành các bước đơn giản. Bằng cách làm theo hướng dẫn này, bạn có thể đảm bảo rằng tài liệu Word của bạn trông chính xác như bạn muốn, với tất cả các phông chữ tùy chỉnh được áp dụng. Vì vậy, hãy tiếp tục, dùng thử và làm cho tài liệu của bạn tỏa sáng!

## Câu hỏi thường gặp

### Tôi có thể đặt nhiều thư mục phông chữ không?
 Có, bạn có thể đặt nhiều thư mục phông chữ bằng cách sử dụng`SetFontsFolders` phương thức chấp nhận một loạt đường dẫn thư mục.

### Aspose.Words hỗ trợ những định dạng tệp nào để lưu tài liệu?
Aspose.Words hỗ trợ nhiều định dạng khác nhau bao gồm DOCX, PDF, HTML, EPUB, v.v.

### Có thể sử dụng phông chữ trực tuyến trong Aspose.Words không?
Không, Aspose.Words hiện chỉ hỗ trợ các tệp phông chữ cục bộ.

### Làm cách nào để đảm bảo phông chữ tùy chỉnh của tôi được nhúng trong tệp PDF đã lưu?
 Bằng cách thiết lập`FontSettings` chính xác và đảm bảo phông chữ có sẵn, Aspose.Words sẽ nhúng chúng vào đầu ra PDF.

### Điều gì xảy ra nếu không tìm thấy phông chữ trong thư mục đã chỉ định?
Aspose.Words sẽ sử dụng phông chữ dự phòng nếu không tìm thấy phông chữ được chỉ định.
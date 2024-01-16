---
title: Nhúng phông chữ tập hợp con vào tài liệu PDF
linktitle: Nhúng phông chữ tập hợp con vào tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để nhúng các tập hợp phông chữ con vào tài liệu PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng tính năng nhúng tập hợp con phông chữ với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách nhúng các tập hợp con phông chữ vào tài liệu và tạo một tệp PDF chỉ chứa các ký tự được sử dụng trong tài liệu.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu lên

Tiếp theo, chúng ta cần tải tài liệu mà chúng ta muốn xử lý. Trong ví dụ này, chúng tôi giả sử tài liệu có tên là "Rendering.docx" và nằm trong thư mục tài liệu được chỉ định.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu dưới dạng PDF

 Để tạo một tệp PDF chỉ chứa các tập hợp con phông chữ được sử dụng trong tài liệu, chúng ta cần định cấu hình`PdfSaveOptions` đối tượng với`EmbedFullFonts` thuộc tính được đặt thành`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Bước 4: Lưu tài liệu dưới dạng PDF với các tập hợp phông chữ

 Cuối cùng, chúng ta có thể lưu tài liệu dưới dạng PDF bằng cách sử dụng các tập hợp phông chữ. Chỉ định tên tệp đầu ra và`saveOptions` đối tượng chúng ta đã cấu hình ở bước trước.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Đó là tất cả ! Bạn đã nhúng thành công các tập hợp con phông chữ vào tài liệu và tạo một tệp PDF chỉ chứa các ký tự được sử dụng trong tài liệu bằng Aspose.Words cho .NET.

### Mã nguồn mẫu để nhúng các tập hợp con phông chữ với Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Tệp PDF đầu ra sẽ chứa các tập hợp con phông chữ trong tài liệu.
	// Chỉ các glyph được sử dụng trong tài liệu mới được đưa vào phông chữ PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã tìm hiểu cách nhúng các tập hợp phông chữ con vào tài liệu PDF bằng Aspose.Words cho .NET. Nhúng các tập hợp con phông chữ giúp giảm kích thước tệp PDF trong khi vẫn giữ được hình thức của tài liệu bằng cách chỉ sử dụng các ký tự thực sự được sử dụng. Điều này đảm bảo khả năng tương thích và hiệu suất tốt hơn khi xem và in PDF. Vui lòng khám phá thêm các tính năng của Aspose.Words for .NET để tối ưu hóa việc tạo tài liệu PDF của bạn với các tập hợp phông chữ được nhúng.

### Các câu hỏi thường gặp

#### Hỏi: Việc nhúng các tập hợp phông chữ con vào tài liệu PDF là gì?
Đáp: Nhúng các tập hợp phông chữ con vào tài liệu PDF là quá trình chỉ bao gồm các ký tự được sử dụng trong tài liệu, thay vì bao gồm tất cả các phông chữ hoàn chỉnh. Điều này làm giảm kích thước của tệp PDF bằng cách chỉ bao gồm dữ liệu phông chữ cần thiết để hiển thị các ký tự thực sự được sử dụng trong tài liệu.

#### Câu hỏi: Sự khác biệt giữa việc nhúng phông chữ đầy đủ và việc nhúng các tập hợp con phông chữ là gì?
Trả lời: Nhúng phông chữ đầy đủ có nghĩa là bao gồm tất cả các phông chữ được sử dụng trong tài liệu vào tệp PDF, điều này đảm bảo rằng tài liệu sẽ được hiển thị chính xác như được thiết kế nhưng có thể làm tăng kích thước của tệp PDF. Ngược lại, việc nhúng các tập hợp phông chữ chỉ chứa các glyph được sử dụng trong tài liệu, do đó làm giảm kích thước của tệp PDF nhưng hạn chế khả năng sao chép chính xác giao diện của tài liệu nếu các ký tự bổ sung được thêm vào sau đó.

#### Câu hỏi: Làm cách nào tôi có thể nhúng các tập hợp phông chữ con vào tài liệu PDF bằng Aspose.Words cho .NET?
Trả lời: Để nhúng các tập hợp phông chữ con vào tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục tài liệu bằng cách thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu bạn muốn xử lý bằng cách sử dụng`Document` lớp và đường dẫn tài liệu.

 Định cấu hình các tùy chọn lưu PDF bằng cách tạo một phiên bản của`PdfSaveOptions` lớp và thiết lập`EmbedFullFonts`tài sản để`false`Điều này đảm bảo rằng chỉ các tập hợp phông chữ được sử dụng trong tài liệu mới được đưa vào tệp PDF.

 Lưu tài liệu ở định dạng PDF với các tập hợp phông chữ được nhúng bằng cách sử dụng`Save` phương pháp của`Document` đối tượng, chỉ định tên của tệp đầu ra và các tùy chọn lưu được cấu hình trước đó.

#### Hỏi: Lợi ích của việc nhúng các tập hợp phông chữ con vào tài liệu PDF là gì?
Đáp: Lợi ích của việc nhúng các tập hợp phông chữ con vào tài liệu PDF là:

Giảm kích thước tệp PDF: Bằng cách chỉ bao gồm các glyph được sử dụng trong tài liệu, kích thước tệp PDF sẽ giảm so với việc nhúng phông chữ đầy đủ.

Giữ nguyên hình thức của tài liệu: Các tập hợp con phông chữ có trong tệp PDF giúp tái tạo hình thức của tài liệu chỉ bằng các ký tự được sử dụng thực sự.

Khả năng tương thích với các hạn chế của Giấy phép: Việc nhúng các tập hợp con phông chữ có thể được ưu tiên trong trường hợp phông chữ đầy đủ không thể được nhúng hợp pháp do các hạn chế về cấp phép.
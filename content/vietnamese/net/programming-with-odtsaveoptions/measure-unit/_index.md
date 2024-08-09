---
title: Đơn vị đo
linktitle: Đơn vị đo
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách định cấu hình tính năng đơn vị đo lường trong Aspose.Words for .NET để duy trì định dạng tài liệu trong quá trình chuyển đổi ODT.
type: docs
weight: 10
url: /vi/net/programming-with-odtsaveoptions/measure-unit/
---
## Giới thiệu

Bạn đã bao giờ phải chuyển đổi tài liệu Word của mình sang các định dạng khác nhau nhưng cần một đơn vị đo lường cụ thể cho bố cục của mình chưa? Cho dù bạn đang xử lý inch, cm hay điểm, việc đảm bảo tài liệu của bạn duy trì tính toàn vẹn trong quá trình chuyển đổi là rất quan trọng. Trong hướng dẫn này, chúng ta sẽ hướng dẫn cách định cấu hình tính năng đơn vị đo lường trong Aspose.Words cho .NET. Tính năng mạnh mẽ này đảm bảo rằng định dạng tài liệu của bạn được giữ nguyên chính xác như bạn cần khi chuyển đổi sang định dạng ODT (Văn bản tài liệu mở).

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, bạn cần bắt đầu một số điều sau:

1. Aspose.Words cho .NET: Đảm bảo bạn đã cài đặt phiên bản Aspose.Words cho .NET mới nhất. Nếu bạn chưa có nó, bạn có thể tải xuống từ[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Một IDE như Visual Studio để viết và thực thi mã C# của bạn.
3. Kiến thức cơ bản về C#: Hiểu những kiến thức cơ bản về C# sẽ giúp bạn làm theo hướng dẫn.
4. Tài liệu Word: Chuẩn bị sẵn tài liệu Word mẫu mà bạn có thể sử dụng để chuyển đổi.

## Nhập không gian tên

Trước khi bắt đầu viết mã, hãy đảm bảo rằng chúng ta đã nhập các không gian tên cần thiết. Thêm các lệnh sử dụng này vào đầu tệp mã của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Đầu tiên, bạn cần xác định đường dẫn đến thư mục tài liệu của mình. Đây là nơi chứa tài liệu Word của bạn và nơi lưu tệp đã chuyển đổi.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến thư mục của bạn. Điều này đảm bảo mã của bạn biết nơi tìm tài liệu Word của bạn.

## Bước 2: Tải tài liệu Word

 Tiếp theo, bạn cần tải tài liệu Word mà bạn muốn chuyển đổi. Việc này được thực hiện bằng cách sử dụng`Document` lớp từ Aspose.Words.

```csharp
// Tải tài liệu Word
Document doc = new Document(dataDir + "Document.docx");
```

Đảm bảo tài liệu Word của bạn, có tên là "Document.docx", có trong thư mục được chỉ định.

## Bước 3: Cấu hình đơn vị đo lường

 Bây giờ, hãy định cấu hình đơn vị đo cho chuyển đổi ODT. Đây là nơi phép thuật xảy ra. Chúng tôi sẽ thiết lập`OdtSaveOptions` dùng inch làm đơn vị đo.

```csharp
// Cấu hình các tùy chọn dự phòng với tính năng “Đơn vị đo lường”
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 Trong ví dụ này, chúng ta đặt đơn vị đo là inch. Ngoài ra bạn cũng có thể lựa chọn các đơn vị khác như`OdtSaveMeasureUnit.Centimeters` hoặc`OdtSaveMeasureUnit.Points` tùy thuộc vào yêu cầu của bạn.

## Bước 4: Chuyển đổi tài liệu sang ODT

 Cuối cùng, chúng ta sẽ chuyển đổi tài liệu Word sang định dạng ODT bằng cách sử dụng cấu hình`OdtSaveOptions`.

```csharp
// Chuyển đổi tài liệu sang ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Dòng mã này lưu tài liệu đã chuyển đổi vào thư mục được chỉ định với đơn vị đo lường mới được áp dụng.

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn có thể dễ dàng định cấu hình tính năng đơn vị đo lường trong Aspose.Words cho .NET để đảm bảo bố cục tài liệu của bạn được giữ nguyên trong quá trình chuyển đổi. Cho dù bạn đang làm việc với inch, cm hay điểm, hướng dẫn này đã chỉ cho bạn cách kiểm soát định dạng tài liệu của mình một cách dễ dàng.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để làm việc với các tài liệu Word theo chương trình. Nó cho phép các nhà phát triển tạo, sửa đổi, chuyển đổi và xử lý tài liệu Word mà không cần đến Microsoft Word.

### Tôi có thể sử dụng đơn vị đo khác ngoài inch không?
 Có, Aspose.Words for .NET hỗ trợ các đơn vị đo lường khác như centimet và điểm. Bạn có thể chỉ định đơn vị mong muốn bằng cách sử dụng`OdtSaveMeasureUnit` sự liệt kê.

### Có bản dùng thử miễn phí dành cho Aspose.Words cho .NET không?
 Có, bạn có thể tải xuống bản dùng thử miễn phí Aspose.Words cho .NET từ[đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu về Aspose.Words cho .NET ở đâu?
 Bạn có thể truy cập tài liệu toàn diện về Aspose.Words for .NET tại[liên kết này](https://reference.aspose.com/words/net/).

### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Words cho .NET?
 Để được hỗ trợ, bạn có thể truy cập diễn đàn Aspose.Words tại[liên kết này](https://forum.aspose.com/c/words/8).

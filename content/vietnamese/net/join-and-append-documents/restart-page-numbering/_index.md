---
title: Khởi động lại đánh số trang
linktitle: Khởi động lại đánh số trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách bắt đầu lại việc đánh số trang trong khi nối và nối thêm tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/restart-page-numbering/
---
## Giới thiệu

Bạn đã bao giờ gặp khó khăn trong việc tạo một tài liệu tinh tế với các phần riêng biệt, mỗi phần bắt đầu bằng trang số 1 chưa? Hãy tưởng tượng một báo cáo trong đó các chương bắt đầu lại từ đầu hoặc một đề xuất dài với các phần riêng biệt dành cho phần tóm tắt và phụ lục chi tiết. Aspose.Words for .NET, một thư viện xử lý tài liệu mạnh mẽ, cho phép bạn đạt được điều này một cách khéo léo. Hướng dẫn toàn diện này sẽ tiết lộ bí quyết bắt đầu lại việc đánh số trang, trang bị cho bạn cách tạo tài liệu trông chuyên nghiệp một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi bắt đầu cuộc hành trình này, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET: Tải xuống thư viện từ trang web chính thức[Liên kết tải xuống](https://releases.aspose.com/words/net/) . Bạn có thể khám phá bản dùng thử miễn phí[Link dùng thử miễn phí](https://releases.aspose.com/) hoặc mua giấy phép[Mua liên kết](https://purchase.aspose.com/buy) dựa trên nhu cầu của bạn.
2. Môi trường phát triển AC#: Visual Studio hoặc bất kỳ môi trường nào hỗ trợ phát triển .NET sẽ hoạt động hoàn hảo.
3. Tài liệu mẫu: Xác định vị trí tài liệu Word mà bạn muốn thử nghiệm.

## Nhập các không gian tên thiết yếu

Để tương tác với các đối tượng và chức năng của Aspose.Words, chúng ta cần nhập các không gian tên cần thiết. Đây là cách thực hiện:

```csharp
using Aspose.Words;
using Aspose.Words.Settings;
```

 Đoạn mã này nhập`Aspose.Words` không gian tên, cung cấp quyền truy cập vào các lớp thao tác tài liệu cốt lõi. Ngoài ra, chúng tôi nhập khẩu`Aspose.Words.Settings` không gian tên, cung cấp các tùy chọn để tùy chỉnh hành vi tài liệu.


Bây giờ, hãy đi sâu vào các bước thực tế liên quan đến việc bắt đầu lại việc đánh số trang trong tài liệu của bạn:

## Bước 1: Tải tài liệu nguồn và đích:

 Xác định một biến chuỗi`dataDir` để lưu trữ đường dẫn đến thư mục tài liệu của bạn. Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng vị trí thực tế.

 Tạo hai`Document` các đối tượng sử dụng`Aspose.Words.Document`người xây dựng. Cái đầu tiên (`srcDoc`) sẽ giữ tài liệu nguồn chứa nội dung được thêm vào. Thứ hai (`dstDoc`) đại diện cho tài liệu đích nơi chúng tôi sẽ tích hợp nội dung nguồn với việc đánh số trang được khởi động lại.

```csharp
string dataDir = @"C:\MyDocuments\"; // Thay thế bằng thư mục thực tế của bạn
Document srcDoc = new Document(dataDir + "source.docx");
Document dstDoc = new Document(dataDir + "destination.docx");
```

## Bước 2: Thiết lập ngắt phần:

 Truy cập`FirstSection` thuộc tính của tài liệu nguồn (`srcDoc`) để thao tác phần ban đầu. Phần này sẽ được đánh số trang lại.

 Sử dụng`PageSetup` thuộc tính của phần để định cấu hình hành vi bố cục của phần đó.

 Đặt`SectionStart` tài sản của`PageSetup` ĐẾN`SectionStart.NewPage`. Điều này đảm bảo một trang mới được tạo trước khi nội dung nguồn được thêm vào tài liệu đích.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Bước 3: Kích hoạt khởi động lại đánh số trang:

 Trong cùng một`PageSetup` đối tượng của phần đầu tiên của tài liệu nguồn, hãy đặt`RestartPageNumbering`tài sản để`true`. Bước quan trọng này hướng dẫn Aspose.Words bắt đầu đánh số trang mới cho nội dung được nối thêm.

```csharp
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Bước 4: Bổ sung tài liệu nguồn:

Bây giờ tài liệu nguồn đã được chuẩn bị với cấu hình đánh số và ngắt trang mong muốn, đã đến lúc tích hợp nó vào tài liệu đích.

 Sử dụng`AppendDocument` phương thức của tài liệu đích (`dstDoc`) để thêm liền mạch nội dung nguồn.

Truyền tài liệu nguồn (`srcDoc` ) và một`ImportFormatMode.KeepSourceFormatting` lập luận cho phương pháp này. Đối số này giữ nguyên định dạng ban đầu của tài liệu nguồn khi được thêm vào.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 5: Lưu tài liệu cuối cùng:

 Cuối cùng, hãy sử dụng`Save` phương thức của tài liệu đích (`dstDoc`) để lưu trữ tài liệu kết hợp với việc đánh số trang được khởi động lại. Chỉ định tên tệp và vị trí phù hợp cho tài liệu đã lưu.

```csharp
dstDoc.Save(dataDir + "final_document.docx");
```

## Phần kết luận

Tóm lại, việc nắm vững các ngắt trang và đánh số trong Aspose.Words for .NET cho phép bạn tạo các tài liệu có cấu trúc tốt và bóng bẩy. Bằng cách triển khai các kỹ thuật được nêu trong hướng dẫn này, bạn có thể tích hợp liền mạch nội dung với việc đánh số trang được khởi động lại, đảm bảo bản trình bày chuyên nghiệp và thân thiện với người đọc. Hãy nhớ rằng, Aspose.Words cung cấp vô số tính năng bổ sung để thao tác tài liệu.

## Câu hỏi thường gặp

### Tôi có thể bắt đầu lại việc đánh số trang ở giữa một phần không?

 Thật không may, Aspose.Words for .NET không hỗ trợ trực tiếp việc khởi động lại việc đánh số trang trong một phần. Tuy nhiên, bạn có thể đạt được hiệu ứng tương tự bằng cách tạo một phần mới tại điểm mong muốn và cài đặt`RestartPageNumbering` ĐẾN`true` cho phần đó.

### Làm cách nào để tùy chỉnh số trang bắt đầu sau khi khởi động lại?

 Mặc dù mã được cung cấp bắt đầu đánh số từ 1 nhưng bạn có thể tùy chỉnh mã đó. Sử dụng`PageNumber` tài sản của`HeaderFooter` đối tượng trong phần mới. Đặt thuộc tính này cho phép bạn xác định số trang bắt đầu.

### Điều gì xảy ra với số trang hiện có trong tài liệu nguồn?

Số trang hiện có trong tài liệu nguồn vẫn không bị ảnh hưởng. Chỉ nội dung được nối thêm trong tài liệu đích mới được đánh số lại.

### Tôi có thể áp dụng các định dạng đánh số khác nhau (ví dụ: chữ số La Mã) không?

 Tuyệt đối! Aspose.Words cung cấp khả năng kiểm soát rộng rãi đối với các định dạng đánh số trang. Khám phá`NumberStyle` tài sản của`HeaderFooter` đối tượng để chọn từ nhiều kiểu đánh số khác nhau như chữ số La Mã, chữ cái hoặc định dạng tùy chỉnh.

### Tôi có thể tìm thêm nguồn lực hoặc hỗ trợ ở đâu?

 Aspose cung cấp một cổng thông tin tài liệu toàn diện[Liên kết tài liệu](https://reference.aspose.com/words/net/) đi sâu hơn vào các chức năng đánh số trang và các tính năng khác của Aspose.Words. Ngoài ra, diễn đàn hoạt động của họ[Liên kết hỗ trợ](https://forum.aspose.com/c/words/8) là một nền tảng tuyệt vời để kết nối với cộng đồng nhà phát triển và tìm kiếm sự trợ giúp khi giải quyết những thách thức cụ thể.
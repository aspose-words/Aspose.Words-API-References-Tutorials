---
title: Chèn trường TOA mà không cần Trình tạo tài liệu
linktitle: Chèn trường TOA mà không cần Trình tạo tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn trường TOA mà không cần sử dụng trình tạo tài liệu trong Aspose.Words cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để quản lý hiệu quả các trích dẫn pháp lý.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-toafield-without-document-builder/
---
## Giới thiệu

Tạo trường Bảng quyền (TOA) trong tài liệu Word có thể giống như ghép một câu đố phức tạp lại với nhau. Tuy nhiên, với sự trợ giúp của Aspose.Words cho .NET, quá trình này trở nên suôn sẻ và đơn giản. Trong bài viết này, chúng tôi sẽ hướng dẫn bạn các bước để chèn trường TOA mà không cần sử dụng trình tạo tài liệu, giúp bạn dễ dàng quản lý các trích dẫn và tài liệu tham khảo pháp lý trong tài liệu Word của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đề cập đến những điều cần thiết mà bạn cần:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt phiên bản mới nhất. Bạn có thể tải nó xuống từ[trang web giả định](https://releases.aspose.com/words/net/).
- Môi trường phát triển: IDE tương thích .NET như Visual Studio.
- Kiến thức C# cơ bản: Hiểu cú pháp và khái niệm C# cơ bản sẽ hữu ích.
- Tài liệu Word mẫu: Tạo hoặc chuẩn bị sẵn tài liệu mẫu ở nơi bạn muốn chèn trường TOA.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các vùng tên cần thiết từ thư viện Aspose.Words. Thiết lập này đảm bảo rằng bạn có quyền truy cập vào tất cả các lớp và phương thức cần thiết để thao tác tài liệu.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Hãy chia nhỏ quy trình thành các bước đơn giản, dễ thực hiện. Chúng tôi sẽ hướng dẫn bạn qua từng giai đoạn, giải thích chức năng của từng đoạn mã và cách nó góp phần tạo ra trường TOA.

## Bước 1: Khởi tạo tài liệu

 Đầu tiên, bạn cần tạo một thể hiện của`Document` lớp học. Đối tượng này đại diện cho tài liệu Word bạn đang làm việc.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Mã này khởi tạo một tài liệu Word mới. Bạn có thể coi việc này giống như việc tạo một khung vẽ trống để bạn thêm nội dung của mình vào đó.

## Bước 2: Tạo và định cấu hình trường TA

Tiếp theo, chúng tôi sẽ thêm trường TA (Bảng quyền hạn). Trường này đánh dấu các mục sẽ xuất hiện trong TOA.

```csharp
Paragraph para = new Paragraph(doc);

// Chúng tôi muốn chèn các trường TA và TOA như thế này:
// { TA \c 1 \l "Giá trị 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Đây là một sự cố:
- Paragraph para = new Paragraph(doc);: Tạo một đoạn văn mới trong tài liệu.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEEntry, false);: Thêm trường TA vào đoạn văn. Các`FieldType.FieldTOAEntry` chỉ định rằng đây là trường mục nhập TOA.
- fieldTA.EntryCategory = "1";: Đặt danh mục mục nhập. Điều này rất hữu ích cho việc phân loại các loại mục khác nhau.
- fieldTA.LongCites = "Value 0";: Chỉ định văn bản trích dẫn dài. Đây là văn bản sẽ xuất hiện trong TOA.
- doc.FirstSection.Body.AppendChild(para);: Nối đoạn văn có trường TA vào nội dung tài liệu.

## Bước 3: Thêm trường TOA

Bây giờ, chúng ta sẽ chèn trường TOA thực tế để tổng hợp tất cả các mục TA vào một bảng.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

Ở bước này:
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Thêm trường TOA vào đoạn văn.
- fieldToa.EntryCategory = "1";: Lọc các mục để chỉ bao gồm những mục được đánh dấu bằng danh mục "1".

## Bước 4: Cập nhật trường TOA

Sau khi chèn trường TOA, bạn cần cập nhật nó để đảm bảo nó phản ánh các mục nhập mới nhất.

```csharp
fieldToa.Update();
```

Lệnh này làm mới trường TOA, đảm bảo rằng tất cả các mục được đánh dấu đều được hiển thị chính xác trong bảng.

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu của bạn với trường TOA mới được thêm vào.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Dòng mã này lưu tài liệu vào thư mục được chỉ định. Đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi bạn muốn lưu tệp của mình.

## Phần kết luận

Và bạn có nó rồi đấy! Bạn đã thêm thành công trường TOA vào tài liệu Word mà không cần sử dụng trình tạo tài liệu. Bằng cách làm theo các bước này, bạn có thể quản lý trích dẫn một cách hiệu quả và tạo các bảng thẩm quyền toàn diện trong các tài liệu pháp lý của mình. Aspose.Words for .NET giúp quá trình này diễn ra suôn sẻ và hiệu quả, cung cấp cho bạn các công cụ để xử lý các tác vụ tài liệu phức tạp một cách dễ dàng.

## Câu hỏi thường gặp

### Tôi có thể thêm nhiều trường TA với các danh mục khác nhau không?
 Có, bạn có thể thêm nhiều trường TA với các danh mục khác nhau bằng cách đặt`EntryCategory`tài sản tương ứng.

### Làm cách nào để tùy chỉnh giao diện của TOA?
Bạn có thể tùy chỉnh giao diện của TOA bằng cách sửa đổi các thuộc tính của trường TOA, chẳng hạn như định dạng mục nhập và nhãn danh mục.

### Có thể cập nhật trường TOA tự động không?
 Mặc dù bạn có thể cập nhật thủ công trường TOA bằng cách sử dụng`Update` phương pháp này, Aspose.Words hiện không hỗ trợ cập nhật tự động khi thay đổi tài liệu.

### Tôi có thể thêm các trường TA theo chương trình vào các phần cụ thể của tài liệu không?
Có, bạn có thể thêm trường TA tại các vị trí cụ thể bằng cách chèn chúng vào các đoạn văn hoặc phần mong muốn.

### Làm cách nào để xử lý nhiều trường TOA trong một tài liệu?
 Bạn có thể quản lý nhiều trường TOA bằng cách chỉ định các trường khác nhau`EntryCategory` giá trị và đảm bảo mỗi trường TOA lọc các mục nhập dựa trên danh mục của nó.
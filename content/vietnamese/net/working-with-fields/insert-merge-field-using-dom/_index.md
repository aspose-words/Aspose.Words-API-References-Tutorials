---
title: Chèn trường hợp nhất bằng DOM
linktitle: Chèn trường hợp nhất bằng DOM
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn và định cấu hình các trường hợp nhất trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước toàn diện này.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-merge-field-using-dom/
---
## Giới thiệu

Nếu bạn đang làm việc với việc xử lý tài liệu trong .NET, có thể bạn đã gặp Aspose.Words. Thư viện mạnh mẽ này cung cấp nhiều tính năng để thao tác tài liệu Word theo chương trình. Trong hướng dẫn này, chúng ta sẽ tập trung vào một tính năng cụ thể: chèn trường hợp nhất bằng Mô hình đối tượng tài liệu (DOM) trong Aspose.Words cho .NET. Hướng dẫn này sẽ hướng dẫn bạn từng bước, từ thiết lập môi trường đến chèn và cập nhật trường hợp nhất trong tài liệu Word.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có mọi thứ bạn cần để làm theo hướng dẫn này.

1. Kiến thức cơ bản về C#: Bạn nên thành thạo lập trình C#.
2. Đã cài đặt Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio hoặc bất kỳ C# IDE nào khác trên máy của mình.
3.  Aspose.Words for .NET: Tải xuống và cài đặt phiên bản mới nhất của Aspose.Words cho .NET từ[phát hành](https://releases.aspose.com/words/net/).
4.  Giấy phép hợp lệ: Nếu bạn không có giấy phép, bạn có thể nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.

## Bước 1: Thiết lập dự án của bạn

Trước tiên, hãy thiết lập một dự án mới trong Visual Studio.

1. Mở Visual Studio.
2. Tạo một dự án mới: Đi tới Tệp > Mới > Dự án. Chọn ứng dụng bảng điều khiển C#.
3. Đặt tên cho dự án của bạn: Đặt cho dự án của bạn một cái tên có ý nghĩa và nhấp vào Tạo.

## Bước 2: Cài đặt Aspose.Words

Để sử dụng Aspose.Words, bạn cần thêm nó vào dự án của mình. Điều này có thể được thực hiện thông qua Trình quản lý gói NuGet.

1. Mở Trình quản lý gói NuGet: Nhấp chuột phải vào dự án của bạn trong Solution Explorer, sau đó chọn Quản lý gói NuGet.
2. Tìm kiếm Aspose.Words: Trong Trình quản lý gói NuGet, tìm kiếm "Aspose.Words".
3. Cài đặt gói: Nhấp vào Cài đặt để thêm Aspose.Words vào dự án của bạn.

## Bước 3: Nhập không gian tên

Để bắt đầu sử dụng Aspose.Words, bạn cần nhập các không gian tên cần thiết vào dự án của mình. Đây là cách bạn có thể làm điều đó:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## Bước 4: Khởi tạo tài liệu của bạn

Bây giờ mọi thứ đã được thiết lập, hãy tạo một tài liệu Word mới và khởi tạo DocumentBuilder.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 5: Di chuyển con trỏ đến đoạn cụ thể

Tiếp theo, chúng ta cần di chuyển con trỏ đến một đoạn cụ thể trong tài liệu mà chúng ta muốn chèn trường hợp nhất.

```csharp
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);
builder.MoveTo(para);
```

## Bước 6: Chèn trường hợp nhất

 Việc chèn một trường hợp nhất rất đơn giản. Chúng tôi sẽ sử dụng`InsertField` phương pháp của`DocumentBuilder` lớp học.

```csharp
// Chèn trường hợp nhất trường.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## Bước 7: Định cấu hình trường hợp nhất

Sau khi chèn trường hợp nhất, bạn có thể đặt các thuộc tính khác nhau để định cấu hình trường đó theo nhu cầu của mình.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## Bước 8: Cập nhật và lưu tài liệu

Cuối cùng, cập nhật trường này để đảm bảo tất cả cài đặt được áp dụng và lưu tài liệu.

```csharp
// Cập nhật trường.
field.Update();

// Lưu tài liệu.
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## Phần kết luận

Bằng cách làm theo các bước này, bạn có thể dễ dàng chèn và định cấu hình các trường hợp nhất trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn này bao gồm các bước thiết yếu từ việc thiết lập môi trường của bạn đến việc lưu tài liệu cuối cùng. Với Aspose.Words, bạn có thể tự động hóa các tác vụ xử lý tài liệu phức tạp, giúp ứng dụng .NET của bạn mạnh mẽ và hiệu quả hơn.

## Câu hỏi thường gặp

###  Trường hợp nhất là gì?
Trường hợp nhất là phần giữ chỗ trong tài liệu có thể được thay thế động bằng dữ liệu từ nguồn dữ liệu, chẳng hạn như cơ sở dữ liệu hoặc tệp CSV.

###  Tôi có thể sử dụng Aspose.Words miễn phí không?
 Aspose.Words cung cấp bản dùng thử miễn phí mà bạn có thể tải xuống[đây](https://releases.aspose.com/). Để sử dụng lâu dài, bạn sẽ cần phải mua giấy phép.

###  Làm cách nào để có được giấy phép tạm thời cho Aspose.Words?
 Bạn có thể lấy giấy phép tạm thời từ trang web Aspose[đây](https://purchase.aspose.com/temporary-license/).

### Phiên bản .NET nào được Aspose.Words hỗ trợ?
Aspose.Words hỗ trợ nhiều phiên bản .NET, bao gồm .NET Framework, .NET Core và .NET Standard.

###  Tôi có thể tìm tài liệu API cho Aspose.Words ở đâu?
 Tài liệu API có sẵn[đây](https://reference.aspose.com/words/net/).
---
title: Hợp nhất theo chiều ngang
linktitle: Hợp nhất theo chiều ngang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hợp nhất các ô theo chiều ngang trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn chi tiết từng bước này.
type: docs
weight: 10
url: /vi/net/programming-with-tables/horizontal-merge/
---
## Giới thiệu

Này! Bạn đã sẵn sàng đi sâu vào thế giới Aspose.Words dành cho .NET chưa? Hôm nay, chúng ta sẽ giải quyết một tính năng cực kỳ hữu ích: hợp nhất theo chiều ngang trong bảng. Điều này nghe có vẻ hơi kỹ thuật nhưng đừng lo lắng, tôi sẽ hỗ trợ bạn. Đến cuối hướng dẫn này, bạn sẽ thành thạo trong việc hợp nhất các ô trong tài liệu Word theo chương trình. Vì vậy, hãy xắn tay áo lên và bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào vấn đề chi tiết, có một số điều bạn cần chuẩn bị sẵn:

1. Aspose.Words for .NET Library: Nếu bạn chưa có, hãy tải xuống thư viện Aspose.Words for .NET. Bạn có thể lấy nó[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển phù hợp, chẳng hạn như Visual Studio.
3. Kiến thức cơ bản về C#: Hiểu biết cơ bản về lập trình C# sẽ có ích.

Khi bạn đã sắp xếp xong những thứ này, bạn đã sẵn sàng để bắt đầu!

## Nhập không gian tên

Trước khi đi sâu vào mã, hãy đảm bảo rằng chúng ta đã nhập các không gian tên cần thiết. Trong dự án C# của bạn, hãy đảm bảo bao gồm:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Được rồi, hãy chia nhỏ quy trình hợp nhất các ô bảng theo chiều ngang trong tài liệu Word bằng Aspose.Words cho .NET.

## Bước 1: Thiết lập tài liệu của bạn

 Trước tiên, chúng ta cần tạo một tài liệu Word mới và khởi tạo`DocumentBuilder`:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Đoạn mã này thiết lập một tài liệu mới và chuẩn bị`DocumentBuilder` hành động.

## Bước 2: Chèn ô đầu tiên

Tiếp theo, chúng ta bắt đầu bằng cách chèn ô đầu tiên và đánh dấu nó để hợp nhất theo chiều ngang:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 Ở đây, chúng ta chèn một ô mới và đặt nó`HorizontalMerge`tài sản để`CellMerge.First`, cho biết ô này là điểm bắt đầu của chuỗi ô được hợp nhất.

## Bước 3: Chèn ô đã hợp nhất

Bây giờ, chúng ta chèn ô sẽ được hợp nhất với ô trước đó:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 Ô này được đặt để hợp nhất với ô trước đó bằng cách sử dụng`CellMerge.Previous` . Lưu ý cách chúng tôi kết thúc hàng với`builder.EndRow()`.

## Bước 4: Chèn các ô chưa được hợp nhất

Để minh họa sự khác biệt, hãy chèn một vài ô chưa được hợp nhất:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

Ở đây, chúng tôi chèn hai ô không có sự hợp nhất theo chiều ngang. Điều này cho thấy các ô hoạt động như thế nào khi chúng không phải là một phần của chuỗi đã hợp nhất.

## Bước 5: Hoàn thiện bảng

Cuối cùng, chúng ta kết thúc bảng và lưu tài liệu:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

Đoạn mã này hoàn thành bảng và lưu tài liệu vào thư mục được chỉ định.

## Phần kết luận

Và bạn có nó rồi đấy! Bạn vừa nắm vững nghệ thuật hợp nhất các ô theo chiều ngang trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước này, bạn có thể tạo các cấu trúc bảng phức tạp một cách dễ dàng. Hãy tiếp tục thử nghiệm và khám phá các khả năng của Aspose.Words để làm cho tài liệu của bạn trở nên năng động và linh hoạt như bạn cần. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và thao tác các tài liệu Word theo chương trình trong các ứng dụng .NET.

### Tôi có thể hợp nhất các ô theo chiều dọc với Aspose.Words cho .NET không?
 Có, bạn cũng có thể hợp nhất các ô theo chiều dọc bằng cách sử dụng`CellFormat.VerticalMerge` tài sản.

### Aspose.Words cho .NET có được sử dụng miễn phí không?
 Aspose.Words for .NET cung cấp bản dùng thử miễn phí nhưng để có đầy đủ chức năng, bạn sẽ cần phải mua giấy phép. Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Làm cách nào tôi có thể tìm hiểu thêm về Aspose.Words cho .NET?
 Bạn có thể khám phá các tài liệu chi tiết[đây](https://reference.aspose.com/words/net/).

### Tôi có thể nhận hỗ trợ cho Aspose.Words cho .NET ở đâu?
 Nếu có bất kỳ thắc mắc hoặc vấn đề nào, bạn có thể truy cập diễn đàn hỗ trợ Aspose[đây](https://forum.aspose.com/c/words/8).
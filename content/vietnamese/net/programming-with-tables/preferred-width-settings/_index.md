---
title: Cài đặt chiều rộng ưa thích
linktitle: Cài đặt chiều rộng ưa thích
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo bảng với cài đặt độ rộng tuyệt đối, tương đối và tự động trong Aspose.Words cho .NET với hướng dẫn từng bước này.
type: docs
weight: 10
url: /vi/net/programming-with-tables/preferred-width-settings/
---
## Giới thiệu

Bảng là một cách mạnh mẽ để sắp xếp và trình bày thông tin trong tài liệu Word của bạn. Khi làm việc với các bảng trong Aspose.Words cho .NET, bạn có một số tùy chọn để đặt độ rộng của các ô trong bảng để đảm bảo chúng phù hợp hoàn hảo với bố cục tài liệu của bạn. Hướng dẫn này sẽ hướng dẫn bạn qua quy trình tạo bảng với cài đặt độ rộng ưa thích bằng Aspose.Words cho .NET, tập trung vào các tùy chọn định cỡ tuyệt đối, tương đối và tự động. 

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt Aspose.Words for .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/words/net/).

2. Môi trường phát triển .NET: Thiết lập môi trường phát triển .NET, chẳng hạn như Visual Studio.

3. Kiến thức cơ bản về C#: Làm quen với lập trình C# sẽ giúp bạn hiểu rõ hơn về các đoạn mã và ví dụ.

4.  Tài liệu Aspose.Words: Tham khảo[Tài liệu Aspose.Words](https://reference.aspose.com/words/net/) để biết thông tin chi tiết về API và đọc thêm.

## Nhập không gian tên

Trước khi bắt đầu viết mã, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Các không gian tên này cung cấp quyền truy cập vào các chức năng cốt lõi của đối tượng Aspose.Words và Table, cho phép bạn thao tác với các bảng tài liệu.

Hãy chia nhỏ quy trình tạo bảng với các cài đặt chiều rộng ưu tiên khác nhau thành các bước rõ ràng, dễ quản lý.

## Bước 1: Khởi tạo Document và DocumentBuilder

Tiêu đề: Tạo một tài liệu mới và DocumentBuilder

 Giải thích: Bắt đầu bằng cách tạo một tài liệu Word mới và một`DocumentBuilder` ví dụ. các`DocumentBuilder` class cung cấp một cách đơn giản để thêm nội dung vào tài liệu của bạn.

```csharp
// Xác định đường dẫn để lưu tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo một tài liệu mới.
Document doc = new Document();

// Tạo DocumentBuilder cho Tài liệu này.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tại đây, bạn chỉ định thư mục nơi tài liệu sẽ được lưu và khởi tạo`Document`Và`DocumentBuilder` đồ vật.

## Bước 2: Chèn ô bảng đầu tiên có chiều rộng tuyệt đối

Chèn ô đầu tiên vào bảng có chiều rộng cố định là 40 điểm. Điều này sẽ đảm bảo rằng ô này luôn duy trì độ rộng 40 điểm bất kể kích thước bảng.

```csharp

// Chèn một ô có kích thước tuyệt đối.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

Ở bước này, bạn bắt đầu tạo bảng và chèn một ô có chiều rộng tuyệt đối. các`PreferredWidth.FromPoints(40)` phương thức đặt chiều rộng của ô thành 40 điểm và`Shading.BackgroundPatternColor` áp dụng màu nền màu vàng nhạt.

## Bước 3: Chèn một ô có kích thước tương đối

Chèn một ô khác có chiều rộng bằng 20% tổng chiều rộng của bảng. Việc định cỡ tương đối này đảm bảo ô điều chỉnh tỷ lệ với chiều rộng của bảng.

```csharp
// Chèn một ô có kích thước tương đối (phần trăm).
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

Chiều rộng của ô này sẽ bằng 20% tổng chiều rộng của bảng, giúp bảng có thể thích ứng với các kích thước màn hình hoặc bố cục tài liệu khác nhau.

### Bước 4: Chèn một ô có kích thước tự động

Cuối cùng, chèn một ô tự động định kích thước dựa trên khoảng trống còn lại trong bảng.

```csharp
// Chèn một ô có kích thước tự động.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

 các`PreferredWidth.Auto` cài đặt cho phép ô này mở rộng hoặc co lại dựa trên khoảng trống còn lại sau khi các ô khác được chiếm. Điều này đảm bảo bố cục bàn trông cân bằng và chuyên nghiệp.

## Bước 5: Hoàn thiện và lưu tài liệu

Sau khi bạn đã chèn tất cả các ô, hãy hoàn thành bảng và lưu tài liệu vào đường dẫn đã chỉ định.

```csharp
// Lưu tài liệu.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Bước này sẽ hoàn thiện bảng và lưu tài liệu với tên tệp "WorkingWithTables.PreferredWidthSettings.docx" trong thư mục được chỉ định của bạn.

## Phần kết luận

Tạo bảng với cài đặt độ rộng ưa thích trong Aspose.Words cho .NET thật đơn giản khi bạn hiểu các tùy chọn định cỡ khác nhau có sẵn. Cho dù bạn cần độ rộng ô cố định, tương đối hay tự động, Aspose.Words cung cấp tính linh hoạt để xử lý các tình huống bố cục bảng khác nhau một cách hiệu quả. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể đảm bảo các bảng của mình có cấu trúc tốt và hấp dẫn về mặt hình ảnh trong tài liệu Word của mình.

## Câu hỏi thường gặp

### Sự khác biệt giữa độ rộng ô tuyệt đối và tương đối là gì?
Độ rộng ô tuyệt đối được cố định và không thay đổi, trong khi độ rộng tương đối điều chỉnh dựa trên tổng chiều rộng của bảng.

### Tôi có thể sử dụng tỷ lệ phần trăm âm cho chiều rộng tương đối không?
Không, tỷ lệ phần trăm âm không hợp lệ đối với độ rộng ô. Chỉ cho phép tỷ lệ phần trăm tích cực.

### Tính năng tự động định cỡ hoạt động như thế nào?
Tự động định cỡ sẽ điều chỉnh độ rộng của ô để lấp đầy mọi khoảng trống còn lại trong bảng sau khi các ô khác đã được điều chỉnh kích thước.

### Tôi có thể áp dụng các kiểu khác nhau cho các ô có cài đặt chiều rộng khác nhau không?
Có, bạn có thể áp dụng nhiều kiểu và định dạng khác nhau cho các ô bất kể cài đặt độ rộng của chúng.

### Điều gì xảy ra nếu tổng chiều rộng của bảng nhỏ hơn tổng chiều rộng của tất cả các ô?
Bảng sẽ tự động điều chỉnh độ rộng của các ô cho vừa với không gian có sẵn, điều này có thể khiến một số ô bị co lại.
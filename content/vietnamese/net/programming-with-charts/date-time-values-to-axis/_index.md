---
title: Thêm giá trị ngày giờ vào trục của biểu đồ
linktitle: Thêm giá trị ngày giờ vào trục của biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm giá trị ngày và giờ vào trục của biểu đồ bằng Aspose.Words cho .NET trong hướng dẫn từng bước toàn diện này.
type: docs
weight: 10
url: /vi/net/programming-with-charts/date-time-values-to-axis/
---
## Giới thiệu

Tạo biểu đồ trong tài liệu có thể là một cách mạnh mẽ để trực quan hóa dữ liệu. Khi xử lý dữ liệu chuỗi thời gian, việc thêm giá trị ngày và giờ vào trục của biểu đồ là rất quan trọng để làm rõ biểu đồ. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm giá trị ngày và giờ vào trục của biểu đồ bằng Aspose.Words cho .NET. Hướng dẫn từng bước này sẽ giúp bạn thiết lập môi trường, viết mã và hiểu từng phần của quy trình. Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1. Visual Studio hoặc bất kỳ .NET IDE nào: Bạn cần một môi trường phát triển để viết và chạy mã .NET của mình.
2.  Aspose.Words for .NET: Bạn nên cài đặt thư viện Aspose.Words for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/net/).
3. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn có hiểu biết cơ bản về lập trình C#.
4.  Giấy phép Aspose hợp lệ: Bạn có thể lấy giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).

## Nhập không gian tên

Để bắt đầu, hãy đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án của mình. Bước này rất quan trọng để truy cập các lớp và phương thức Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Đầu tiên, bạn cần xác định thư mục nơi tài liệu của bạn sẽ được lưu. Điều này rất quan trọng để sắp xếp các tệp của bạn và đảm bảo mã của bạn chạy chính xác.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu mới và DocumentBuilder

 Tiếp theo, tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` sự vật. Những đối tượng này sẽ giúp bạn xây dựng và thao tác với tài liệu của mình.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn biểu đồ vào tài liệu

 Bây giờ, hãy chèn biểu đồ vào tài liệu của bạn bằng cách sử dụng`DocumentBuilder` sự vật. Trong ví dụ này, chúng tôi đang sử dụng biểu đồ cột nhưng bạn cũng có thể chọn các loại khác.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Bước 4: Xóa chuỗi hiện có

Xóa mọi chuỗi hiện có trong biểu đồ để đảm bảo bạn đang bắt đầu với một bảng trống. Bước này rất cần thiết cho dữ liệu tùy chỉnh.

```csharp
chart.Series.Clear();
```

## Bước 5: Thêm giá trị ngày và giờ vào chuỗi

Thêm giá trị ngày và giờ của bạn vào chuỗi biểu đồ. Bước này liên quan đến việc tạo mảng cho ngày và giá trị tương ứng.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Bước 6: Cấu hình trục X

Đặt tỷ lệ và dấu kiểm cho trục X. Điều này đảm bảo ngày của bạn được hiển thị chính xác và ở những khoảng thời gian thích hợp.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Bước 7: Lưu tài liệu

Cuối cùng, lưu tài liệu của bạn vào thư mục được chỉ định. Bước này kết thúc quá trình và tài liệu của bạn bây giờ sẽ chứa biểu đồ có giá trị ngày và giờ trên trục X.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Phần kết luận

Thêm giá trị ngày và giờ vào trục của biểu đồ trong tài liệu là một quy trình đơn giản với Aspose.Words dành cho .NET. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể tạo các biểu đồ rõ ràng và giàu thông tin để trực quan hóa dữ liệu chuỗi thời gian một cách hiệu quả. Cho dù bạn đang chuẩn bị báo cáo, bản trình bày hay bất kỳ tài liệu nào yêu cầu trình bày dữ liệu chi tiết, Aspose.Words đều cung cấp các công cụ bạn cần để thành công.

## Câu hỏi thường gặp

### Tôi có thể sử dụng các loại biểu đồ khác với Aspose.Words cho .NET không?

Có, Aspose.Words hỗ trợ nhiều loại biểu đồ khác nhau, bao gồm đường, thanh, hình tròn, v.v.

### Làm cách nào tôi có thể tùy chỉnh giao diện biểu đồ của mình?

Bạn có thể tùy chỉnh giao diện bằng cách truy cập các thuộc tính của biểu đồ và cài đặt kiểu, màu sắc, v.v.

### Có thể thêm nhiều chuỗi vào biểu đồ không?

 Tuyệt đối! Bạn có thể thêm nhiều chuỗi vào biểu đồ của mình bằng cách gọi`Series.Add` phương pháp nhiều lần với dữ liệu khác nhau.

### Nếu tôi cần cập nhật dữ liệu biểu đồ một cách linh hoạt thì sao?

Bạn có thể cập nhật dữ liệu biểu đồ một cách linh hoạt bằng cách thao tác các thuộc tính chuỗi và trục theo chương trình dựa trên yêu cầu của bạn.

### Tôi có thể tìm tài liệu chi tiết hơn về Aspose.Words cho .NET ở đâu?

 Bạn có thể tìm tài liệu chi tiết hơn[đây](https://reference.aspose.com/words/net/).
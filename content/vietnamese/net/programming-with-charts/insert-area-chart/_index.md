---
title: Chèn biểu đồ vùng vào tài liệu Word
linktitle: Chèn biểu đồ vùng vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn biểu đồ vùng vào tài liệu bằng Aspose.Words cho .NET. Thêm dữ liệu chuỗi và lưu tài liệu cùng với biểu đồ.
type: docs
weight: 10
url: /vi/net/programming-with-charts/insert-area-chart/
---
## Giới thiệu

Chào mừng bạn đến với hướng dẫn từng bước này về cách chèn biểu đồ vùng vào tài liệu Word bằng Aspose.Words cho .NET. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay chỉ mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn mọi thứ bạn cần biết để tạo biểu đồ vùng đầy thông tin và ấn tượng trong tài liệu Word của bạn. Chúng tôi sẽ đề cập đến các điều kiện tiên quyết, chỉ cho bạn cách nhập các không gian tên cần thiết và hướng dẫn bạn qua từng bước của quy trình bằng các hướng dẫn rõ ràng, dễ thực hiện.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào, hãy đảm bảo bạn có mọi thứ bạn cần để bắt đầu:

1.  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt Aspose.Words for .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/words/net/).
2. .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework trên máy của mình.
3. IDE: Môi trường phát triển tích hợp (IDE) như Visual Studio để viết và thực thi mã của bạn.
4. Kiến thức cơ bản về C#: Hiểu biết cơ bản về lập trình C# sẽ rất hữu ích.

Sau khi đã có những điều kiện tiên quyết này, bạn đã sẵn sàng bắt đầu tạo các biểu đồ vùng đẹp mắt trong tài liệu Word của mình.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Các không gian tên này cung cấp các lớp và phương thức cần thiết để làm việc với tài liệu Word và biểu đồ trong Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Bây giờ chúng ta đã nhập các không gian tên thiết yếu, hãy chuyển sang tạo tài liệu và chèn biểu đồ vùng từng bước.

## Bước 1: Tạo tài liệu Word mới

Hãy bắt đầu bằng cách tạo một tài liệu Word mới. Đây sẽ là cơ sở nơi chúng ta sẽ chèn biểu đồ vùng của mình.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Ở bước này, chúng ta khởi tạo một`Document` đối tượng đại diện cho tài liệu Word của chúng tôi.

## Bước 2: Sử dụng DocumentBuilder để chèn biểu đồ

 Tiếp theo, chúng ta sẽ sử dụng`DocumentBuilder` class để chèn biểu đồ vùng vào tài liệu của chúng tôi.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Ở đây, chúng tôi tạo ra một`DocumentBuilder` đối tượng và sử dụng nó để chèn biểu đồ vùng có kích thước cụ thể (432x252) vào tài liệu của chúng tôi.

## Bước 3: Truy cập đối tượng biểu đồ

 Sau khi chèn biểu đồ, chúng ta cần truy cập vào`Chart` đối tượng để tùy chỉnh biểu đồ khu vực của chúng tôi.

```csharp
Chart chart = shape.Chart;
```

 Dòng mã này truy xuất`Chart` đối tượng từ hình dạng chúng ta vừa chèn.

## Bước 4: Thêm dữ liệu chuỗi vào biểu đồ

Bây giờ là lúc thêm một số dữ liệu vào biểu đồ của chúng ta. Chúng tôi sẽ thêm một chuỗi có ngày tháng và giá trị tương ứng.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

Trong bước này, chúng tôi thêm một chuỗi có tên "Aspose Series 1" với một tập hợp ngày và giá trị tương ứng.

## Bước 5: Lưu tài liệu

Cuối cùng, chúng ta sẽ lưu tài liệu của mình với biểu đồ vùng được chèn.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Dòng mã này lưu tài liệu vào thư mục được chỉ định với tên tệp đã cho.

## Phần kết luận

Chúc mừng! Bạn đã chèn thành công biểu đồ vùng vào tài liệu Word bằng Aspose.Words for .NET. Hướng dẫn này đã hướng dẫn bạn qua từng bước, từ thiết lập môi trường cho đến lưu tài liệu cuối cùng. Với Aspose.Words cho .NET, bạn có thể tạo nhiều loại biểu đồ và các thành phần phức tạp khác trong tài liệu Word của mình, làm cho báo cáo và bản trình bày của bạn trở nên năng động và giàu thông tin hơn.

## Câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Words cho .NET với các ngôn ngữ .NET khác không?
Có, Aspose.Words for .NET hỗ trợ các ngôn ngữ .NET khác như VB.NET.

### Có thể tùy chỉnh sự xuất hiện của biểu đồ?
Tuyệt đối! Aspose.Words for .NET cung cấp các tùy chọn mở rộng để tùy chỉnh giao diện biểu đồ của bạn.

### Tôi có thể thêm nhiều biểu đồ vào một tài liệu Word không?
Có, bạn có thể chèn bao nhiêu biểu đồ tùy thích vào một tài liệu Word.

### Aspose.Words for .NET có hỗ trợ các loại biểu đồ khác không?
Có, Aspose.Words for .NET hỗ trợ nhiều loại biểu đồ khác nhau bao gồm thanh, đường, hình tròn, v.v.

### Tôi có thể lấy giấy phép tạm thời cho Aspose.Words cho .NET ở đâu?
 Bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).
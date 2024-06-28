---
title: Tùy chỉnh chuỗi biểu đồ đơn trong biểu đồ
linktitle: Tùy chỉnh chuỗi biểu đồ đơn trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tùy chỉnh chuỗi biểu đồ đơn lẻ trong biểu đồ bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/single-chart-series/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để tùy chỉnh chuỗi biểu đồ đơn lẻ trong biểu đồ. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, truy cập các chuỗi cụ thể và sửa đổi các thuộc tính của chúng.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

- Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải xuống bằng cách sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu đầu ra sẽ được lưu.

## Bước 2: Tạo một tài liệu mới và chèn biểu đồ.

 Tạo một cái mới`Document` đối tượng và một`DocumentBuilder` để xây dựng tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tiếp theo, sử dụng`InsertChart` phương pháp của`DocumentBuilder` để chèn biểu đồ đường vào tài liệu.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Truy cập và tùy chỉnh chuỗi biểu đồ

 Để sửa đổi chuỗi biểu đồ đơn lẻ, bạn cần truy cập vào`ChartSeries` các đối tượng của biểu đồ.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Bước 4: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Điều này hoàn tất việc triển khai tùy chỉnh một chuỗi biểu đồ bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho Chuỗi biểu đồ đơn sử dụng Aspose.Words for .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Bạn cũng có thể chỉ định xem đường nối các điểm trên biểu đồ có được làm mịn hay không bằng cách sử dụng các đường nối Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Chỉ định xem theo mặc định, phần tử cha có đảo ngược màu của nó hay không nếu giá trị âm.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tùy chỉnh một chuỗi biểu đồ trong biểu đồ bằng Aspose.Words for .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo tài liệu mới, chèn biểu đồ đường, truy cập chuỗi biểu đồ cụ thể và sửa đổi thuộc tính của chúng để đạt được tùy chỉnh mong muốn.

Aspose.Words for .NET cung cấp các tính năng mạnh mẽ để thao tác biểu đồ trong tài liệu Word. Bằng cách truy cập vào từng chuỗi biểu đồ riêng lẻ, bạn có thể áp dụng các sửa đổi cụ thể để tùy chỉnh giao diện và hành vi của chúng. Điều này cho phép bạn thay đổi tên chuỗi, cho phép làm mịn đường biểu đồ, tùy chỉnh điểm đánh dấu cho điểm dữ liệu, đảo ngược màu cho giá trị âm, v.v. để nâng cao khả năng trình bày trực quan cho biểu đồ của bạn.

Việc tùy chỉnh một chuỗi biểu đồ giúp bạn linh hoạt làm nổi bật dữ liệu cụ thể hoặc nhấn mạnh các xu hướng cụ thể trong biểu đồ của mình. Với Aspose.Words for .NET, bạn có thể dễ dàng truy cập và sửa đổi các thuộc tính chuỗi biểu đồ, cho phép bạn tạo các biểu đồ giàu thông tin và hấp dẫn về mặt trực quan trong tài liệu Word của mình.

### Câu hỏi thường gặp

#### Q1. Tôi có thể tùy chỉnh nhiều chuỗi biểu đồ trong một biểu đồ không?
 Có, bạn có thể tùy chỉnh nhiều chuỗi biểu đồ trong biểu đồ bằng Aspose.Words for .NET. Bằng cách truy cập vào`ChartSeries`các đối tượng trong biểu đồ, bạn có thể chọn và sửa đổi nhiều chuỗi dựa trên chỉ số hoặc tiêu chí cụ thể của chúng. Sử dụng vòng lặp hoặc các bài tập riêng lẻ để sửa đổi các thuộc tính mong muốn cho từng chuỗi biểu đồ. Bằng cách này, bạn có thể áp dụng các tùy chỉnh khác nhau cho nhiều chuỗi trong cùng một biểu đồ.

#### Q2. Làm cách nào để thay đổi tên của một chuỗi biểu đồ?
 Để thay đổi tên của chuỗi biểu đồ trong biểu đồ bằng Aspose.Words cho .NET, bạn cần truy cập vào`Name` tài sản của`ChartSeries` đối tượng và đặt nó thành tên mong muốn. Tên chuỗi thường được hiển thị trong chú giải biểu đồ hoặc nhãn dữ liệu, cung cấp nhãn mô tả cho chuỗi. Bằng cách sửa đổi tên chuỗi, bạn có thể cung cấp các tên có ý nghĩa phản ánh dữ liệu được biểu thị bằng mỗi chuỗi.

#### Q3. Làm mịn chuỗi biểu đồ là gì?
Làm mịn chuỗi biểu đồ là một kỹ thuật nâng cao hình ảnh cho phép bạn tạo một đường thẳng nối các điểm trên biểu đồ. Nó áp dụng một thuật toán làm mịn, chẳng hạn như các đường trục Catmull-Rom, để nội suy giữa các điểm dữ liệu và tạo ra một đường cong trực quan đẹp mắt. Để bật làm mịn chuỗi trong biểu đồ bằng Aspose.Words cho .NET, hãy truy cập`Smooth` tài sản của`ChartSeries` đối tượng và đặt nó thành`true`. Làm mịn có thể hữu ích để hiển thị các xu hướng hoặc mẫu trong dữ liệu có biến động không đều.

#### Q4. Làm cách nào tôi có thể tùy chỉnh điểm đánh dấu cho các điểm dữ liệu trong chuỗi biểu đồ?
 Để tùy chỉnh điểm đánh dấu cho các điểm dữ liệu trong chuỗi biểu đồ bằng Aspose.Words cho .NET, bạn cần truy cập vào`Marker` tài sản của`ChartSeries` đối tượng và sửa đổi các thuộc tính của nó như`Symbol` Và`Size`. Điểm đánh dấu là các chỉ báo trực quan được đặt trên biểu đồ để thể hiện các điểm dữ liệu riêng lẻ. Bạn có thể chọn từ nhiều ký hiệu đánh dấu tích hợp sẵn và điều chỉnh kích thước của chúng để làm nổi bật hoặc phân biệt các điểm dữ liệu cụ thể trong chuỗi.

#### Q5. Tôi có thể đảo ngược màu cho các giá trị âm trong chuỗi biểu đồ không?
 Có, bạn có thể đảo ngược màu cho các giá trị âm trong chuỗi biểu đồ bằng Aspose.Words for .NET. Bằng cách thiết lập`InvertIfNegative` tài sản của`ChartSeries` chủ đề`true`, màu sắc của các điểm dữ liệu có giá trị âm sẽ bị đảo ngược, khiến chúng khác biệt về mặt trực quan với các giá trị dương. Tính năng này có thể hữu ích khi so sánh các giá trị dương và âm trong một chuỗi biểu đồ, mang lại sự khác biệt rõ ràng giữa hai giá trị này.
---
title: Đặt tùy chọn mặc định cho nhãn dữ liệu trong biểu đồ
linktitle: Đặt tùy chọn mặc định cho nhãn dữ liệu trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt tùy chọn mặc định cho nhãn dữ liệu trong biểu đồ bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/default-options-for-data-labels/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để đặt các tùy chọn mặc định cho nhãn dữ liệu trong biểu đồ. Mã được cung cấp trình bày cách tạo biểu đồ, thêm chuỗi dữ liệu và tùy chỉnh nhãn dữ liệu bằng Aspose.Words.

## Bước 1: Thiết lập dự án

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có sẵn các yêu cầu sau:

- Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải xuống bằng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu đầu ra sẽ được lưu.

## Bước 2: Tạo một tài liệu mới và chèn biểu đồ.

 Đầu tiên chúng ta hãy tạo một cái mới`Document` đối tượng và một`DocumentBuilder` để xây dựng tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tiếp theo, chúng ta chèn biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder`. Trong ví dụ này, chúng tôi sẽ chèn biểu đồ hình tròn.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Thêm chuỗi dữ liệu vào biểu đồ

Bây giờ, hãy thêm chuỗi dữ liệu vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm ba danh mục và giá trị tương ứng của chúng.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Bước 4: Tùy chỉnh nhãn dữ liệu

 Để tùy chỉnh nhãn dữ liệu trong biểu đồ, chúng ta cần truy cập vào`ChartDataLabelCollection` đối tượng liên quan đến chuỗi.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Sau đó chúng ta có thể sửa đổi các thuộc tính khác nhau của`labels`đối tượng để đặt các tùy chọn mong muốn cho nhãn dữ liệu. Trong ví dụ này, chúng tôi sẽ bật hiển thị phần trăm và giá trị, tắt dòng dẫn đầu và đặt dấu phân cách tùy chỉnh.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Bước 5: Lưu tài liệu

 Cuối cùng, chúng ta lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Điều này hoàn tất việc triển khai cài đặt các tùy chọn mặc định cho nhãn dữ liệu trong biểu đồ bằng Aspose.Words for .NET.

### Mã nguồn ví dụ cho Tùy chọn mặc định cho nhãn dữ liệu bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách đặt các tùy chọn mặc định cho nhãn dữ liệu trong biểu đồ bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tạo biểu đồ, thêm chuỗi dữ liệu và tùy chỉnh nhãn dữ liệu để đáp ứng các yêu cầu cụ thể của mình. Aspose.Words for .NET cung cấp API mạnh mẽ để Xử lý Từ với các biểu đồ trong tài liệu Word, cho phép bạn thao tác các thành phần biểu đồ khác nhau và đạt được hình thức cũng như chức năng mong muốn.

 Bằng cách thiết lập các thuộc tính của`ChartDataLabelCollection`đối tượng được liên kết với chuỗi biểu đồ, bạn có thể kiểm soát việc hiển thị nhãn dữ liệu, bao gồm các tùy chọn như hiển thị tỷ lệ phần trăm, giá trị, dòng chỉ dẫn và dấu phân cách tùy chỉnh. Tính linh hoạt này cho phép bạn trình bày dữ liệu một cách hiệu quả và nâng cao khả năng trình bày trực quan của biểu đồ.

### Câu hỏi thường gặp

#### Q1. Aspose.Words cho .NET là gì?
Aspose.Words for .NET là thư viện cho phép các nhà phát triển tạo, thao tác và lưu tài liệu Word theo chương trình bằng các ứng dụng .NET. Nó cung cấp nhiều tính năng cho Xử lý văn bản với các thành phần tài liệu, bao gồm cả biểu đồ.

#### Q2. Làm cách nào tôi có thể cài đặt Aspose.Words cho .NET?
Bạn có thể cài đặt Aspose.Words cho .NET bằng cách tải xuống bằng cách sử dụng trình quản lý gói NuGet trong Visual Studio. Chỉ cần tìm kiếm "Apose.Words" trong trình quản lý gói NuGet và cài đặt nó vào dự án của bạn.

#### Q3. Tôi có thể tùy chỉnh các khía cạnh khác của biểu đồ bằng Aspose.Words cho .NET không?
Có, Aspose.Words for .NET cho phép bạn tùy chỉnh các khía cạnh khác nhau của biểu đồ, chẳng hạn như loại biểu đồ, nhãn trục, chú giải, vùng vẽ, v.v. Bạn có thể truy cập và sửa đổi các thuộc tính khác nhau của đối tượng biểu đồ để đạt được hình thức và hành vi mong muốn.

#### Q4. Tôi có thể lưu biểu đồ ở các định dạng khác nhau không?
 Có, Aspose.Words for .NET hỗ trợ lưu tài liệu chứa biểu đồ ở nhiều định dạng khác nhau, bao gồm DOCX, PDF, HTML, v.v. Bạn có thể chọn định dạng phù hợp dựa trên yêu cầu của mình và sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu.

#### Q5. Tôi có thể áp dụng những kỹ thuật này cho các loại biểu đồ khác không?
Có, các kỹ thuật được mô tả trong hướng dẫn này có thể được áp dụng cho các loại biểu đồ khác được Aspose.Words hỗ trợ cho .NET. Điều quan trọng là truy cập vào các đối tượng và thuộc tính có liên quan cụ thể cho loại biểu đồ mà bạn đang Xử lý Từ.
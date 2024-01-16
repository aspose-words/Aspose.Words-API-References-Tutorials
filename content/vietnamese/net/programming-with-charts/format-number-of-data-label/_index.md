---
title: Định dạng số nhãn dữ liệu trong biểu đồ
linktitle: Định dạng số nhãn dữ liệu trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách định dạng số lượng nhãn dữ liệu trong biểu đồ bằng Aspose.Words for .NET. Tùy chỉnh định dạng số cho nhãn dữ liệu một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-charts/format-number-of-data-label/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để định dạng số lượng nhãn dữ liệu trong biểu đồ. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, thêm dữ liệu chuỗi và tùy chỉnh định dạng số của nhãn dữ liệu.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

- Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải xuống bằng cách sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu đầu ra sẽ được lưu.

## Bước 2: Tạo một tài liệu mới và chèn biểu đồ

 Tạo một cái mới`Document` đối tượng và một`DocumentBuilder` để xây dựng tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tiếp theo, chèn biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder`. Trong ví dụ này, chúng tôi sẽ chèn biểu đồ dạng đường.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Bước 3: Thêm dữ liệu chuỗi vào biểu đồ

Thêm dữ liệu chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm ba danh mục và giá trị tương ứng của chúng.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Bước 4: Tùy chỉnh định dạng số của nhãn dữ liệu

 Để định dạng số lượng nhãn dữ liệu, hãy truy cập vào`DataLabels` bộ sưu tập liên quan đến bộ truyện.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Trong ví dụ này, chúng tôi đặt các định dạng số khác nhau cho mỗi nhãn dữ liệu. Nhãn dữ liệu đầu tiên được định dạng dưới dạng tiền tệ, nhãn thứ hai dưới dạng ngày và nhãn thứ ba dưới dạng phần trăm.

## Bước 5: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Điều này hoàn tất việc thực hiện định dạng số lượng nhãn dữ liệu trong biểu đồ bằng Aspose.Words for .NET.

### Mã nguồn mẫu cho Định dạng số nhãn dữ liệu bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Xóa chuỗi được tạo mặc định.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Hoặc bạn có thể đặt mã định dạng để được liên kết với ô nguồn,
	//trong trường hợp này NumberFormat sẽ được đặt lại thành chung và được kế thừa từ ô nguồn.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách định dạng số lượng nhãn dữ liệu trong biểu đồ bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo biểu đồ, thêm dữ liệu chuỗi và tùy chỉnh định dạng số của nhãn dữ liệu theo yêu cầu của mình.

 Aspose.Words for .NET cung cấp API toàn diện để Xử lý từ với các biểu đồ trong tài liệu Word, cho phép bạn thao tác các khía cạnh khác nhau của biểu đồ, bao gồm cả nhãn dữ liệu. Bằng cách truy cập vào`DataLabels` bộ sưu tập được liên kết với một chuỗi, bạn có thể tùy chỉnh định dạng số của các nhãn dữ liệu riêng lẻ.

API cho phép bạn kiểm soát việc hiển thị các giá trị, đặt các định dạng số khác nhau cho từng nhãn dữ liệu và liên kết định dạng số với một ô nguồn. Tính linh hoạt này cho phép bạn trình bày dữ liệu số trong biểu đồ với định dạng mong muốn, chẳng hạn như ký hiệu tiền tệ, định dạng ngày và giá trị phần trăm.

Bằng cách sử dụng Aspose.Words cho .NET, bạn có thể kết hợp các khả năng lập biểu đồ mạnh mẽ vào các ứng dụng .NET của mình và tạo các tài liệu có giao diện chuyên nghiệp với các biểu đồ và nhãn dữ liệu được định dạng đầy đủ.

### Câu hỏi thường gặp

#### Q1. Aspose.Words cho .NET là gì?
Aspose.Words for .NET là thư viện xử lý tài liệu giàu tính năng cho phép các nhà phát triển tạo, thao tác và lưu tài liệu Word theo chương trình trong các ứng dụng .NET. Nó cung cấp nhiều tính năng cho Xử lý văn bản với các thành phần tài liệu, bao gồm biểu đồ và nhãn dữ liệu.

#### Q2. Làm cách nào tôi có thể cài đặt Aspose.Words cho .NET?
Bạn có thể cài đặt Aspose.Words cho .NET bằng cách tải xuống bằng cách sử dụng trình quản lý gói NuGet trong Visual Studio. Chỉ cần tìm kiếm "Aspose.Words" trong trình quản lý gói NuGet và cài đặt nó vào dự án của bạn.

#### Q3. Tôi có thể định dạng các khía cạnh khác của biểu đồ bằng Aspose.Words cho .NET không?
Có, Aspose.Words for .NET cung cấp các khả năng mở rộng để định dạng các khía cạnh khác nhau của biểu đồ. Ngoài nhãn dữ liệu, bạn có thể tùy chỉnh loại biểu đồ, dữ liệu chuỗi, thuộc tính trục, chú giải, tiêu đề, vùng ô và nhiều thành phần khác của biểu đồ. API cung cấp khả năng kiểm soát chi tiết về hình thức và định dạng biểu đồ.

#### Q4. Tôi có thể áp dụng các định dạng số khác nhau cho các nhãn dữ liệu khác nhau trong cùng một chuỗi không?
Có, Aspose.Words for .NET cho phép bạn áp dụng các định dạng số khác nhau cho các nhãn dữ liệu riêng lẻ trong cùng một chuỗi. Bằng cách truy cập vào`DataLabels` bộ sưu tập được liên kết với một bộ truyện, bạn có thể đặt`FormatCode` thuộc tính của mỗi nhãn dữ liệu để chỉ định định dạng số mong muốn. Điều này cho phép bạn trình bày các giá trị số ở các định dạng khác nhau trong cùng một biểu đồ.

#### Q5. Tôi có thể sử dụng định dạng số tùy chỉnh cho nhãn dữ liệu không?
 Có, Aspose.Words for .NET hỗ trợ các định dạng số tùy chỉnh cho nhãn dữ liệu. Bạn có thể chỉ định định dạng số mong muốn bằng cách đặt`FormatCode` thuộc tính của nhãn dữ liệu sang mã định dạng tùy chỉnh. Điều này mang lại cho bạn sự linh hoạt để áp dụng nhiều định dạng số, chẳng hạn như ký hiệu tiền tệ, định dạng ngày, giá trị phần trăm, v.v.

#### Q6. Tôi có thể lưu biểu đồ với các nhãn dữ liệu được định dạng ở các định dạng khác nhau không?
Có, Aspose.Words for .NET cho phép bạn lưu tài liệu chứa biểu đồ với các nhãn dữ liệu được định dạng ở nhiều định dạng khác nhau, chẳng hạn như DOCX, PDF, HTML, v.v. Bạn có thể chọn định dạng phù hợp dựa trên yêu cầu của mình và sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu. Các nhãn dữ liệu đã định dạng sẽ được giữ nguyên trong tài liệu đã lưu.
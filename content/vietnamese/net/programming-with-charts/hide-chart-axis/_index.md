---
title: Ẩn trục biểu đồ trong tài liệu Word
linktitle: Ẩn trục biểu đồ trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách ẩn trục biểu đồ trong tài liệu bằng Aspose.Words for .NET. Ẩn trục để hiển thị biểu đồ rõ ràng và tập trung hơn.
type: docs
weight: 10
url: /vi/net/programming-with-charts/hide-chart-axis/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để ẩn trục biểu đồ trong tài liệu. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, thêm dữ liệu chuỗi và ẩn trục biểu đồ.

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

 Tiếp theo, chèn biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder`. Trong ví dụ này, chúng tôi sẽ chèn biểu đồ cột.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Thêm dữ liệu chuỗi vào biểu đồ

Thêm dữ liệu chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm năm mục và giá trị tương ứng của chúng.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Bước 4: Ẩn trục biểu đồ

 Để ẩn trục biểu đồ, hãy truy cập vào`AxisY` thuộc tính của biểu đồ và thiết lập`Hidden`tài sản để`true`.

```csharp
chart.AxisY.Hidden = true;
```

Trong ví dụ này, chúng tôi ẩn trục Y của biểu đồ.

## Bước 5: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Điều này hoàn tất việc thực hiện ẩn trục biểu đồ bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Ẩn trục biểu đồ bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách ẩn trục biểu đồ trong tài liệu Word bằng Aspose.Words for .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo biểu đồ, thêm dữ liệu chuỗi và ẩn trục biểu đồ để đạt được hiệu ứng hình ảnh mong muốn.

 Aspose.Words for .NET cung cấp API toàn diện cho Xử lý từ với các biểu đồ trong tài liệu Word, cho phép bạn thao tác các khía cạnh khác nhau của biểu đồ, bao gồm các thuộc tính trục. Bằng cách truy cập vào`AxisY` của biểu đồ, bạn có thể ẩn trục Y để xóa nó khỏi trực quan hóa biểu đồ.

Việc ẩn trục biểu đồ có thể hữu ích khi bạn muốn tập trung vào dữ liệu biểu đồ mà không bị các đường trục và nhãn làm phân tâm. Nó mang lại vẻ ngoài gọn gàng và tối giản hơn cho biểu đồ.

Bằng cách sử dụng Aspose.Words cho .NET, bạn có thể dễ dàng kết hợp các khả năng lập biểu đồ vào các ứng dụng .NET của mình và tạo các tài liệu có giao diện chuyên nghiệp với các biểu đồ tùy chỉnh và các trục biểu đồ ẩn.

### Câu hỏi thường gặp

#### Q1. Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện xử lý tài liệu mạnh mẽ cho phép các nhà phát triển tạo, thao tác và lưu tài liệu Word theo chương trình trong các ứng dụng .NET. Nó cung cấp nhiều tính năng cho Xử lý văn bản với các thành phần tài liệu, bao gồm biểu đồ và trục biểu đồ.

#### Q2. Làm cách nào tôi có thể cài đặt Aspose.Words cho .NET?
Bạn có thể cài đặt Aspose.Words cho .NET bằng cách tải xuống bằng cách sử dụng trình quản lý gói NuGet trong Visual Studio. Chỉ cần tìm kiếm "Aspose.Words" trong trình quản lý gói NuGet và cài đặt nó vào dự án của bạn.

#### Q3. Tôi có thể ẩn cả trục X và trục Y của biểu đồ không?
 Có, bạn có thể ẩn cả trục X và trục Y của biểu đồ bằng Aspose.Words for .NET. Để ẩn trục X, bạn có thể truy cập`AxisX` thuộc tính của biểu đồ và thiết lập`Hidden`tài sản để`true` . Tương tự, để ẩn trục Y, bạn có thể truy cập vào`AxisY` thuộc tính và thiết lập`Hidden`tài sản để`true`. Điều này cho phép bạn loại bỏ cả hai trục khỏi trực quan hóa biểu đồ.

#### Q4. Tôi có thể hiển thị lại trục sau khi ẩn nó không?
Có, bạn có thể hiển thị lại trục biểu đồ sau khi ẩn nó bằng Aspose.Words for .NET. Để hiển thị trục ẩn, chỉ cần đặt`Hidden` thuộc tính tương ứng`AxisX` hoặc`AxisY` chủ đề`false`. Điều này sẽ làm cho trục hiển thị trở lại trong biểu đồ.

#### Q5. Tôi có thể tùy chỉnh các thuộc tính khác của trục biểu đồ không?
 Có, Aspose.Words for .NET cho phép bạn tùy chỉnh các thuộc tính khác nhau của trục biểu đồ, chẳng hạn như tiêu đề trục, nhãn, màu đường, v.v. Bằng cách truy cập vào`AxisX` Và`AxisY` thuộc tính của biểu đồ, bạn có thể sửa đổi các thuộc tính như`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, và nhiều người khác. Điều này mang lại cho bạn khả năng kiểm soát chi tiết về hình thức và hoạt động của trục biểu đồ.

#### Q6. Tôi có thể lưu biểu đồ có trục ẩn ở các định dạng tệp khác nhau không?
 Có, Aspose.Words for .NET cho phép bạn lưu tài liệu chứa biểu đồ có trục ẩn ở nhiều định dạng tệp khác nhau, chẳng hạn như DOCX, PDF, HTML, v.v. Bạn có thể chọn định dạng đầu ra mong muốn dựa trên yêu cầu của mình và sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu. Trục ẩn sẽ được giữ nguyên trong tài liệu đã lưu.
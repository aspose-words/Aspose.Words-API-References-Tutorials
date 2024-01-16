---
title: Chèn biểu đồ cột đơn giản vào tài liệu Word
linktitle: Chèn biểu đồ cột đơn giản vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn biểu đồ cột đơn giản vào tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/insert-simple-column-chart/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để chèn biểu đồ cột đơn giản vào tài liệu. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, thêm dữ liệu chuỗi và lưu tài liệu.

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

 Tiếp theo, sử dụng`InsertChart` phương pháp của`DocumentBuilder` để chèn biểu đồ cột vào tài liệu. Bạn có thể chỉ định các loại và kích thước biểu đồ khác nhau theo yêu cầu của mình.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Thêm dữ liệu chuỗi vào biểu đồ

Thêm dữ liệu chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm nhiều chuỗi, mỗi chuỗi có hai danh mục.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Bước 4: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Điều này hoàn tất việc triển khai chèn biểu đồ cột đơn giản bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Chèn biểu đồ cột đơn giản bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Bạn có thể chỉ định các loại và kích cỡ biểu đồ khác nhau.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Xóa chuỗi được tạo mặc định.
	seriesColl.Clear();
	// Tạo mảng tên danh mục, trong hướng dẫn này chúng ta có hai danh mục.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Xin lưu ý, mảng dữ liệu không được để trống và các mảng phải có cùng kích thước.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách chèn biểu đồ cột đơn giản vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo tài liệu mới, chèn biểu đồ cột, thêm nhiều chuỗi với các danh mục và giá trị tương ứng cũng như lưu tài liệu cùng với biểu đồ.

Aspose.Words for .NET cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản với các biểu đồ trong tài liệu Word. Biểu đồ cột đơn giản là cách hiệu quả để trình bày và so sánh dữ liệu trong các danh mục khác nhau. Với Aspose.Words for .NET, bạn có thể dễ dàng tạo biểu đồ cột với dữ liệu tùy chỉnh, thêm nhiều chuỗi để so sánh trực quan và tùy chỉnh giao diện của biểu đồ theo yêu cầu của bạn.

Bằng cách sử dụng Aspose.Words for .NET, bạn có thể tự động hóa quá trình tạo tài liệu bằng biểu đồ cột, tiết kiệm thời gian và công sức khi tạo tài liệu thủ công. Thư viện cung cấp nhiều loại biểu đồ, bao gồm biểu đồ cột đơn giản và cung cấp nhiều tùy chọn tùy chỉnh khác nhau để điều chỉnh hình thức của biểu đồ cho phù hợp với nhu cầu của bạn.

### Câu hỏi thường gặp

#### Q1. Biểu đồ cột là gì?
Biểu đồ cột là loại biểu đồ hiển thị dữ liệu bằng các thanh dọc có độ cao khác nhau. Mỗi cột đại diện cho một danh mục và chiều cao của cột tương ứng với giá trị của danh mục đó. Biểu đồ cột thường được sử dụng để so sánh dữ liệu giữa các danh mục khác nhau hoặc để theo dõi các thay đổi theo thời gian.

#### Q2. Tôi có thể thêm nhiều chuỗi vào biểu đồ cột không?
Có, bằng cách sử dụng Aspose.Words cho .NET, bạn có thể thêm nhiều chuỗi vào biểu đồ cột. Mỗi chuỗi đại diện cho một tập hợp các điểm dữ liệu với các danh mục và giá trị tương ứng. Bằng cách thêm nhiều chuỗi, bạn có thể so sánh và phân tích các tập dữ liệu khác nhau trong cùng một biểu đồ cột, cung cấp cái nhìn toàn diện về dữ liệu của bạn.

#### Q3. Tôi có thể tùy chỉnh giao diện của biểu đồ cột không?
Có, Aspose.Words for .NET cho phép bạn tùy chỉnh các khía cạnh khác nhau về hình thức của biểu đồ cột. Bạn có thể sửa đổi các thuộc tính như màu chuỗi, nhãn trục, nhãn dữ liệu và định dạng vùng biểu đồ. Thư viện cung cấp một bộ API phong phú để kiểm soát các thành phần trực quan của biểu đồ và tạo giao diện tùy chỉnh phù hợp với nhu cầu của bạn.

#### Q4. Tôi có thể lưu tài liệu có biểu đồ cột được chèn ở các định dạng khác nhau không?
 Có, Aspose.Words for .NET cho phép bạn lưu tài liệu có biểu đồ cột được chèn ở nhiều định dạng khác nhau, chẳng hạn như DOCX, PDF, HTML, v.v. Bạn có thể chọn định dạng đầu ra mong muốn dựa trên yêu cầu của mình và sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu. Biểu đồ cột được chèn sẽ được giữ nguyên trong tài liệu đã lưu.

#### Q5. Tôi có thể sửa đổi dữ liệu và hình thức của biểu đồ cột sau khi chèn nó không?
Có, sau khi chèn biểu đồ cột vào tài liệu, bạn có thể sửa đổi dữ liệu và giao diện của biểu đồ cột bằng cách sử dụng API do Aspose.Words cung cấp cho .NET. Bạn có thể cập nhật dữ liệu chuỗi với các danh mục và giá trị mới, thay đổi màu sắc và định dạng của cột, tùy chỉnh thuộc tính trục và áp dụng các tùy chọn định dạng khác nhau để tạo biểu đồ động và hấp dẫn trực quan trong tài liệu Word của bạn.
---
title: Chèn biểu đồ phân tán vào tài liệu Word
linktitle: Chèn biểu đồ phân tán vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn biểu đồ phân tán vào tài liệu bằng Aspose.Words cho .NET. Thêm dữ liệu chuỗi với tọa độ X và Y.
type: docs
weight: 10
url: /vi/net/programming-with-charts/insert-scatter-chart/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để chèn biểu đồ phân tán vào tài liệu. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, thêm dữ liệu chuỗi và lưu tài liệu.

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

 Tiếp theo, sử dụng`InsertChart` phương pháp của`DocumentBuilder` để chèn biểu đồ phân tán vào tài liệu.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Thêm dữ liệu chuỗi vào biểu đồ

Thêm dữ liệu chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm hai bộ tọa độ X và Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Bước 4: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Điều này hoàn tất việc triển khai chèn biểu đồ phân tán bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Chèn biểu đồ phân tán bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách chèn biểu đồ phân tán vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo tài liệu mới, chèn biểu đồ phân tán, thêm dữ liệu chuỗi với tọa độ X và Y và lưu tài liệu cùng với biểu đồ.

Aspose.Words for .NET cung cấp API toàn diện cho Xử lý văn bản với các biểu đồ trong tài liệu Word. Biểu đồ tán xạ rất hữu ích cho việc hiển thị và phân tích dữ liệu với hai biến số. Với Aspose.Words for .NET, bạn có thể dễ dàng tạo biểu đồ phân tán thể hiện mối quan hệ giữa các giá trị X và Y cũng như xác định các mẫu hoặc xu hướng trong dữ liệu.

Bằng cách sử dụng Aspose.Words cho .NET, bạn có thể tự động hóa quá trình tạo tài liệu bằng biểu đồ phân tán, tiết kiệm thời gian và công sức khi tạo tài liệu thủ công. Thư viện cung cấp nhiều loại biểu đồ, bao gồm biểu đồ phân tán và cung cấp nhiều tùy chọn tùy chỉnh khác nhau để điều chỉnh giao diện của biểu đồ theo nhu cầu của bạn.

### Câu hỏi thường gặp

#### Q1. Biểu đồ phân tán là gì?
Biểu đồ phân tán là một loại biểu đồ hiển thị mối quan hệ giữa hai biến số. Nó bao gồm một loạt các điểm được vẽ trên lưới tọa độ, với một biến được biểu thị trên trục X và biến còn lại được biểu thị trên trục Y. Biểu đồ phân tán được sử dụng để xác định các mẫu, mối tương quan hoặc xu hướng giữa hai bộ điểm dữ liệu.

#### Q2. Tôi có thể thêm nhiều chuỗi vào biểu đồ phân tán không?
Có, bạn có thể thêm nhiều chuỗi vào biểu đồ phân tán bằng Aspose.Words for .NET. Mỗi chuỗi đại diện cho một tập hợp các điểm dữ liệu có tọa độ X và Y tương ứng. Bằng cách thêm nhiều chuỗi, bạn có thể so sánh và phân tích các tập dữ liệu khác nhau trong cùng một biểu đồ phân tán, cung cấp cái nhìn toàn diện về dữ liệu của bạn.

#### Q3. Tôi có thể tùy chỉnh giao diện của biểu đồ phân tán không?
Có, bằng cách sử dụng Aspose.Words cho .NET, bạn có thể tùy chỉnh các khía cạnh khác nhau về giao diện của biểu đồ phân tán. Bạn có thể sửa đổi các thuộc tính như màu chuỗi, hình dạng điểm đánh dấu, nhãn trục và định dạng vùng biểu đồ. Thư viện cung cấp một bộ API phong phú để kiểm soát các thành phần trực quan của biểu đồ và tạo giao diện tùy chỉnh phù hợp với nhu cầu của bạn.

#### Q4. Tôi có thể lưu tài liệu có biểu đồ tán xạ được chèn ở các định dạng khác nhau không?
Có, Aspose.Words for .NET cho phép bạn lưu tài liệu với biểu đồ phân tán được chèn ở nhiều định dạng khác nhau, chẳng hạn như DOCX, PDF, HTML, v.v. Bạn có thể chọn định dạng đầu ra mong muốn dựa trên yêu cầu của mình và sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu. Biểu đồ phân tán được chèn sẽ được giữ nguyên trong tài liệu đã lưu.

#### Q5. Tôi có thể sửa đổi dữ liệu và hình thức của biểu đồ phân tán sau khi chèn nó không?
Có, sau khi chèn biểu đồ phân tán vào tài liệu, bạn có thể sửa đổi dữ liệu và giao diện của biểu đồ bằng cách sử dụng API do Aspose.Words cho .NET cung cấp. Bạn có thể cập nhật dữ liệu chuỗi với tọa độ X và Y mới, thay đổi hình dạng và màu sắc của điểm đánh dấu, tùy chỉnh thuộc tính trục và áp dụng các tùy chọn định dạng để tạo biểu đồ động và tương tác trong tài liệu Word của bạn.
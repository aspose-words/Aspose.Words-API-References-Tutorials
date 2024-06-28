---
title: Chèn biểu đồ vùng vào tài liệu Word
linktitle: Chèn biểu đồ vùng vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn biểu đồ vùng vào tài liệu bằng Aspose.Words cho .NET. Thêm dữ liệu chuỗi và lưu tài liệu cùng với biểu đồ.
type: docs
weight: 10
url: /vi/net/programming-with-charts/insert-area-chart/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để chèn biểu đồ vùng vào tài liệu. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, thêm dữ liệu chuỗi và lưu tài liệu.

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

 Tiếp theo, sử dụng`InsertChart` phương pháp của`DocumentBuilder` để chèn biểu đồ vùng vào tài liệu.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Thêm dữ liệu chuỗi vào biểu đồ

Thêm dữ liệu chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm năm điểm dữ liệu có ngày và giá trị tương ứng.

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

## Bước 4: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Điều này hoàn tất việc triển khai chèn biểu đồ vùng bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Chèn biểu đồ vùng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Phần kết luận

Trong hướng dẫn này, bạn đã học cách chèn biểu đồ vùng vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo tài liệu mới, chèn biểu đồ vùng, thêm dữ liệu chuỗi và lưu tài liệu cùng với biểu đồ.

Aspose.Words for .NET cung cấp API mạnh mẽ để Xử lý Từ với các biểu đồ trong tài liệu Word. Chỉ với một vài dòng mã, bạn có thể tạo biểu đồ vùng trông chuyên nghiệp và tùy chỉnh chúng theo yêu cầu của mình. Biểu đồ vùng thường được sử dụng để hiển thị mức độ và xu hướng của dữ liệu theo thời gian hoặc danh mục.

Bằng cách sử dụng Aspose.Words cho .NET, bạn có thể tự động hóa quá trình tạo tài liệu bằng biểu đồ vùng, tiết kiệm thời gian và công sức khi tạo tài liệu thủ công. Thư viện cung cấp nhiều loại biểu đồ và tùy chọn tùy chỉnh, cho phép bạn tạo các biểu đồ mang tính thông tin và hấp dẫn trực quan trong tài liệu Word của mình.

### Câu hỏi thường gặp

#### Q1. Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện xử lý tài liệu mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi tài liệu Word theo chương trình trong các ứng dụng .NET. Nó cung cấp một bộ API toàn diện để Xử lý văn bản với các thành phần tài liệu, bao gồm biểu đồ, đoạn văn, bảng, v.v.

#### Q2. Làm cách nào để cài đặt Aspose.Words cho .NET?
Để cài đặt Aspose.Words cho .NET, bạn có thể sử dụng trình quản lý gói NuGet trong Visual Studio để cài đặt thư viện trực tiếp vào dự án của mình. Chỉ cần tìm kiếm "Apose.Words" trong trình quản lý gói NuGet và cài đặt gói.

#### Q3. Tôi có thể tùy chỉnh hình thức của biểu đồ vùng không?
Có, bằng cách sử dụng Aspose.Words cho .NET, bạn có thể tùy chỉnh các khía cạnh khác nhau về hình thức của biểu đồ vùng. Bạn có thể sửa đổi các thuộc tính như tiêu đề biểu đồ, màu chuỗi, nhãn trục và định dạng vùng biểu đồ. Thư viện cung cấp một bộ API phong phú để kiểm soát các thành phần trực quan của biểu đồ và tạo giao diện tùy chỉnh phù hợp với nhu cầu của bạn.

#### Q4. Tôi có thể thêm nhiều chuỗi vào biểu đồ vùng không?
Có, bạn có thể thêm nhiều chuỗi vào biểu đồ vùng bằng Aspose.Words for .NET. Mỗi chuỗi đại diện cho một tập hợp các điểm dữ liệu được vẽ trên biểu đồ. Bạn có thể thêm chuỗi với các tập dữ liệu khác nhau và tùy chỉnh từng chuỗi riêng lẻ, bao gồm tên, điểm dữ liệu và hình thức của chuỗi.

#### Q5. Tôi có thể lưu tài liệu có biểu đồ vùng được chèn ở các định dạng khác nhau không?
 Có, Aspose.Words for .NET cho phép bạn lưu tài liệu có biểu đồ vùng được chèn ở nhiều định dạng khác nhau, chẳng hạn như DOCX, PDF, HTML, v.v. Bạn có thể chọn định dạng đầu ra mong muốn dựa trên yêu cầu của mình và sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu. Biểu đồ vùng được chèn sẽ được giữ nguyên trong tài liệu đã lưu.

#### Q6. Tôi có thể sửa đổi dữ liệu và hình thức của biểu đồ vùng sau khi chèn nó không?
Có, sau khi chèn biểu đồ vùng vào tài liệu, bạn có thể sửa đổi dữ liệu và hình thức của biểu đồ bằng cách sử dụng API do Aspose.Words cung cấp cho .NET. Bạn có thể cập nhật dữ liệu chuỗi, thay đổi loại biểu đồ, tùy chỉnh thuộc tính trục và áp dụng các tùy chọn định dạng để tạo biểu đồ động và tương tác trong tài liệu Word của mình.
---
title: Tùy chỉnh nhãn dữ liệu biểu đồ
linktitle: Tùy chỉnh nhãn dữ liệu biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm và tùy chỉnh nhãn dữ liệu trong biểu đồ bằng Aspose.Words for .NET để cung cấp thêm thông tin về điểm dữ liệu.
type: docs
weight: 10
url: /vi/net/programming-with-charts/chart-data-label/
---

Hướng dẫn này giải thích cách thêm và tùy chỉnh nhãn dữ liệu trong biểu đồ bằng Aspose.Words cho .NET. Nhãn dữ liệu cung cấp thông tin bổ sung về các điểm dữ liệu trong biểu đồ.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu mới và DocumentBuilder
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder`đối tượng làm việc với tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn và định cấu hình biểu đồ
 Chèn biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder` sự vật. Đặt loại và kích thước biểu đồ mong muốn.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Bước 4: Tùy chỉnh nhãn dữ liệu
Truy cập bộ sưu tập nhãn dữ liệu của chuỗi biểu đồ và sửa đổi các thuộc tính khác nhau để tùy chỉnh giao diện của nhãn dữ liệu.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Bước 5: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Mã nguồn mẫu cho Nhãn dữ liệu biểu đồ bằng Aspose.Words for .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Theo mặc định, khi bạn thêm nhãn dữ liệu vào các điểm dữ liệu trong biểu đồ hình tròn, các dòng dẫn đầu sẽ được hiển thị cho các nhãn dữ liệu
	// được đặt xa bên ngoài điểm cuối của các điểm dữ liệu. Đường dẫn tạo ra sự kết nối trực quan giữa nhãn dữ liệu và
	// điểm dữ liệu tương ứng.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Đó là nó! Bạn đã thêm và tùy chỉnh thành công nhãn dữ liệu trong biểu đồ bằng Aspose.Words for .NET.

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách thêm và tùy chỉnh nhãn dữ liệu trong biểu đồ bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể chèn biểu đồ, truy cập bộ sưu tập nhãn dữ liệu và sửa đổi các thuộc tính để tùy chỉnh giao diện của nhãn dữ liệu. Aspose.Words for .NET cung cấp một API mạnh mẽ để Xử lý Từ bằng các tài liệu và biểu đồ Word, cho phép bạn tạo các biểu đồ mang tính thông tin và hấp dẫn trực quan với các nhãn dữ liệu tùy chỉnh.

### Câu hỏi thường gặp

#### Q1. Nhãn dữ liệu trong biểu đồ là gì?
Nhãn dữ liệu trong biểu đồ cung cấp thông tin bổ sung về các điểm dữ liệu được biểu thị trong biểu đồ. Chúng có thể hiển thị giá trị, danh mục, tên chuỗi, tỷ lệ phần trăm hoặc các chi tiết liên quan khác tùy thuộc vào loại và cấu hình biểu đồ.

#### Q2. Tôi có thể tùy chỉnh giao diện của nhãn dữ liệu không?
Có, bạn có thể tùy chỉnh giao diện của nhãn dữ liệu trong biểu đồ. Aspose.Words for .NET cung cấp các tùy chọn để sửa đổi các thuộc tính khác nhau của nhãn dữ liệu, chẳng hạn như hiển thị các khóa chú giải, dòng dẫn đầu, tên danh mục, tên chuỗi, giá trị, v.v. Bạn cũng có thể đặt dấu phân cách và định dạng nhãn để đáp ứng yêu cầu cụ thể của mình.

#### Q3. Tôi có thể thêm nhãn dữ liệu vào bất kỳ loại biểu đồ nào không?
Có, bạn có thể thêm nhãn dữ liệu vào nhiều loại biểu đồ khác nhau, bao gồm biểu đồ thanh, biểu đồ hình tròn, biểu đồ đường, v.v. Quá trình thêm và tùy chỉnh nhãn dữ liệu có thể hơi khác nhau tùy thuộc vào loại biểu đồ và thư viện hoặc công cụ bạn đang sử dụng.

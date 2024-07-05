---
title: Tạo và tùy chỉnh biểu đồ bằng hình dạng
linktitle: Tạo và tùy chỉnh biểu đồ bằng hình dạng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo và tùy chỉnh biểu đồ bằng hình dạng trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/create-chart-using-shape/
---

Hướng dẫn này giải thích cách tạo biểu đồ bằng hình dạng trong tài liệu Word bằng Aspose.Words cho .NET.

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

## Bước 3: Chèn và định cấu hình hình dạng biểu đồ
 Chèn hình dạng biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder` sự vật. Đặt loại và kích thước biểu đồ mong muốn.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Bước 4: Tùy chỉnh biểu đồ
Tùy chỉnh biểu đồ bằng cách sửa đổi các thuộc tính khác nhau như tiêu đề và chú giải biểu đồ.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Bước 5: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Mã nguồn ví dụ cho Tạo biểu đồ bằng hình dạng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Xin lưu ý nếu giá trị null hoặc trống được chỉ định làm văn bản tiêu đề, tiêu đề được tạo tự động sẽ được hiển thị.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Đó là nó! Bạn đã tạo thành công biểu đồ bằng hình dạng trong tài liệu Word bằng Aspose.Words for .NET.

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách tạo biểu đồ bằng hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể chèn và định cấu hình hình dạng biểu đồ, tùy chỉnh giao diện của biểu đồ và lưu tài liệu. Aspose.Words for .NET cung cấp một bộ tính năng toàn diện để Xử lý văn bản bằng tài liệu và biểu đồ Word, cho phép bạn tạo các biểu đồ trông chuyên nghiệp và hấp dẫn trực tiếp trong các ứng dụng .NET của mình.

### Câu hỏi thường gặp

#### Q1. Tôi có thể tạo biểu đồ trong tài liệu Word bằng Aspose.Words cho .NET không?
Có, với Aspose.Words for .NET, bạn có thể tạo biểu đồ trong tài liệu Word theo chương trình. Aspose.Words cung cấp API và chức năng để chèn nhiều loại biểu đồ khác nhau, tùy chỉnh giao diện của chúng và thao tác dữ liệu biểu đồ.

#### Q2. Những loại biểu đồ nào được Aspose.Words hỗ trợ cho .NET?
Aspose.Words for .NET hỗ trợ nhiều loại biểu đồ, bao gồm biểu đồ đường, biểu đồ thanh, biểu đồ hình tròn, biểu đồ vùng, biểu đồ phân tán, v.v. Bạn có thể chọn loại biểu đồ phù hợp dựa trên yêu cầu về dữ liệu và hình ảnh của mình.

#### Q3. Tôi có thể tùy chỉnh giao diện của biểu đồ đã tạo không?
Có, bạn có thể tùy chỉnh giao diện của biểu đồ đã tạo bằng Aspose.Words for .NET. Bạn có thể sửa đổi các thuộc tính như tiêu đề biểu đồ, vị trí chú giải, nhãn dữ liệu, nhãn trục, màu sắc và các thành phần trực quan khác để đáp ứng nhu cầu định dạng và thiết kế cụ thể của bạn.

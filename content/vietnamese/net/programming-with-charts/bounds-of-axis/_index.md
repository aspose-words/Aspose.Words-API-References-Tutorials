---
title: Giới hạn của trục trong biểu đồ
linktitle: Giới hạn của trục trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt giới hạn của một trục trong biểu đồ bằng Aspose.Words for .NET kiểm soát phạm vi giá trị được hiển thị trên trục.
type: docs
weight: 10
url: /vi/net/programming-with-charts/bounds-of-axis/
---

Hướng dẫn này giải thích cách đặt giới hạn của một trục trong biểu đồ bằng Aspose.Words cho .NET. Bằng cách chèn biểu đồ, thêm dữ liệu chuỗi và định cấu hình chia tỷ lệ trục, bạn có thể xác định giá trị tối thiểu và tối đa cho trục.

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
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` đối tượng làm việc với tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn và định cấu hình biểu đồ
 Chèn biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder` sự vật. Đặt loại và kích thước biểu đồ mong muốn.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Bước 4: Thêm dữ liệu chuỗi
Xóa mọi chuỗi hiện có trong biểu đồ và thêm dữ liệu chuỗi mới. Trong ví dụ này, chúng tôi thêm một chuỗi có nhãn "Mục 1" vào "Mục 5" và các giá trị tương ứng.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Bước 5: Đặt giới hạn của trục
 Định cấu hình tỷ lệ của trục Y bằng cách đặt giá trị tối thiểu và tối đa bằng cách sử dụng`Scaling.Minimum` Và`Scaling.Maximum` tính chất của trục.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Bước 6: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Mã nguồn ví dụ cho Bounds Of Axis sử dụng Aspose.Words for .NET 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Đó là nó! Bạn đã đặt thành công giới hạn của một trục trong biểu đồ bằng Aspose.Words for .NET.

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách đặt giới hạn của một trục trong biểu đồ bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể chèn và định cấu hình biểu đồ, thêm dữ liệu chuỗi cũng như xác định giá trị tối thiểu và tối đa cho tỷ lệ trục. Aspose.Words for .NET cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản bằng tài liệu Word, cho phép bạn tạo các biểu đồ động và hấp dẫn trực quan một cách dễ dàng.


### Câu hỏi thường gặp

#### Q1. Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện cho phép các nhà phát triển làm việc với các tài liệu Word theo chương trình. Nó cung cấp nhiều tính năng và chức năng để tạo, thao tác và lưu tài liệu Word.

#### Q2. Làm cách nào tôi có thể cài đặt Aspose.Words cho .NET?
Để cài đặt Aspose.Words cho .NET, bạn có thể sử dụng trình quản lý gói NuGet trong Visual Studio. Chỉ cần tìm kiếm "Apose.Words" trong trình quản lý gói NuGet và cài đặt nó vào dự án của bạn.

#### Q3. Tôi có thể sử dụng Aspose.Words cho .NET với các ngôn ngữ lập trình khác không?
Không, Aspose.Words for .NET được thiết kế riêng cho các ứng dụng .NET. Nó hoạt động với các ngôn ngữ lập trình như C# và VB.NET.

#### Q4. Có điều kiện tiên quyết nào khác để sử dụng Aspose.Words cho .NET không?
Bên cạnh việc cài đặt thư viện Aspose.Words for .NET, bạn nên có kiến thức cơ bản về lập trình C# và Xử lý văn bản với tài liệu Word. Làm quen với .NET framework cũng sẽ hữu ích.

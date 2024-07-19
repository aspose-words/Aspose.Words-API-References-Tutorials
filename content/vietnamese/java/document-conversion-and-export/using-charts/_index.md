---
title: Sử dụng Biểu đồ trong Aspose.Words cho Java
linktitle: Sử dụng biểu đồ
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách tạo và tùy chỉnh biểu đồ trong Aspose.Words cho Java. Khám phá các loại biểu đồ, định dạng và thuộc tính trục để trực quan hóa dữ liệu.
type: docs
weight: 12
url: /vi/java/document-conversion-and-export/using-charts/
---

## Giới thiệu về Sử dụng Biểu đồ trong Aspose.Words cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với biểu đồ bằng Aspose.Words cho Java. Bạn sẽ tìm hiểu cách tạo nhiều loại biểu đồ khác nhau, tùy chỉnh thuộc tính trục, định dạng nhãn dữ liệu, v.v. Hãy đi sâu vào!

## Tạo biểu đồ đường

Để tạo biểu đồ đường, hãy sử dụng đoạn mã sau:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// Xóa chuỗi được tạo mặc định.
chart.getSeries().clear();

// Thêm một chuỗi có dữ liệu và nhãn dữ liệu.
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// Hoặc liên kết mã định dạng tới một ô nguồn.
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Tạo các loại biểu đồ khác

Bạn có thể tạo các loại biểu đồ khác nhau như cột, vùng, bong bóng, phân tán, v.v. bằng cách sử dụng các kỹ thuật tương tự. Dưới đây là ví dụ về cách chèn biểu đồ cột đơn giản:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Xóa chuỗi được tạo mặc định.
chart.getSeries().clear();

// Tạo danh mục và thêm dữ liệu.
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Tùy chỉnh thuộc tính trục

Bạn có thể tùy chỉnh các thuộc tính trục, chẳng hạn như thay đổi loại trục, đặt dấu kiểm, định dạng nhãn, v.v. Dưới đây là ví dụ về xác định thuộc tính trục XY:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// Xóa chuỗi mặc định và thêm dữ liệu của bạn.

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// Thay đổi trục X thành danh mục thay vì ngày.
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); //Được đo bằng đơn vị hiển thị của trục Y (hàng trăm).
xAxis.setReverseOrder(true);
xAxis.setMajorTickMark(AxisTickMark.CROSS);
xAxis.setMinorTickMark(AxisTickMark.OUTSIDE);
xAxis.setTickLabelOffset(200);

yAxis.setTickLabelPosition(AxisTickLabelPosition.HIGH);
yAxis.setMajorUnit(100.0);
yAxis.setMinorUnit(50.0);
yAxis.getDisplayUnit().setUnit(AxisBuiltInUnit.HUNDREDS);
yAxis.getScaling().setMinimum(new AxisBound(100.0));
yAxis.getScaling().setMaximum(new AxisBound(700.0));

doc.save("Your Directory Path" + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Định dạng nhãn dữ liệu

Bạn có thể định dạng nhãn dữ liệu với các định dạng số khác nhau. Đây là một ví dụ:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Xóa chuỗi mặc định và thêm dữ liệu của bạn.

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Tùy chỉnh biểu đồ bổ sung

Bạn có thể tùy chỉnh thêm biểu đồ của mình bằng cách điều chỉnh giới hạn, đơn vị khoảng cách giữa các nhãn, ẩn trục biểu đồ, v.v. Khám phá các đoạn mã được cung cấp để tìm hiểu thêm về các tùy chọn này.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách làm việc với biểu đồ bằng Aspose.Words cho Java. Bạn đã học cách tạo nhiều loại biểu đồ, tùy chỉnh thuộc tính trục, định dạng nhãn dữ liệu, v.v. Aspose.Words for Java cung cấp các công cụ mạnh mẽ để thêm cách trình bày dữ liệu trực quan vào tài liệu của bạn, nâng cao cách bạn trình bày thông tin.

## Câu hỏi thường gặp

### Làm cách nào để thêm nhiều chuỗi vào biểu đồ?

 Bạn có thể thêm nhiều chuỗi vào biểu đồ bằng cách sử dụng`chart.getSeries().add()` phương pháp. Đảm bảo chỉ định tên chuỗi, danh mục và giá trị dữ liệu.

### Làm cách nào tôi có thể định dạng nhãn dữ liệu bằng định dạng số tùy chỉnh?

Bạn có thể định dạng nhãn dữ liệu bằng cách truy cập vào`DataLabels` thuộc tính của một chuỗi và đặt mã định dạng mong muốn bằng cách sử dụng`getNumberFormat().setFormatCode()`.

### Làm cách nào để tùy chỉnh các thuộc tính trục trong biểu đồ?

 Bạn có thể tùy chỉnh các thuộc tính trục như loại, dấu kiểm, nhãn, v.v. bằng cách truy cập vào`ChartAxis` tính chất như`setCategoryType()`, `setCrosses()` , Và`setMajorTickMark()`.

### Làm cách nào tôi có thể tạo các loại biểu đồ khác như biểu đồ phân tán hoặc biểu đồ vùng?

 Bạn có thể tạo nhiều loại biểu đồ khác nhau bằng cách chỉ định các loại biểu đồ thích hợp.`ChartType` khi chèn biểu đồ bằng cách sử dụng`builder.insertChart(ChartType.TYPE, width, height)`.

### Làm cách nào để ẩn trục biểu đồ?

 Bạn có thể ẩn trục biểu đồ bằng cách đặt`setHidden(true)` tính chất của trục.
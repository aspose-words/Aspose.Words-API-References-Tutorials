---
title: การใช้แผนภูมิใน Aspose.Words สำหรับ Java
linktitle: การใช้แผนภูมิ
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีสร้างและปรับแต่งแผนภูมิใน Aspose.Words สำหรับ Java สำรวจประเภทแผนภูมิ การจัดรูปแบบ และคุณสมบัติของแกนสำหรับการแสดงข้อมูลเป็นภาพ
type: docs
weight: 12
url: /th/java/document-conversion-and-export/using-charts/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการใช้แผนภูมิใน Aspose.Words สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับแผนภูมิโดยใช้ Aspose.Words สำหรับ Java คุณจะได้เรียนรู้วิธีสร้างแผนภูมิประเภทต่างๆ ปรับแต่งคุณสมบัติของแกน จัดรูปแบบป้ายชื่อข้อมูล และอื่นๆ มาดำน้ำกันเถอะ!

## การสร้างแผนภูมิเส้น

หากต้องการสร้างแผนภูมิเส้น ให้ใช้โค้ดต่อไปนี้:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// ลบซีรี่ส์ที่สร้างโดยค่าเริ่มต้น
chart.getSeries().clear();

// การเพิ่มชุดข้อมูลและป้ายกำกับข้อมูล
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// หรือลิงก์โค้ดรูปแบบไปยังเซลล์ต้นทาง
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## การสร้างแผนภูมิประเภทอื่นๆ

คุณสามารถสร้างแผนภูมิประเภทต่างๆ ได้ เช่น คอลัมน์ พื้นที่ ฟองอากาศ กระจาย และอื่นๆ โดยใช้เทคนิคที่คล้ายกัน ต่อไปนี้เป็นตัวอย่างของการแทรกแผนภูมิคอลัมน์แบบง่าย:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// ลบซีรี่ส์ที่สร้างโดยค่าเริ่มต้น
chart.getSeries().clear();

// การสร้างหมวดหมู่และเพิ่มข้อมูล
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## การปรับแต่งคุณสมบัติของแกน

คุณสามารถปรับแต่งคุณสมบัติของแกนได้ เช่น การเปลี่ยนประเภทแกน การตั้งค่าเครื่องหมายถูก การจัดรูปแบบป้ายกำกับ และอื่นๆ ต่อไปนี้เป็นตัวอย่างการกำหนดคุณสมบัติแกน XY:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// ล้างชุดข้อมูลเริ่มต้นและเพิ่มข้อมูลของคุณ

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// เปลี่ยนแกน X ให้เป็นหมวดหมู่แทนวันที่
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); //วัดในหน่วยแสดงผลของแกน Y (หลักร้อย)
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

## การจัดรูปแบบฉลากข้อมูล

คุณสามารถจัดรูปแบบป้ายกำกับข้อมูลด้วยรูปแบบตัวเลขที่แตกต่างกันได้ นี่คือตัวอย่าง:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// ล้างชุดข้อมูลเริ่มต้นและเพิ่มข้อมูลของคุณ

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## การปรับแต่งแผนภูมิเพิ่มเติม

คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้โดยการปรับขอบเขต หน่วยช่วงเวลาระหว่างป้ายกำกับ ซ่อนแกนแผนภูมิ และอื่นๆ สำรวจข้อมูลโค้ดที่ให้มาเพื่อเรียนรู้เพิ่มเติมเกี่ยวกับตัวเลือกเหล่านี้

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการทำงานกับแผนภูมิโดยใช้ Aspose.Words สำหรับ Java คุณได้เรียนรู้วิธีสร้างแผนภูมิประเภทต่างๆ ปรับแต่งคุณสมบัติของแกน จัดรูปแบบป้ายกำกับข้อมูล และอื่นๆ อีกมากมาย Aspose.Words สำหรับ Java มอบเครื่องมืออันทรงพลังสำหรับการเพิ่มการแสดงข้อมูลด้วยภาพลงในเอกสารของคุณ ซึ่งช่วยปรับปรุงวิธีการนำเสนอข้อมูลของคุณ

## คำถามที่พบบ่อย

### ฉันจะเพิ่มหลายชุดลงในแผนภูมิได้อย่างไร

 คุณสามารถเพิ่มหลายชุดลงในแผนภูมิโดยใช้`chart.getSeries().add()` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุชื่อซีรีส์ หมวดหมู่ และค่าข้อมูล

### ฉันจะจัดรูปแบบป้ายกำกับข้อมูลด้วยรูปแบบตัวเลขที่กำหนดเองได้อย่างไร

คุณสามารถจัดรูปแบบป้ายกำกับข้อมูลได้โดยเข้าไปที่`DataLabels` คุณสมบัติของซีรีย์และการตั้งค่าโค้ดรูปแบบที่ต้องการโดยใช้`getNumberFormat().setFormatCode()`.

### ฉันจะปรับแต่งคุณสมบัติของแกนในแผนภูมิได้อย่างไร

 คุณสามารถปรับแต่งคุณสมบัติของแกน เช่น ประเภท เครื่องหมายถูก ป้ายกำกับ และอื่นๆ ได้โดยเข้าไปที่`ChartAxis` คุณสมบัติเช่น`setCategoryType()`, `setCrosses()` , และ`setMajorTickMark()`.

### ฉันจะสร้างแผนภูมิประเภทอื่นๆ เช่น แผนภูมิกระจายหรือแผนภูมิพื้นที่ได้อย่างไร

 คุณสามารถสร้างแผนภูมิประเภทต่างๆ ได้โดยการระบุประเภทแผนภูมิที่เหมาะสม`ChartType` เมื่อแทรกแผนภูมิโดยใช้`builder.insertChart(ChartType.TYPE, width, height)`.

### ฉันจะซ่อนแกนแผนภูมิได้อย่างไร

 คุณสามารถซ่อนแกนแผนภูมิได้โดยการตั้งค่า`setHidden(true)` คุณสมบัติของแกน
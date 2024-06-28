---
title: สร้างและปรับแต่งแผนภูมิโดยใช้รูปร่าง
linktitle: สร้างและปรับแต่งแผนภูมิโดยใช้รูปร่าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างและปรับแต่งแผนภูมิโดยใช้รูปร่างในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-charts/create-chart-using-shape/
---

บทช่วยสอนนี้จะอธิบายวิธีสร้างแผนภูมิโดยใช้รูปร่างในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่คุณต้องการบันทึกเอกสาร

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และ DocumentBuilder
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder` คัดค้านการทำงานกับเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกและกำหนดค่ารูปร่างแผนภูมิ
 แทรกรูปร่างแผนภูมิลงในเอกสารโดยใช้`InsertChart` วิธีการของ`DocumentBuilder` วัตถุ วัตถุ ตั้งค่าประเภทแผนภูมิและขนาดที่ต้องการ

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## ขั้นตอนที่ 4: ปรับแต่งแผนภูมิ
ปรับแต่งแผนภูมิโดยการแก้ไขคุณสมบัติต่างๆ เช่น ชื่อแผนภูมิและคำอธิบายแผนภูมิ

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithCharts.CreateChartUsingShape.docx"

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับสร้างแผนภูมิโดยใช้รูปร่างโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// โปรดทราบว่าหากมีการระบุค่าว่างหรือค่าว่างเป็นข้อความชื่อเรื่อง ชื่อที่สร้างขึ้นโดยอัตโนมัติจะปรากฏขึ้น
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

แค่นั้นแหละ! คุณสร้างแผนภูมิโดยใช้รูปร่างในเอกสาร Word ได้สำเร็จโดยใช้ Aspose.Words สำหรับ .NET

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างแผนภูมิโดยใช้รูปร่างในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET โดยทำตามคำแนะนำทีละขั้นตอน คุณสามารถแทรกและกำหนดค่ารูปร่างแผนภูมิ ปรับแต่งลักษณะที่ปรากฏ และบันทึกเอกสารได้ Aspose.Words สำหรับ .NET มีชุดคุณลักษณะที่ครอบคลุมสำหรับการประมวลผลคำด้วยเอกสารและแผนภูมิ Word ทำให้คุณสามารถสร้างแผนภูมิที่ดูเป็นมืออาชีพและดึงดูดสายตาได้โดยตรงในแอปพลิเคชัน .NET ของคุณ

### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 ฉันสามารถสร้างแผนภูมิในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
ได้ ด้วย Aspose.Words สำหรับ .NET คุณสามารถสร้างแผนภูมิในเอกสาร Word โดยทางโปรแกรมได้ Aspose.Words มี API และฟังก์ชันต่างๆ เพื่อแทรกแผนภูมิประเภทต่างๆ ปรับแต่งรูปลักษณ์ และจัดการข้อมูลแผนภูมิ

#### ไตรมาสที่ 2 Aspose.Words สำหรับ .NET รองรับแผนภูมิประเภทใดบ้าง
Aspose.Words สำหรับ .NET รองรับแผนภูมิหลายประเภท รวมถึงแผนภูมิเส้น แผนภูมิแท่ง แผนภูมิวงกลม แผนภูมิพื้นที่ แผนภูมิกระจาย และอื่นๆ คุณสามารถเลือกประเภทแผนภูมิที่เหมาะสมโดยอิงตามข้อกำหนดข้อมูลและการแสดงภาพของคุณ

#### ไตรมาสที่ 3 ฉันสามารถปรับแต่งรูปลักษณ์ของแผนภูมิที่สร้างขึ้นได้หรือไม่?
ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิที่สร้างขึ้นได้โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถปรับเปลี่ยนคุณสมบัติ เช่น ชื่อแผนภูมิ ตำแหน่งคำอธิบาย ป้ายข้อมูล ป้ายแกน สี และองค์ประกอบภาพอื่นๆ เพื่อให้ตรงกับความต้องการด้านการออกแบบและการจัดรูปแบบเฉพาะของคุณ

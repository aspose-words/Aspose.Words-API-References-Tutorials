---
title: เพิ่มค่าวันที่และเวลาให้กับแกนของแผนภูมิ
linktitle: เพิ่มค่าวันที่และเวลาให้กับแกนของแผนภูมิ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มค่าวันที่ เวลา ให้กับแกนของแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-charts/date-time-values-to-axis/
---

บทช่วยสอนนี้จะอธิบายวิธีเพิ่มค่าวันที่ เวลา ให้กับแกนของแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## ขั้นตอนที่ 4: เพิ่มข้อมูลลงในแผนภูมิ
เพิ่มข้อมูลลงในชุดแผนภูมิ รวมถึงค่าวันที่และเวลา

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## ขั้นตอนที่ 5: กำหนดค่าแกน
กำหนดค่าแกน X ของแผนภูมิเพื่อแสดงค่าวันที่ เวลา

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithCharts.DateTimeValuesToAxis.docx"

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับค่าวันที่ เวลา ถึงแกน โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// ตั้งค่าหน่วยหลักเป็นหนึ่งสัปดาห์ และหน่วยย่อยเป็นหนึ่งวัน
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

โค้ดตัวอย่างนี้จะสร้างเอกสาร Word ใหม่ แทรกแผนภูมิคอลัมน์ที่มีค่าวันที่ เวลา บนแกน X และบันทึกเอกสารลงในไดเร็กทอรีที่ระบุ

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเพิ่มค่าวันที่และเวลาลงในแกนของแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET โดยทำตามคำแนะนำทีละขั้นตอน คุณจะสามารถสร้างแผนภูมิ เพิ่มค่าวันที่ เวลา ให้กับซีรีส์ และกำหนดค่าแกนให้แสดงค่าวันที่ เวลา ได้อย่างถูกต้อง Aspose.Words สำหรับ .NET มอบชุดคุณสมบัติอันทรงพลังสำหรับการประมวลผลคำด้วยแผนภูมิในเอกสาร Word ช่วยให้คุณสามารถแสดงและแสดงภาพข้อมูลด้วยค่าวันที่และเวลาได้อย่างมีประสิทธิภาพ

### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 ฉันสามารถเพิ่มค่าวันที่และเวลาลงในแกนของแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
ได้ ด้วย Aspose.Words สำหรับ .NET คุณสามารถเพิ่มและแสดงค่าวันที่ เวลา บนแกนของแผนภูมิในเอกสาร Word ได้ Aspose.Words มี API และฟังก์ชันการทำงานเพื่อทำงานกับแผนภูมิต่างๆ และปรับแต่งรูปลักษณ์ รวมถึงประเภทที่จัดการค่าวันที่ เวลา บนแกน

#### ไตรมาสที่ 2 ฉันจะเพิ่มค่าวันที่และเวลาลงในชุดแผนภูมิได้อย่างไร
 หากต้องการเพิ่มค่าวันที่ เวลา ให้กับชุดแผนภูมิ คุณสามารถใช้`Add`วิธีการอนุกรมของแผนภูมิ ระบุอาร์เรย์ของค่าวันที่และเวลาเป็นข้อมูลหมวดหมู่ (แกน X) พร้อมด้วยค่าอนุกรมที่สอดคล้องกัน ซึ่งจะทำให้คุณสามารถลงจุดข้อมูลด้วยค่าวันที่ เวลา บนแผนภูมิได้

#### ไตรมาสที่ 3 ฉันจะกำหนดค่าแกนให้แสดงค่าวันที่และเวลาได้อย่างไร
 คุณสามารถกำหนดค่าแกนของแผนภูมิให้แสดงค่าวันที่ เวลา ได้โดยการตั้งค่าคุณสมบัติที่เหมาะสม ตัวอย่างเช่น คุณสามารถระบุค่าต่ำสุดและค่าสูงสุดสำหรับแกนได้โดยใช้`Scaling.Minimum` และ`Scaling.Maximum` คุณสมบัติตามลำดับ นอกจากนี้ คุณยังสามารถตั้งค่าหน่วยหลักและหน่วยรองเพื่อกำหนดช่วงเวลาและเครื่องหมายถูกสำหรับแกนได้

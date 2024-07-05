---
title: กำหนดคุณสมบัติแกน XY ในแผนภูมิ
linktitle: กำหนดคุณสมบัติแกน XY ในแผนภูมิ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีกำหนดคุณสมบัติแกน XY ในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET มีการสาธิตตัวเลือกการปรับแต่งสำหรับแกน X และ Y
type: docs
weight: 10
url: /th/net/programming-with-charts/define-xyaxis-properties/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อกำหนดคุณสมบัติสำหรับแกน X และ Y ในแผนภูมิ ซอร์สโค้ดที่ให้มาสาธิตวิธีสร้างแผนภูมิ เพิ่มข้อมูลชุด และปรับแต่งคุณสมบัติของแกน

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้โดยใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่เอกสารเอาต์พุตจะถูกบันทึก

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และแทรกแผนภูมิ

 สร้างใหม่`Document` วัตถุและก`DocumentBuilder` เพื่อสร้างเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 จากนั้น แทรกแผนภูมิลงในเอกสารโดยใช้`InsertChart` วิธีการของ`DocumentBuilder`- ในตัวอย่างนี้ เราจะแทรกแผนภูมิพื้นที่

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## ขั้นตอนที่ 3: เพิ่มข้อมูลซีรีส์ลงในแผนภูมิ

เพิ่มข้อมูลซีรีส์ลงในแผนภูมิ ในตัวอย่างนี้ เราจะเพิ่มจุดข้อมูล 5 จุดพร้อมวันที่และค่าที่สอดคล้องกัน

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## ขั้นตอนที่ 4: ปรับแต่งคุณสมบัติแกน X และ Y

 หากต้องการปรับแต่งคุณสมบัติของแกน X และ Y ให้เข้าไปที่`ChartAxis` วัตถุที่เกี่ยวข้องกับแผนภูมิ

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 ปรับเปลี่ยนคุณสมบัติของ`xAxis` และ`yAxis`วัตถุเพื่อตั้งค่าตัวเลือกที่ต้องการสำหรับแกน X และ Y ในตัวอย่างนี้ เราจะสาธิตคุณสมบัติทั่วไปบางอย่างที่สามารถปรับแต่งได้

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

 สุดท้าย ให้บันทึกเอกสารลงในไดเร็กทอรีที่ระบุโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

ซึ่งจะทำให้การดำเนินการกำหนดคุณสมบัติแกน XY ในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับกำหนดคุณสมบัติ XYAxis โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// แทรกแผนภูมิ
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// เปลี่ยนแกน X ให้เป็นหมวดหมู่แทนวันที่ ดังนั้นจุดทั้งหมดจะถูกใส่โดยมีช่วงเวลาเท่ากันบนแกน X
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //วัดในหน่วยแสดงผลของแกน Y (หลักร้อย)
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีกำหนดคุณสมบัติสำหรับแกน X และ Y ในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณจะสามารถสร้างแผนภูมิ เพิ่มข้อมูลชุด และปรับแต่งคุณสมบัติของแกนให้ตรงกับความต้องการเฉพาะของคุณได้ Aspose.Words สำหรับ .NET มี API ที่ครอบคลุมสำหรับการประมวลผลคำพร้อมแผนภูมิในเอกสาร Word ซึ่งช่วยให้คุณสามารถจัดการแง่มุมต่างๆ ของแผนภูมิ รวมถึงแกนด้วย

โดยเข้าไปที่`ChartAxis` วัตถุที่เกี่ยวข้องกับแผนภูมิ คุณสามารถแก้ไขคุณสมบัติได้ เช่น ประเภทหมวดหมู่ กากบาทของแกน เครื่องหมายถูก ตำแหน่งป้ายกำกับ การปรับขนาด และอื่นๆ ความยืดหยุ่นนี้ช่วยให้คุณสามารถปรับแต่งรูปลักษณ์และการทำงานของแกนของแผนภูมิเพื่อนำเสนอข้อมูลของคุณได้อย่างมีประสิทธิภาพ

ด้วยการใช้ Aspose.Words สำหรับ .NET คุณสามารถรวมความสามารถในการสร้างแผนภูมิและการปรับแต่งเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น และทำให้การสร้างเอกสารที่ดูเป็นมืออาชีพเป็นอัตโนมัติด้วยการแสดงภาพข้อมูลที่สมบูรณ์

### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีการประมวลผลเอกสารที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และบันทึกเอกสาร Word โดยทางโปรแกรมในแอปพลิเคชัน .NET โดยมีคุณสมบัติที่หลากหลายสำหรับการประมวลผลคำพร้อมองค์ประกอบเอกสาร รวมถึงแผนภูมิ

#### ไตรมาสที่ 2 ฉันจะติดตั้ง Aspose.Words สำหรับ .NET ได้อย่างไร
คุณสามารถติดตั้ง Aspose.Words สำหรับ .NET ได้ด้วยการดาวน์โหลดโดยใช้ตัวจัดการแพ็คเกจ NuGet ใน Visual Studio เพียงค้นหา "Aspose.Words" ในตัวจัดการแพ็คเกจ NuGet และติดตั้งลงในโปรเจ็กต์ของคุณ

#### ไตรมาสที่ 3 ฉันสามารถปรับแต่งด้านอื่นๆ ของแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET มอบความสามารถที่ครอบคลุมสำหรับการปรับแต่งแง่มุมต่างๆ ของแผนภูมิ นอกเหนือจากการกำหนดคุณสมบัติของแกนแล้ว คุณยังสามารถแก้ไขประเภทแผนภูมิ ชุดข้อมูล คำอธิบาย ชื่อเรื่อง พื้นที่ลงจุด ป้ายชื่อข้อมูล และองค์ประกอบอื่นๆ มากมายของแผนภูมิได้ API ให้การควบคุมลักษณะและลักษณะการทำงานของแผนภูมิอย่างละเอียด

#### ไตรมาสที่ 4 ฉันสามารถสร้างแผนภูมิประเภทต่างๆ โดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
 ใช่ Aspose.Words สำหรับ .NET รองรับแผนภูมิหลายประเภท รวมถึงพื้นที่ แท่ง เส้น พาย กระจาย และอื่นๆ คุณสามารถใช้`ChartType` การแจงนับเพื่อระบุประเภทแผนภูมิที่ต้องการเมื่อแทรกรูปร่างแผนภูมิลงในเอกสาร Word

#### คำถามที่ 5 ฉันสามารถบันทึกแผนภูมิในรูปแบบอื่นได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถบันทึกเอกสารที่มีแผนภูมิในรูปแบบต่างๆ เช่น DOCX, PDF, HTML และอื่นๆ คุณสามารถเลือกรูปแบบที่เหมาะสมตามความต้องการของคุณและใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร

#### คำถามที่ 6 ฉันสามารถใช้เทคนิคเหล่านี้กับแผนภูมิหลายแผนภูมิในเอกสารได้หรือไม่
 ได้ คุณสามารถใช้เทคนิคเหล่านี้กับแผนภูมิหลายแผนภูมิในเอกสารได้โดยการทำซ้ำขั้นตอนที่จำเป็นสำหรับแต่ละแผนภูมิ คุณสามารถสร้างแยกต่างหาก`Chart` และ`ChartAxis` ออบเจ็กต์สำหรับแต่ละแผนภูมิและปรับแต่งคุณสมบัติตามนั้น Aspose.Words สำหรับ .NET ให้การสนับสนุนอย่างเต็มที่สำหรับการประมวลผลคำด้วยแผนภูมิหลายแผนภูมิในเอกสารเดียว
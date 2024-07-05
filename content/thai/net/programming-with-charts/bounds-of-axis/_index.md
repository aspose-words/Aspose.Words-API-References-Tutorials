---
title: ขอบเขตของแกนในแผนภูมิ
linktitle: ขอบเขตของแกนในแผนภูมิ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีกำหนดขอบเขตของแกนในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET เพื่อควบคุมช่วงของค่าที่แสดงบนแกน
type: docs
weight: 10
url: /th/net/programming-with-charts/bounds-of-axis/
---

บทช่วยสอนนี้จะอธิบายวิธีตั้งค่าขอบเขตของแกนในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ด้วยการแทรกแผนภูมิ เพิ่มข้อมูลชุดข้อมูล และกำหนดค่ามาตราส่วนแกน คุณสามารถกำหนดค่าต่ำสุดและสูงสุดสำหรับแกนได้

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
 สร้างอินสแตนซ์ใหม่ของ`Document` คลาสและก`DocumentBuilder`คัดค้านการทำงานกับเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกและกำหนดค่าแผนภูมิ
 แทรกแผนภูมิลงในเอกสารโดยใช้`InsertChart` วิธีการของ`DocumentBuilder` วัตถุ. ตั้งค่าประเภทแผนภูมิและขนาดที่ต้องการ

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ขั้นตอนที่ 4: เพิ่มข้อมูลซีรี่ส์
ล้างชุดข้อมูลที่มีอยู่ในแผนภูมิและเพิ่มข้อมูลชุดข้อมูลใหม่ ในตัวอย่างนี้ เราเพิ่มชุดที่มีป้ายกำกับ "รายการที่ 1" ให้กับ "รายการที่ 5" และค่าที่เกี่ยวข้อง

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## ขั้นตอนที่ 5: กำหนดขอบเขตของแกน
 กำหนดค่ามาตราส่วนของแกน Y โดยการตั้งค่าต่ำสุดและสูงสุดโดยใช้`Scaling.Minimum` และ`Scaling.Maximum` คุณสมบัติของแกน

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## ขั้นตอนที่ 6: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithCharts.BoundsOfAxis.docx"

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Bounds Of Axis โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
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

แค่นั้นแหละ! คุณได้ตั้งค่าขอบเขตของแกนในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีตั้งค่าขอบเขตของแกนในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET โดยทำตามคำแนะนำทีละขั้นตอน คุณสามารถแทรกและกำหนดค่าแผนภูมิ เพิ่มข้อมูลชุด และกำหนดค่าต่ำสุดและสูงสุดสำหรับมาตราส่วนแกนได้ Aspose.Words สำหรับ .NET มอบ API ที่ทรงพลังและยืดหยุ่นสำหรับการประมวลผลคำด้วยเอกสาร Word ช่วยให้คุณสร้างแผนภูมิแบบไดนามิกและดึงดูดสายตาได้อย่างง่ายดาย


### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words for .NET เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร Word โดยทางโปรแกรมได้ มีคุณลักษณะและฟังก์ชันการทำงานมากมายสำหรับการสร้าง จัดการ และบันทึกเอกสาร Word

#### ไตรมาสที่ 2 ฉันจะติดตั้ง Aspose.Words สำหรับ .NET ได้อย่างไร
หากต้องการติดตั้ง Aspose.Words สำหรับ .NET คุณสามารถใช้ตัวจัดการแพ็คเกจ NuGet ใน Visual Studio ได้ เพียงค้นหา "Aspose.Words" ในตัวจัดการแพ็คเกจ NuGet และติดตั้งลงในโปรเจ็กต์ของคุณ

#### ไตรมาสที่ 3 ฉันสามารถใช้ Aspose.Words สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
ไม่ Aspose.Words สำหรับ .NET ได้รับการออกแบบมาเป็นพิเศษสำหรับแอปพลิเคชัน .NET ทำงานร่วมกับภาษาการเขียนโปรแกรมเช่น C# และ VB.NET

#### ไตรมาสที่ 4 มีข้อกำหนดเบื้องต้นอื่นใดสำหรับการใช้ Aspose.Words สำหรับ .NET หรือไม่
นอกจากการติดตั้งไลบรารี Aspose.Words สำหรับ .NET แล้ว คุณควรมีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และการประมวลผลคำด้วยเอกสาร Word ความคุ้นเคยกับ .NET Framework ก็จะเป็นประโยชน์เช่นกัน

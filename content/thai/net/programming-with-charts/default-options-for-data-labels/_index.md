---
title: ตั้งค่าตัวเลือกเริ่มต้นสำหรับป้ายกำกับข้อมูลในแผนภูมิ
linktitle: ตั้งค่าตัวเลือกเริ่มต้นสำหรับป้ายกำกับข้อมูลในแผนภูมิ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าตัวเลือกเริ่มต้นสำหรับป้ายกำกับข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-charts/default-options-for-data-labels/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อตั้งค่าตัวเลือกเริ่มต้นสำหรับป้ายชื่อข้อมูลในแผนภูมิ รหัสที่ให้มาสาธิตวิธีการสร้างแผนภูมิ เพิ่มชุดข้อมูล และปรับแต่งป้ายกำกับข้อมูลโดยใช้ Aspose.Words

## ขั้นตอนที่ 1: ตั้งค่าโครงการ

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้โดยใช้ตัวจัดการแพ็คเกจ NuGet เพื่อติดตั้ง
- เส้นทางไดเร็กทอรีเอกสารที่เอกสารเอาต์พุตจะถูกบันทึก

## ขั้นตอนที่ 2: สร้างเอกสารใหม่และแทรกแผนภูมิ

 ก่อนอื่นเรามาสร้างอันใหม่กัน`Document` วัตถุและก`DocumentBuilder` เพื่อสร้างเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ต่อไป เราจะแทรกแผนภูมิลงในเอกสารโดยใช้`InsertChart` วิธีการของ`DocumentBuilder`- ในตัวอย่างนี้ เราจะแทรกแผนภูมิวงกลม

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## ขั้นตอนที่ 3: เพิ่มชุดข้อมูลลงในแผนภูมิ

ตอนนี้ เรามาเพิ่มชุดข้อมูลลงในแผนภูมิกัน ในตัวอย่างนี้ เราจะเพิ่มสามหมวดหมู่และค่าที่สอดคล้องกัน

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## ขั้นตอนที่ 4: ปรับแต่งป้ายกำกับข้อมูล

 ในการปรับแต่งป้ายกำกับข้อมูลในแผนภูมิ เราจำเป็นต้องเข้าถึง`ChartDataLabelCollection` วัตถุที่เกี่ยวข้องกับซีรีส์

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 จากนั้นเราก็สามารถปรับเปลี่ยนคุณสมบัติต่างๆ ของ`labels`วัตถุเพื่อตั้งค่าตัวเลือกที่ต้องการสำหรับป้ายกำกับข้อมูล ในตัวอย่างนี้ เราจะเปิดใช้งานการแสดงเปอร์เซ็นต์และค่า ปิดใช้งานเส้นตัวนำ และตั้งค่าตัวคั่นแบบกำหนดเอง

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

 สุดท้าย เราบันทึกเอกสารลงในไดเร็กทอรีที่ระบุโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

การดำเนินการนี้ทำให้การดำเนินการตั้งค่าตัวเลือกเริ่มต้นสำหรับป้ายกำกับข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับตัวเลือกเริ่มต้นสำหรับป้ายกำกับข้อมูลโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีการตั้งค่าตัวเลือกเริ่มต้นสำหรับป้ายชื่อข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอน คุณจะสามารถสร้างแผนภูมิ เพิ่มชุดข้อมูล และปรับแต่งป้ายชื่อข้อมูลให้ตรงกับความต้องการเฉพาะของคุณได้ Aspose.Words สำหรับ .NET มี API ที่มีประสิทธิภาพสำหรับการประมวลผลคำพร้อมแผนภูมิในเอกสาร Word ช่วยให้คุณสามารถจัดการองค์ประกอบแผนภูมิต่างๆ และบรรลุรูปลักษณ์และฟังก์ชันการทำงานที่ต้องการได้

 โดยการกำหนดคุณสมบัติของ`ChartDataLabelCollection`ออบเจ็กต์ที่เกี่ยวข้องกับชุดแผนภูมิ คุณสามารถควบคุมการแสดงป้ายข้อมูลได้ รวมถึงตัวเลือกต่างๆ เช่น การแสดงเปอร์เซ็นต์ ค่า เส้นผู้นำ และตัวคั่นแบบกำหนดเอง ความยืดหยุ่นนี้ช่วยให้คุณสามารถนำเสนอข้อมูลได้อย่างมีประสิทธิภาพและปรับปรุงการแสดงแผนภูมิของคุณ

### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words for .NET เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และบันทึกเอกสาร Word โดยทางโปรแกรมโดยใช้แอปพลิเคชัน .NET โดยมีคุณสมบัติที่หลากหลายสำหรับการประมวลผลคำพร้อมองค์ประกอบเอกสาร รวมถึงแผนภูมิ

#### ไตรมาสที่ 2 ฉันจะติดตั้ง Aspose.Words สำหรับ .NET ได้อย่างไร
คุณสามารถติดตั้ง Aspose.Words สำหรับ .NET ได้ด้วยการดาวน์โหลดโดยใช้ตัวจัดการแพ็คเกจ NuGet ใน Visual Studio เพียงค้นหา "Aspose.Words" ในตัวจัดการแพ็คเกจ NuGet และติดตั้งลงในโปรเจ็กต์ของคุณ

#### ไตรมาสที่ 3 ฉันสามารถปรับแต่งด้านอื่นๆ ของแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถปรับแต่งแง่มุมต่างๆ ของแผนภูมิได้ เช่น ประเภทแผนภูมิ ป้ายแกน คำอธิบาย พื้นที่ลงจุด และอื่นๆ คุณสามารถเข้าถึงและแก้ไขคุณสมบัติต่างๆ ของออบเจ็กต์แผนภูมิเพื่อให้ได้รูปลักษณ์และลักษณะการทำงานที่ต้องการ

#### ไตรมาสที่ 4 ฉันสามารถบันทึกแผนภูมิในรูปแบบอื่นได้หรือไม่
 ใช่ Aspose.Words สำหรับ .NET รองรับการบันทึกเอกสารที่มีแผนภูมิในรูปแบบต่างๆ รวมถึง DOCX, PDF, HTML และอื่นๆ คุณสามารถเลือกรูปแบบที่เหมาะสมได้ตามความต้องการและการใช้งานของคุณ`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร

#### คำถามที่ 5 ฉันสามารถใช้เทคนิคเหล่านี้กับแผนภูมิประเภทอื่นได้หรือไม่
ใช่ เทคนิคที่อธิบายไว้ในบทช่วยสอนนี้สามารถนำไปใช้กับแผนภูมิประเภทอื่นๆ ที่ Aspose.Words สำหรับ .NET รองรับ กุญแจสำคัญคือการเข้าถึงออบเจ็กต์และคุณสมบัติที่เกี่ยวข้องเฉพาะกับประเภทแผนภูมิที่คุณใช้ในการประมวลผลคำ
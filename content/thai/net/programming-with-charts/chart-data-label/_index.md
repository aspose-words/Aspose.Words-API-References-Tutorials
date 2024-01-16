---
title: ปรับแต่งป้ายกำกับข้อมูลแผนภูมิ
linktitle: ปรับแต่งป้ายกำกับข้อมูลแผนภูมิ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มและปรับแต่งป้ายข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET เพื่อให้ข้อมูลเพิ่มเติมเกี่ยวกับจุดข้อมูล
type: docs
weight: 10
url: /th/net/programming-with-charts/chart-data-label/
---

บทช่วยสอนนี้จะอธิบายวิธีเพิ่มและปรับแต่งป้ายกำกับข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET ป้ายข้อมูลให้ข้อมูลเพิ่มเติมเกี่ยวกับจุดข้อมูลในแผนภูมิ

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

## ขั้นตอนที่ 3: แทรกและกำหนดค่าแผนภูมิ
 แทรกแผนภูมิลงในเอกสารโดยใช้`InsertChart` วิธีการของ`DocumentBuilder` วัตถุ. ตั้งค่าประเภทแผนภูมิและขนาดที่ต้องการ

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## ขั้นตอนที่ 4: ปรับแต่งป้ายกำกับข้อมูล
เข้าถึงคอลเลกชันป้ายกำกับข้อมูลของชุดแผนภูมิและแก้ไขคุณสมบัติต่างๆ เพื่อปรับแต่งรูปลักษณ์ของป้ายกำกับข้อมูล

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

## ขั้นตอนที่ 5: บันทึกเอกสาร
 บันทึกเอกสารไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithCharts.ChartDataLabel.docx"

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Chart Data Label โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// ตามค่าเริ่มต้น เมื่อคุณเพิ่มป้ายข้อมูลลงในจุดข้อมูลในแผนภูมิวงกลม เส้นตัวนำจะแสดงสำหรับป้ายข้อมูลที่เป็น
	// อยู่นอกจุดสิ้นสุดของจุดข้อมูล เส้นตัวนำสร้างการเชื่อมโยงภาพระหว่างป้ายข้อมูลกับป้ายชื่อข้อมูล
	// จุดข้อมูลที่สอดคล้องกัน
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

แค่นั้นแหละ! คุณได้เพิ่มและปรับแต่งป้ายกำกับข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเพิ่มและปรับแต่งป้ายข้อมูลในแผนภูมิโดยใช้ Aspose.Words สำหรับ .NET โดยทำตามคำแนะนำทีละขั้นตอน คุณสามารถแทรกแผนภูมิ เข้าถึงคอลเลกชันป้ายชื่อข้อมูล และแก้ไขคุณสมบัติเพื่อปรับแต่งลักษณะที่ปรากฏของป้ายชื่อข้อมูลได้ Aspose.Words สำหรับ .NET มอบ API ที่มีประสิทธิภาพสำหรับการประมวลผลคำด้วยเอกสารและแผนภูมิ Word ทำให้คุณสามารถสร้างแผนภูมิที่น่าดึงดูดสายตาและให้ข้อมูลด้วยป้ายชื่อข้อมูลที่ปรับแต่งได้

### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 ป้ายชื่อข้อมูลในแผนภูมิคืออะไร
ป้ายข้อมูลในแผนภูมิให้ข้อมูลเพิ่มเติมเกี่ยวกับจุดข้อมูลที่แสดงในแผนภูมิ พวกเขาสามารถแสดงค่า หมวดหมู่ ชื่อชุดข้อมูล เปอร์เซ็นต์ หรือรายละเอียดอื่นๆ ที่เกี่ยวข้อง ขึ้นอยู่กับประเภทแผนภูมิและการกำหนดค่า

#### ไตรมาสที่ 2 ฉันสามารถปรับแต่งลักษณะที่ปรากฏของป้ายกำกับข้อมูลได้หรือไม่
ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของป้ายชื่อข้อมูลในแผนภูมิได้ Aspose.Words สำหรับ .NET มีตัวเลือกในการปรับเปลี่ยนคุณสมบัติต่างๆ ของป้ายข้อมูล เช่น การแสดงคีย์คำอธิบาย เส้นผู้นำ ชื่อหมวดหมู่ ชื่อซีรีส์ ค่า และอื่นๆ คุณยังสามารถตั้งค่าตัวคั่นและจัดรูปแบบฉลากเพื่อให้ตรงตามความต้องการเฉพาะของคุณได้

#### ไตรมาสที่ 3 ฉันสามารถเพิ่มป้ายกำกับข้อมูลให้กับแผนภูมิประเภทใดก็ได้หรือไม่
ได้ คุณสามารถเพิ่มป้ายกำกับข้อมูลลงในแผนภูมิประเภทต่างๆ ได้ รวมถึงแผนภูมิแท่ง แผนภูมิวงกลม แผนภูมิเส้น และอื่นๆ กระบวนการเพิ่มและปรับแต่งป้ายข้อมูลอาจแตกต่างกันเล็กน้อย ขึ้นอยู่กับประเภทแผนภูมิและไลบรารีหรือเครื่องมือที่คุณใช้

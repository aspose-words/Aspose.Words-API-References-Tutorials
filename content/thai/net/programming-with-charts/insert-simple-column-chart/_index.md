---
title: แทรกแผนภูมิคอลัมน์อย่างง่ายในเอกสาร Word
linktitle: แทรกแผนภูมิคอลัมน์อย่างง่ายในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกแผนภูมิคอลัมน์อย่างง่ายลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-charts/insert-simple-column-chart/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อแทรกแผนภูมิคอลัมน์อย่างง่ายลงในเอกสาร ซอร์สโค้ดที่ให้มาสาธิตวิธีการสร้างแผนภูมิ เพิ่มข้อมูลชุด และบันทึกเอกสาร

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

 ต่อไปให้ใช้`InsertChart` วิธีการของ`DocumentBuilder` เพื่อแทรกแผนภูมิคอลัมน์ลงในเอกสาร คุณสามารถระบุประเภทและขนาดแผนภูมิที่แตกต่างกันได้ตามความต้องการของคุณ

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ขั้นตอนที่ 3: เพิ่มข้อมูลซีรีส์ลงในแผนภูมิ

เพิ่มข้อมูลซีรีส์ลงในแผนภูมิ ในตัวอย่างนี้ เราจะเพิ่มหลายชุดโดยแต่ละหมวดหมู่มี 2 หมวดหมู่

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

 สุดท้าย ให้บันทึกเอกสารลงในไดเร็กทอรีที่ระบุโดยใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

การดำเนินการแทรกแผนภูมิคอลัมน์อย่างง่ายโดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกแผนภูมิคอลัมน์อย่างง่ายโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// คุณสามารถระบุประเภทและขนาดแผนภูมิที่แตกต่างกันได้
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// ลบซีรี่ส์ที่สร้างโดยค่าเริ่มต้น
	seriesColl.Clear();
	// สร้างอาร์เรย์ชื่อหมวดหมู่ ในบทช่วยสอนนี้เรามีสองหมวดหมู่
	string[] categories = new string[] { "Category 1", "Category 2" };
	// โปรดทราบว่าอาร์เรย์ข้อมูลต้องไม่ว่างเปล่า และอาร์เรย์ต้องมีขนาดเท่ากัน
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแทรกแผนภูมิคอลัมน์อย่างง่ายลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถสร้างเอกสารใหม่ แทรกแผนภูมิคอลัมน์ เพิ่มชุดข้อมูลหลายชุดพร้อมหมวดหมู่และค่าที่เกี่ยวข้อง และบันทึกเอกสารด้วยแผนภูมิได้

Aspose.Words สำหรับ .NET มอบ API ที่ทรงพลังและยืดหยุ่นสำหรับการประมวลผลคำพร้อมแผนภูมิในเอกสาร Word แผนภูมิคอลัมน์แบบง่ายเป็นวิธีที่มีประสิทธิภาพในการแสดงและเปรียบเทียบข้อมูลในหมวดหมู่ต่างๆ ด้วย Aspose.Words สำหรับ .NET คุณสามารถสร้างแผนภูมิคอลัมน์ด้วยข้อมูลที่กำหนดเอง เพิ่มชุดข้อมูลหลายชุดสำหรับการเปรียบเทียบด้วยภาพ และปรับแต่งรูปลักษณ์ของแผนภูมิตามความต้องการของคุณ

ด้วยการใช้ Aspose.Words สำหรับ .NET คุณสามารถทำให้กระบวนการสร้างเอกสารด้วยแผนภูมิคอลัมน์เป็นอัตโนมัติ ช่วยประหยัดเวลาและความพยายามในการสร้างเอกสารด้วยตนเอง ไลบรารีมีแผนภูมิหลายประเภท รวมถึงแผนภูมิคอลัมน์แบบธรรมดา และมีตัวเลือกการปรับแต่งต่างๆ เพื่อปรับแต่งรูปลักษณ์ของแผนภูมิให้เหมาะกับความต้องการของคุณ

### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 แผนภูมิคอลัมน์คืออะไร?
แผนภูมิคอลัมน์เป็นแผนภูมิประเภทหนึ่งที่แสดงข้อมูลโดยใช้แถบแนวตั้งที่มีความสูงต่างกัน แต่ละคอลัมน์แสดงถึงหมวดหมู่ และความสูงของคอลัมน์สอดคล้องกับค่าของหมวดหมู่นั้น โดยทั่วไปแล้วแผนภูมิคอลัมน์ใช้เพื่อเปรียบเทียบข้อมูลในหมวดหมู่ต่างๆ หรือเพื่อติดตามการเปลี่ยนแปลงเมื่อเวลาผ่านไป

#### ไตรมาสที่ 2 ฉันสามารถเพิ่มหลายชุดลงในแผนภูมิคอลัมน์ได้หรือไม่
ได้ เมื่อใช้ Aspose.Words สำหรับ .NET คุณสามารถเพิ่มหลายชุดข้อมูลลงในแผนภูมิคอลัมน์ได้ แต่ละชุดจะแสดงชุดจุดข้อมูลพร้อมหมวดหมู่และค่าตามลำดับ ด้วยการเพิ่มหลายชุด คุณสามารถเปรียบเทียบและวิเคราะห์ชุดข้อมูลต่างๆ ภายในแผนภูมิคอลัมน์เดียวกันได้ ทำให้มีมุมมองข้อมูลที่ครอบคลุม

#### ไตรมาสที่ 3 ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิคอลัมน์ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถปรับแต่งรูปลักษณ์ต่างๆ ของแผนภูมิคอลัมน์ได้ คุณสามารถแก้ไขคุณสมบัติ เช่น สีของชุดข้อมูล ป้ายแกน ป้ายข้อมูล และการจัดรูปแบบพื้นที่แผนภูมิ ไลบรารีมีชุด API มากมายเพื่อควบคุมองค์ประกอบภาพของแผนภูมิและสร้างรูปลักษณ์ที่ปรับแต่งให้เหมาะกับความต้องการของคุณ

#### ไตรมาสที่ 4 ฉันสามารถบันทึกเอกสารด้วยแผนภูมิคอลัมน์ที่แทรกในรูปแบบอื่นได้หรือไม่
 ใช่ Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถบันทึกเอกสารด้วยการแทรกแผนภูมิคอลัมน์ในรูปแบบต่างๆ เช่น DOCX, PDF, HTML และอื่นๆ คุณสามารถเลือกรูปแบบผลลัพธ์ที่ต้องการได้ตามความต้องการและการใช้งานของคุณ`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร แผนภูมิคอลัมน์ที่แทรกจะถูกบันทึกลงในเอกสารที่บันทึกไว้

#### คำถามที่ 5 ฉันสามารถแก้ไขข้อมูลและลักษณะของแผนภูมิคอลัมน์หลังจากแทรกแล้วได้หรือไม่
ได้ หลังจากแทรกแผนภูมิคอลัมน์ลงในเอกสารแล้ว คุณสามารถแก้ไขข้อมูลและลักษณะที่ปรากฏได้โดยใช้ API ที่ Aspose.Words สำหรับ .NET มอบให้ คุณสามารถอัปเดตข้อมูลชุดข้อมูลด้วยหมวดหมู่และค่าใหม่ เปลี่ยนสีและการจัดรูปแบบของคอลัมน์ ปรับแต่งคุณสมบัติของแกน และใช้ตัวเลือกการจัดรูปแบบต่างๆ เพื่อสร้างแผนภูมิแบบไดนามิกและสวยงามในเอกสาร Word ของคุณ
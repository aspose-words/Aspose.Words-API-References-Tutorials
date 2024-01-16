---
title: แทรกแผนภูมิคอลัมน์ในเอกสาร Word
linktitle: แทรกแผนภูมิคอลัมน์ในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกแผนภูมิคอลัมน์ลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-charts/insert-column-chart/
---

บทช่วยสอนนี้จะอธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อแทรกแผนภูมิคอลัมน์ลงในเอกสาร ซอร์สโค้ดที่ให้มาสาธิตวิธีการสร้างแผนภูมิ เพิ่มข้อมูลชุด และบันทึกเอกสาร

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

 ต่อไปให้ใช้`InsertChart` วิธีการของ`DocumentBuilder` เพื่อแทรกแผนภูมิคอลัมน์ลงในเอกสาร

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ขั้นตอนที่ 3: เพิ่มข้อมูลซีรีส์ลงในแผนภูมิ

เพิ่มข้อมูลซีรีส์ลงในแผนภูมิ ในตัวอย่างนี้ เราจะเพิ่มสองหมวดหมู่และค่าที่เกี่ยวข้องกัน

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

 สุดท้าย ให้บันทึกเอกสารลงในไดเร็กทอรีที่ระบุโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

การดำเนินการแทรกแผนภูมิคอลัมน์โดยใช้ Aspose.Words สำหรับ .NET เสร็จสมบูรณ์

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกแผนภูมิคอลัมน์โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแทรกแผนภูมิคอลัมน์ลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถสร้างเอกสารใหม่ แทรกแผนภูมิคอลัมน์ เพิ่มข้อมูลชุดข้อมูล และบันทึกเอกสารด้วยแผนภูมิได้

Aspose.Words สำหรับ .NET มี API ที่มีประสิทธิภาพสำหรับการประมวลผลคำพร้อมแผนภูมิในเอกสาร Word โดยทั่วไปแล้วแผนภูมิคอลัมน์จะใช้เพื่อแสดงและเปรียบเทียบข้อมูลระหว่างหมวดหมู่หรือกลุ่มต่างๆ ด้วย Aspose.Words สำหรับ .NET คุณสามารถสร้างแผนภูมิคอลัมน์ที่แสดงภาพข้อมูลของคุณอย่างมีประสิทธิภาพและให้ข้อมูลเชิงลึกอันมีค่าได้อย่างง่ายดาย

ด้วยการใช้ Aspose.Words สำหรับ .NET คุณสามารถทำให้กระบวนการสร้างเอกสารด้วยแผนภูมิคอลัมน์เป็นอัตโนมัติ ช่วยประหยัดเวลาและความพยายามในการสร้างเอกสารด้วยตนเอง ไลบรารีมีประเภทแผนภูมิและตัวเลือกการปรับแต่งที่หลากหลาย ช่วยให้คุณสร้างแผนภูมิที่ดึงดูดสายตาและมีข้อมูลมากมายในเอกสาร Word ของคุณ

### คำถามที่พบบ่อย

#### ไตรมาสที่ 1 แผนภูมิคอลัมน์คืออะไร?
แผนภูมิคอลัมน์คือแผนภูมิประเภทหนึ่งที่แสดงข้อมูลในแถบแนวตั้งหรือคอลัมน์ โดยทั่วไปแต่ละคอลัมน์จะแสดงถึงหมวดหมู่หรือกลุ่ม และความสูงหรือความยาวของคอลัมน์จะระบุค่าของข้อมูลที่เกี่ยวข้องกับหมวดหมู่นั้น โดยทั่วไปแล้วแผนภูมิคอลัมน์ใช้เพื่อเปรียบเทียบข้อมูลในหมวดหมู่ต่างๆ หรือเพื่อติดตามการเปลี่ยนแปลงเมื่อเวลาผ่านไป

#### ไตรมาสที่ 2 ฉันสามารถเพิ่มหลายชุดลงในแผนภูมิคอลัมน์ได้หรือไม่
ใช่ คุณสามารถเพิ่มหลายชุดข้อมูลลงในแผนภูมิคอลัมน์ได้โดยใช้ Aspose.Words สำหรับ .NET แต่ละชุดจะแสดงชุดจุดข้อมูลพร้อมหมวดหมู่และค่าตามลำดับ ด้วยการเพิ่มหลายชุด คุณสามารถเปรียบเทียบและวิเคราะห์ชุดข้อมูลต่างๆ ภายในแผนภูมิเดียวกันได้ ทำให้มีมุมมองข้อมูลที่ครอบคลุม

#### ไตรมาสที่ 3 ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิคอลัมน์ได้หรือไม่
ใช่ การใช้ Aspose.Words สำหรับ .NET คุณสามารถปรับแต่งลักษณะต่างๆ ของลักษณะที่ปรากฏของแผนภูมิคอลัมน์ได้ คุณสามารถแก้ไขคุณสมบัติ เช่น สีของชุดข้อมูล ป้ายแกน ความกว้างของคอลัมน์ และการจัดรูปแบบพื้นที่แผนภูมิได้ ไลบรารีมีชุด API มากมายเพื่อควบคุมองค์ประกอบภาพของแผนภูมิและสร้างรูปลักษณ์ที่ปรับแต่งให้เหมาะกับความต้องการของคุณ

#### ไตรมาสที่ 4 ฉันสามารถบันทึกเอกสารด้วยแผนภูมิคอลัมน์ที่แทรกในรูปแบบอื่นได้หรือไม่
 ใช่ Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถบันทึกเอกสารด้วยการแทรกแผนภูมิคอลัมน์ในรูปแบบต่างๆ เช่น DOCX, PDF, HTML และอื่นๆ คุณสามารถเลือกรูปแบบผลลัพธ์ที่ต้องการได้ตามความต้องการของคุณ และใช้`Save` วิธีการของ`Document` วัตถุเพื่อบันทึกเอกสาร แผนภูมิคอลัมน์ที่แทรกจะถูกเก็บไว้ในเอกสารที่บันทึกไว้

#### คำถามที่ 5 ฉันสามารถแก้ไขข้อมูลและลักษณะของแผนภูมิคอลัมน์หลังจากแทรกแล้วได้หรือไม่
ได้ หลังจากแทรกแผนภูมิคอลัมน์ลงในเอกสารแล้ว คุณสามารถแก้ไขข้อมูลและลักษณะที่ปรากฏได้โดยใช้ API ที่ Aspose.Words สำหรับ .NET มอบให้ คุณสามารถอัปเดตข้อมูลชุด เปลี่ยนสีคอลัมน์ ปรับแต่งคุณสมบัติของแกน และใช้ตัวเลือกการจัดรูปแบบเพื่อสร้างแผนภูมิแบบไดนามิกและเชิงโต้ตอบในเอกสาร Word ของคุณ
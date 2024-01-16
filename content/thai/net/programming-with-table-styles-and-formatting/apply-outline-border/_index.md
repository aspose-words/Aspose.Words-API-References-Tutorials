---
title: ใช้เส้นขอบเค้าร่าง
linktitle: ใช้เส้นขอบเค้าร่าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการใช้เส้นขอบเค้าร่างกับตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อใช้เส้นขอบเค้าร่างกับตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการจัดการเส้นขอบตารางในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่เก็บเอกสาร Word ของคุณ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: อัปโหลดเอกสาร
 ถัดไป คุณต้องโหลดเอกสาร Word ลงในอินสแตนซ์ของ`Document` ระดับ.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ขั้นตอนที่ 3: เข้าถึงตาราง
 หากต้องการใช้เส้นขอบเค้าร่าง เราจำเป็นต้องเข้าถึงตารางในเอกสาร ที่`Table` class แสดงถึงตารางใน Aspose.Words

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## ขั้นตอนที่ 4: จัดตารางให้อยู่ตรงกลางหน้า
 ตอนนี้เราสามารถจัดตำแหน่งตารางให้อยู่ตรงกลางหน้าได้โดยใช้`Alignment` คุณสมบัติของตาราง

```csharp
table. Alignment = Table Alignment. Center;
```

## ขั้นตอนที่ 5: ลบเส้นขอบตารางที่มีอยู่
ในการเริ่มต้นด้วยเส้นขอบเค้าร่างใหม่ เราต้องลบเส้นขอบที่มีอยู่ทั้งหมดออกจากตารางก่อน ซึ่งสามารถทำได้โดยใช้`ClearBorders()` วิธี.

```csharp
table. ClearBorders();
```

## ขั้นตอนที่ 6: กำหนดเส้นขอบสีเขียวรอบๆ ตาราง
 ตอนนี้เราสามารถกำหนดเส้นขอบสีเขียวรอบโต๊ะได้โดยใช้`SetBorder()` วิธีการสำหรับแต่ละด้านของตาราง ในตัวอย่างนี้ เราใช้เส้นขอบประเภท "เดี่ยว" ที่มีความหนา 1.5 จุดและมีสีเขียว

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## ขั้นตอนที่ 7: เติมเซลล์ด้วยสีพื้นหลัง
เพื่อปรับปรุงการนำเสนอด้วยภาพของตาราง เราสามารถเติมเซลล์ด้วยสีพื้นหลังพื้นได้

ความคิด. ในตัวอย่างนี้ เราใช้สีเขียวอ่อน

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## ขั้นตอนที่ 8: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจะบันทึกเอกสารที่แก้ไขลงในไฟล์ คุณสามารถเลือกชื่อและตำแหน่งที่เหมาะสมสำหรับเอกสารเอาต์พุตได้

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

ขอแสดงความยินดี! ตอนนี้คุณได้ใช้เส้นขอบเค้าร่างกับตารางโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับ Apply Outline Border โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// จัดตารางให้อยู่ตรงกลางหน้า
	table.Alignment = TableAlignment.Center;
	//ล้างเส้นขอบที่มีอยู่ออกจากตาราง
	table.ClearBorders();
	// กำหนดเส้นขอบสีเขียวรอบโต๊ะแต่ไม่ใช่ด้านใน
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// เติมเซลล์ด้วยสีทึบสีเขียวอ่อน
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้เส้นขอบเค้าร่างกับตารางโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถรวมฟังก์ชันนี้เข้ากับโปรเจ็กต์ C# ของคุณได้อย่างง่ายดาย การจัดการการจัดรูปแบบตารางเป็นส่วนสำคัญของการประมวลผลเอกสาร และ Aspose.Words ก็มี API ที่ทรงพลังและยืดหยุ่นเพื่อให้บรรลุเป้าหมายนี้ ด้วยความรู้นี้ คุณสามารถปรับปรุงการนำเสนอด้วยภาพในเอกสาร Word ของคุณและปฏิบัติตามข้อกำหนดเฉพาะได้
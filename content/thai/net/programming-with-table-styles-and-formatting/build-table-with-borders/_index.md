---
title: สร้างตารางที่มีเส้นขอบ
linktitle: สร้างตารางที่มีเส้นขอบ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการสร้างตารางที่มีเส้นขอบโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อสร้างตารางที่มีเส้นขอบโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีสร้างตารางที่มีเส้นขอบแบบกำหนดเองในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่เก็บเอกสาร Word ของคุณ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารที่มีอยู่
 ถัดไป คุณต้องโหลดเอกสาร Word ที่มีอยู่ลงในอินสแตนซ์ของ`Document` ชั้นเรียน

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ขั้นตอนที่ 3: เข้าถึงตารางและลบเส้นขอบที่มีอยู่
 ในการเริ่มสร้างตารางที่มีเส้นขอบ เราจำเป็นต้องนำทางไปยังตารางในเอกสารและลบเส้นขอบที่มีอยู่ออก ที่`ClearBorders()` วิธีการลบเส้นขอบทั้งหมดออกจากตาราง

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## ขั้นตอนที่ 4: ตั้งค่าเส้นขอบตาราง
 ตอนนี้เราสามารถกำหนดเส้นขอบของตารางโดยใช้`SetBorders()` วิธี. ในตัวอย่างนี้ เราใช้เส้นขอบสีเขียวที่มีความหนา 1.5 จุด

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## ขั้นตอนที่ 5: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจะบันทึกเอกสารที่แก้ไขลงในไฟล์ คุณสามารถเลือกชื่อและตำแหน่งที่เหมาะสมสำหรับเอกสารเอาต์พุตได้

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

ขอแสดงความยินดี! ตอนนี้คุณได้สร้างตารางที่มีเส้นขอบแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับ Build Table With Borders โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//ล้างเส้นขอบที่มีอยู่ออกจากตาราง
	table.ClearBorders();
	// กำหนดเส้นขอบสีเขียวรอบๆ และภายในตาราง
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างตารางที่มีเส้นขอบโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถปรับแต่งเส้นขอบตารางในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับปรุงการนำเสนอด้วยภาพในเอกสาร Word ของคุณและตอบสนองความต้องการเฉพาะได้
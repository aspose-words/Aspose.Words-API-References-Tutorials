---
title: แก้ไขการจัดรูปแบบแถว
linktitle: แก้ไขการจัดรูปแบบแถว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการเปลี่ยนการจัดรูปแบบแถวตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อเปลี่ยนการจัดรูปแบบของแถวตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีเปลี่ยนเส้นขอบ ความสูง และตัวแบ่งบรรทัดของแถวตารางในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่ตั้งเอกสาร Word ของคุณ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารที่มีอยู่
 ถัดไป คุณต้องโหลดเอกสาร Word ที่มีอยู่ลงในอินสแตนซ์ของ`Document` ชั้นเรียน

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ขั้นตอนที่ 3: เข้าถึงบรรทัดเพื่อแก้ไข
 หากต้องการเปลี่ยนการจัดรูปแบบของแถวตาราง เราจำเป็นต้องนำทางไปยังแถวที่ต้องการในตาราง เราใช้`GetChild()` และ`FirstRow` วิธีการรับการอ้างอิงถึงแถวแรกของตาราง

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## ขั้นตอนที่ 4: เปลี่ยนการจัดรูปแบบแถว
 ตอนนี้เราสามารถเปลี่ยนการจัดรูปแบบแถวโดยใช้คุณสมบัติของ`RowFormat` ชั้นเรียน ตัวอย่างเช่น เราสามารถลบเส้นขอบ ตั้งค่าความสูงอัตโนมัติ และอนุญาตให้แบ่งบรรทัดได้

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### ตัวอย่างซอร์สโค้ดสำหรับการปรับเปลี่ยนการจัดรูปแบบแถวโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// ดึงข้อมูลแถวแรกในตาราง
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเปลี่ยนการจัดรูปแบบของแถวตารางโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถปรับเส้นขอบ ความสูง และการแบ่งบรรทัดของแถวในตารางในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับแต่งเค้าโครงภาพของตารางได้ตามความต้องการเฉพาะของคุณ
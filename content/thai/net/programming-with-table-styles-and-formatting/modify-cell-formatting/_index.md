---
title: แก้ไขการจัดรูปแบบเซลล์
linktitle: แก้ไขการจัดรูปแบบเซลล์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการเปลี่ยนการจัดรูปแบบของเซลล์ในตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/modify-cell-formatting/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อเปลี่ยนการจัดรูปแบบเซลล์โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีเปลี่ยนความกว้าง การวางแนว และสีพื้นหลังของเซลล์ในตารางในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

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

## ขั้นตอนที่ 3: ไปที่เซลล์เพื่อแก้ไข
 หากต้องการเปลี่ยนการจัดรูปแบบของเซลล์ เราจำเป็นต้องนำทางไปยังเซลล์ที่ต้องการในตาราง เราใช้`GetChild()` และ`FirstRow.FirstCell` วิธีการรับการอ้างอิงไปยังเซลล์แรกของอาร์เรย์แรก

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## ขั้นตอนที่ 4: เปลี่ยนการจัดรูปแบบเซลล์
 ตอนนี้เราสามารถเปลี่ยนการจัดรูปแบบเซลล์โดยใช้คุณสมบัติของ`CellFormat` ชั้นเรียน ตัวอย่างเช่น เราสามารถกำหนดความกว้างของเซลล์ การวางแนวข้อความ และสีพื้นหลังได้

```csharp
firstCell.CellFormat.Width = 30;
firstCell.CellFormat.Orientation = TextOrientation.Downward;
firstCell.CellFormat.Shading.ForegroundPatternColor = Color.LightGreen;
```

### ตัวอย่างซอร์สโค้ดสำหรับการปรับเปลี่ยนการจัดรูปแบบเซลล์โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	firstCell.CellFormat.Width = 30;
	firstCell.CellFormat.Orientation = TextOrientation.Downward;
	firstCell.CellFormat.Shading.ForegroundPatternColor = Color.LightGreen;
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเปลี่ยนการจัดรูปแบบของเซลล์ในตารางโดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถปรับความกว้างของเซลล์ การวางแนว และสีพื้นหลังในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับแต่งเค้าโครงภาพของตารางได้ตามความต้องการเฉพาะของคุณ
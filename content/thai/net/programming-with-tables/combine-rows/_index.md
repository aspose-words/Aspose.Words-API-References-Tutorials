---
title: รวมแถว
linktitle: รวมแถว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรวมแถวของตารางในเอกสาร Word กับ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/combine-rows/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อรวมแถวของตารางในเอกสาร Word เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถจัดการและรวมแถวของตารางในเอกสาร Word ของคุณโดยทางโปรแกรมได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสารและเข้าถึงตาราง
ในการเริ่มการประมวลผลคำด้วยตาราง เราจำเป็นต้องโหลดเอกสารที่มีตารางเหล่านั้นและเข้าถึงได้ ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Tables.docx");

// การเข้าถึงตาราง
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การรวมแถวของตาราง
ต่อไป เราจะรวมแถวของตารางที่สองเข้ากับส่วนท้ายของตารางแรก ใช้รหัสต่อไปนี้:

```csharp
// การรวมแถวของตาราง
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 ในที่นี้เราใช้ก`while` วนซ้ำเพื่อวนซ้ำแถวทั้งหมดของอาร์เรย์ที่สองและเพิ่มที่ส่วนท้ายของอาร์เรย์แรกโดยใช้`Add` วิธี. ต่อไป เราจะลบตารางที่สองออกจากเอกสารโดยใช้`Remove` วิธี.

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจำเป็นต้องบันทึกเอกสารที่แก้ไขด้วยแถวตารางที่รวมกัน ใช้รหัสต่อไปนี้:

```csharp
// บันทึกเอกสารที่แก้ไข
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการรวมแถวโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// แถวจากตารางที่สองจะถูกต่อท้ายตารางแรก
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// ผนวกแถวทั้งหมดจากตารางปัจจุบันเข้ากับตารางถัดไป
	// ด้วยจำนวนเซลล์และความกว้างที่แตกต่างกันสามารถรวมเป็นตารางเดียวได้
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรวมแถวของตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้โค้ด C# ที่ให้มา คุณสามารถจัดการแถวของตารางในเอกสาร Word ของคุณโดยทางโปรแกรมได้ คุณลักษณะนี้ช่วยให้คุณสามารถผสานและจัดระเบียบข้อมูลของคุณลงในตารางได้อย่างมีประสิทธิภาพ
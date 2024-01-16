---
title: เก็บโต๊ะไว้ด้วยกัน
linktitle: เก็บโต๊ะไว้ด้วยกัน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรวมตารางไว้ด้วยกันในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/keep-table-together/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีรวมตารางเข้าด้วยกันในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถรักษาตารางให้คงเดิมได้โดยไม่ต้องแยกเป็นหลายหน้าในเอกสาร Word ของคุณ

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสารและดึงข้อมูลตาราง
ในการเริ่มการประมวลผลคำด้วยตาราง เราจำเป็นต้องโหลดเอกสารและดึงตารางที่เราต้องการเก็บไว้ด้วยกัน ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// ดึงโต๊ะกลับมา
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: เปิดใช้งานตัวเลือก "KeepWithNext"
ในการเก็บตารางไว้ด้วยกันและป้องกันไม่ให้แยกออกเป็นหลายหน้า เราจำเป็นต้องเปิดใช้งานตัวเลือก "KeepWithNext" สำหรับแต่ละย่อหน้าในตาราง ยกเว้นย่อหน้าสุดท้ายของแถวสุดท้ายของตาราง ใช้รหัสต่อไปนี้:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

ที่นี่เราวนซ้ำแต่ละเซลล์ในตารางและเปิดใช้งานตัวเลือก "KeepWithNext" สำหรับแต่ละย่อหน้าในเซลล์ ยกเว้นย่อหน้าสุดท้ายของแถวสุดท้ายในตาราง

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้ายเราจำเป็นต้องบันทึกเอกสารที่แก้ไขโดยจัดตารางไว้ด้วยกัน ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับ Keep Table Together โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// เราจำเป็นต้องเปิดใช้งาน KeepWithNext สำหรับทุกย่อหน้าในตารางเพื่อป้องกันไม่ให้แตกข้ามหน้า
	// ยกเว้นย่อหน้าสุดท้ายในแถวสุดท้ายของตาราง
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีจัดตารางไว้ด้วยกันในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณสามารถรักษาตารางให้ไม่เสียหายและป้องกันไม่ให้แยกเป็นหลายหน้าในเอกสารของคุณ คุณลักษณะนี้ช่วยให้คุณควบคุมลักษณะและเค้าโครงของตารางในเอกสารของคุณได้มากขึ้น
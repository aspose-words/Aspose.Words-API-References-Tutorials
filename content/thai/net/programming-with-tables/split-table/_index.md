---
title: แยกโต๊ะ
linktitle: แยกโต๊ะ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแยกตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/split-table/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีแยกตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถแยกตารางออกจากแถวบางแถวในเอกสาร Word ของคุณได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร
เมื่อต้องการเริ่มการประมวลผลคำกับเอกสาร ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Tables.docx");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ และระบุชื่อไฟล์ที่ถูกต้อง

## ขั้นตอนที่ 3: การแบ่งโต๊ะ
ต่อไปเราจะแยกตารางออกจากแถวหนึ่ง ใช้รหัสต่อไปนี้:

```csharp
// ดึงตารางแรก
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// การกำหนดเส้นที่จะแบ่งตาราง
Row row = firstTable.Rows[2];

// สร้างคอนเทนเนอร์ใหม่สำหรับตารางแยก
Table table = (Table)firstTable.Clone(false);

// ใส่ภาชนะหลังโต๊ะเดิม
firstTable.ParentNode.InsertAfter(table, firstTable);

// เพิ่มย่อหน้าบัฟเฟอร์เพื่อรักษาระยะห่างระหว่างตาราง
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// ย้ายแถวจากตารางต้นฉบับไปยังตารางแยก
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

ที่นี่เราใช้เอกสารเพื่อดึงตารางแรกจากโหนดเอกสาร จากนั้นเราจะกำหนดแถวที่เราต้องการแยกตาราง ในตัวอย่างนี้คือแถวที่สาม (ดัชนี 2) จากนั้นเราสร้างคอนเทนเนอร์ใหม่โดยการโคลนตารางต้นฉบับแล้วแทรกไว้หลังตารางต้นฉบับ นอกจากนี้เรายังเพิ่มย่อหน้าบัฟเฟอร์เพื่อรักษาระยะห่างระหว่างสองตาราง จากนั้นเราจะย้ายแถวจากตารางเดิมไปยังตารางแยกโดยใช้การวนซ้ำแบบ do- While จนกระทั่งเราไปถึงแถวที่ระบุ

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
ในที่สุดเราก็ต้องบันทึก

  แก้ไขเอกสารด้วยตารางแยก ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับ Split Table โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// เราจะแบ่งตารางเป็นแถวที่สาม (รวม)
Row row = firstTable.Rows[2];
// สร้างคอนเทนเนอร์ใหม่สำหรับตารางแยก
Table table = (Table) firstTable.Clone(false);
// ใส่ภาชนะหลังของเดิม
firstTable.ParentNode.InsertAfter(table, firstTable);
// เพิ่มย่อหน้าบัฟเฟอร์เพื่อให้แน่ใจว่าตารางจะแยกจากกัน
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแบ่งตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้โค้ด C# ที่ให้มา คุณจะสามารถแยกตารางออกจากบรรทัดใดบรรทัดหนึ่งในเอกสาร Word ของคุณได้อย่างง่ายดาย
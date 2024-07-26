---
title: รูปแบบแถวปิดการใช้งานการแบ่งข้ามหน้า
linktitle: รูปแบบแถวปิดการใช้งานการแบ่งข้ามหน้า
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีปิดการใช้งานตัวแบ่งบรรทัดสำหรับตารางในหลายหน้าในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/row-format-disable-break-across-pages/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีปิดการใช้งานตัวแบ่งบรรทัดของตารางแบบหลายหน้าในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถปิดใช้การแบ่งบรรทัดสำหรับแถวทั้งหมดในตารางในเอกสาร Word ได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร
เมื่อต้องการเริ่มการประมวลผลคำกับเอกสาร ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ และระบุชื่อไฟล์ที่ถูกต้อง

## ขั้นตอนที่ 3: ปิดใช้งานตัวแบ่งแถวของตาราง
ต่อไป เราจะปิดการใช้งานการแบ่งแถวสำหรับแถวทั้งหมดในตาราง ใช้รหัสต่อไปนี้:

```csharp
// ดึงโต๊ะกลับมา
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// ปิดใช้งานตัวแบ่งแถวสำหรับแถวทั้งหมดในตาราง
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 ที่นี่เราใช้เอกสารเพื่อดึงข้อมูลตารางแรก จากนั้นวนซ้ำแถวทั้งหมดในตารางโดยใช้ foreach loop ภายในลูป เราปิดการใช้งานการแบ่งแถวสำหรับแต่ละแถวโดยการตั้งค่า`RowFormat.AllowBreakAcrossPages`ทรัพย์สินเพื่อ`false`.

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้ายนี้ เราจำเป็นต้องบันทึกเอกสารที่แก้ไขโดยปิดใช้งานตัวแบ่งบรรทัดของตาราง ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับรูปแบบแถวปิดการใช้งานการแบ่งข้ามหน้าโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// ปิดใช้การแยกหน้าสำหรับแถวทั้งหมดในตาราง
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปิดการใช้งานตัวแบ่งบรรทัดของตารางแบบหลายหน้าในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณจะสามารถนำการปิดใช้งานนี้ไปใช้กับตารางในเอกสาร Word ของคุณได้
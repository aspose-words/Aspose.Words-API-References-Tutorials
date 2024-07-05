---
title: ดึงข้อมูลประเภทความกว้างที่ต้องการ
linktitle: ดึงข้อมูลประเภทความกว้างที่ต้องการ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีดึงข้อมูลประเภทและค่าความกว้างที่ต้องการของเซลล์ในตาราง Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/retrieve-preferred-width-type/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีดึงข้อมูลประเภทความกว้างที่ต้องการและค่าจากเซลล์ตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถดึงข้อมูลประเภทความกว้างที่ต้องการ (สัมบูรณ์ สัมพันธ์ หรืออัตโนมัติ) และค่าของประเภทนั้นสำหรับเซลล์ใดเซลล์หนึ่งในตารางเอกสาร Word ของคุณ

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

## ขั้นตอนที่ 3: การดึงข้อมูลประเภทความกว้างและค่าที่ต้องการ
ต่อไป เราจะดึงข้อมูลประเภทความกว้างที่ต้องการและค่าสำหรับเซลล์ตารางที่ระบุ ใช้รหัสต่อไปนี้:

```csharp
// ดึงโต๊ะกลับมา
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// เปิดใช้งานการปรับตารางอัตโนมัติ
table. AllowAutoFit = true;

// ดึงข้อมูลเซลล์แรกของแถวแรก
Cell firstCell = table.FirstRow.FirstCell;

// ดึงข้อมูลประเภทความกว้างที่ต้องการและค่าของมัน
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

ที่นี่เราใช้เอกสารเพื่อดึงข้อมูลตารางแรก จากนั้นเราเปิดใช้งานตารางอัตโนมัติที่พอดีกับ`AllowAutoFit` คุณสมบัติ. จากนั้นเราจะดึงข้อมูลเซลล์แรกของแถวแรกของตาราง จากเซลล์นี้ เราสามารถดึงข้อมูลประเภทความกว้างที่ต้องการได้ด้วย`PreferredWidth.Type` ทรัพย์สินและมูลค่าของมันด้วย`PreferredWidth.Value` คุณสมบัติ.

### ตัวอย่างซอร์สโค้ดสำหรับการดึงข้อมูลประเภทความกว้างที่ต้องการโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีดึงข้อมูลประเภทความกว้างที่ต้องการและค่าจากเซลล์ตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้โค้ด C# ที่ให้มา คุณสามารถดึงข้อมูลนี้สำหรับเซลล์ที่ต้องการในตารางเอกสาร Word ของคุณได้
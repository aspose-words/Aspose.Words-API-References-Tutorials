---
title: ตั้งค่าตำแหน่งแนวนอนหรือแนวตั้งสัมพัทธ์
linktitle: ตั้งค่าตำแหน่งแนวนอนหรือแนวตั้งสัมพัทธ์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการตั้งค่าตำแหน่งแนวนอนหรือแนวตั้งสัมพัทธ์ของตารางในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีการตั้งค่าตำแหน่งแนวนอนหรือแนวตั้งสัมพัทธ์ของตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถกำหนดตำแหน่งสัมพัทธ์ในแนวนอนหรือแนวตั้งของตารางในเอกสาร Word ได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร
เมื่อต้องการเริ่มการประมวลผลคำกับเอกสาร ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ และระบุชื่อไฟล์ที่ถูกต้อง

## ขั้นตอนที่ 3: การตั้งค่าตำแหน่งสัมพันธ์ของตาราง
ต่อไป เราจะตั้งค่าตำแหน่งแนวนอนหรือแนวตั้งสัมพัทธ์ของตาราง ใช้รหัสต่อไปนี้:

```csharp
// ดึงโต๊ะกลับมา
Table table = doc.FirstSection.Body.Tables[0];

//คำจำกัดความของตำแหน่งแนวนอนสัมพัทธ์ของตาราง
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// กำหนดตำแหน่งแนวตั้งสัมพัทธ์ของตาราง
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 ที่นี่เราใช้เอกสารเพื่อดึงข้อมูลตารางแรกจากเนื้อหาของส่วนแรก ต่อไป เรากำหนดตำแหน่งแนวนอนของตารางด้วย`HorizontalAnchor` คุณสมบัติโดยใช้`RelativeHorizontalPosition.Column` ค่า. ในทำนองเดียวกัน เรากำหนดตำแหน่งแนวตั้งสัมพัทธ์ของตารางด้วย`VerticalAnchor` คุณสมบัติโดยใช้`RelativeVerticalPosition.Page` ค่า.

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้ายนี้ เราจำเป็นต้องบันทึกเอกสารที่แก้ไขโดยกำหนดตำแหน่งสัมพัทธ์ของตาราง ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าตำแหน่งแนวนอนหรือแนวตั้งสัมพัทธ์โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการตั้งค่าตำแหน่งแนวนอนหรือแนวตั้งสัมพัทธ์ของตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณจะสามารถใช้ตำแหน่งสัมพันธ์นี้กับตารางของคุณในเอกสาร Word ได้
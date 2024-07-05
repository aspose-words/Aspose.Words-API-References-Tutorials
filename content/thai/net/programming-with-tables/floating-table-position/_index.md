---
title: ตำแหน่งตารางลอยตัว
linktitle: ตำแหน่งตารางลอยตัว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีวางตำแหน่งตารางในตำแหน่งลอยในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/floating-table-position/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อวางตำแหน่งตารางในตำแหน่งลอยตัวในเอกสาร Word เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถควบคุมตำแหน่งและการจัดตำแหน่งของตารางลอยในเอกสาร Word ของคุณโดยทางโปรแกรม

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสารและเข้าถึงตาราง
ในการเริ่มการประมวลผลคำด้วยตาราง เราจำเป็นต้องโหลดเอกสารที่มีอยู่และเข้าถึงได้ ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// การเข้าถึงอาร์เรย์
Table table = doc.FirstSection.Body.Tables[0];
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ นอกจากนี้ ตรวจสอบให้แน่ใจว่าเอกสารมีตารางที่จะวางในตำแหน่งลอยตัว

## ขั้นตอนที่ 3: การวางตำแหน่งกระดานลอย
ต่อไป เราจะวางตำแหน่งตารางในตำแหน่งลอยตัวโดยใช้คุณสมบัติที่ได้รับจาก Aspose.Words สำหรับ .NET ใช้รหัสต่อไปนี้:

```csharp
// การจัดตำแหน่งโต๊ะลอยน้ำ
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 ในที่นี้เราใช้`AbsoluteHorizontalDistance` คุณสมบัติเพื่อกำหนดระยะห่างแนวนอนสัมบูรณ์ของตารางจากขอบด้านซ้ายของหน้า เรายังใช้`RelativeVerticalAlignment` คุณสมบัติเพื่อตั้งค่าการจัดตำแหน่งแนวตั้งที่สัมพันธ์กันของตารางกับเนื้อหาโดยรอบ

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้าย เราจำเป็นต้องบันทึกเอกสารที่แก้ไขโดยให้ตารางอยู่ในตำแหน่งลอยตัว ใช้รหัสต่อไปนี้:

```csharp
// บันทึกเอกสารที่แก้ไข
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับตำแหน่งตารางลอยตัวโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีวางตำแหน่งตารางในตำแหน่งลอยในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และการใช้โค้ด C# ที่ให้มา คุณสามารถควบคุมตำแหน่งและการจัดตำแหน่งของตารางลอยในเอกสาร Word ของคุณโดยทางโปรแกรมได้
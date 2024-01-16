---
title: แทรกตารางจาก Html
linktitle: แทรกตารางจาก Html
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกตารางจาก HTML ลงในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/insert-table-from-html/
---

ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีแทรกตารางลงในเอกสาร Word จาก HTML โดยใช้ Aspose.Words สำหรับ .NET เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถแทรกตารางจาก HTML ลงในเอกสาร Word ของคุณโดยทางโปรแกรมได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: การสร้างเอกสารและการเริ่มต้นตัวสร้างเอกสาร
เมื่อต้องการเริ่มการประมวลผลคำด้วยตัวสร้างเอกสารและเอกสาร ให้ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// การสร้างเอกสาร
Document doc = new Document();

// เริ่มต้นตัวสร้างเอกสาร
DocumentBuilder builder = new DocumentBuilder(doc);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การแทรกตารางจาก HTML
ต่อไปเราจะแทรกตารางลงในเอกสารโดยใช้โค้ด HTML ใช้รหัสต่อไปนี้:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 ในที่นี้เราใช้`InsertHtml` วิธีการสร้างเอกสารเพื่อแทรก HTML ที่มีตาราง HTML ที่ระบุจะสร้างตารางที่มีสองแถวและสองเซลล์ในแต่ละแถว คุณสามารถปรับแต่งเนื้อหาของตารางได้โดยแก้ไขโค้ด HTML ตามความต้องการของคุณ

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข
สุดท้าย เราต้องบันทึกเอกสารที่แก้ไขโดยแทรกตารางจาก HTML ใช้รหัสต่อไปนี้:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องสำหรับเอกสารเอาต์พุต

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกตารางจาก Html โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// โปรดทราบว่า AutoFitSettings ใช้ไม่ได้กับตารางที่แทรกจาก HTML
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแทรกตารางลงในเอกสาร Word จาก HTML โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และนำโค้ด C# ที่ให้มาไปใช้ คุณสามารถแทรกตารางจาก HTML ลงในเอกสาร Word ของคุณโดยทางโปรแกรมได้ คุณลักษณะนี้ช่วยให้คุณสามารถแปลงและนำเข้าข้อมูลแบบตารางจากแหล่ง HTML ลงในเอกสาร Word ของคุณได้

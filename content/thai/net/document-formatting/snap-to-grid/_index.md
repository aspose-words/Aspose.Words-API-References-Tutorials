---
title: จัดชิดตารางในเอกสาร Word
linktitle: จัดชิดตารางในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ของ Snap to Grid ในฟีเจอร์เอกสาร word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/document-formatting/snap-to-grid/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีใช้ฟีเจอร์จัดชิดตารางในเอกสารเวิร์ดด้วย Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและใช้การเปลี่ยนแปลง

## ขั้นตอนที่ 1: การสร้างและกำหนดค่าเอกสาร

ในการเริ่มต้น ให้สร้างเอกสารใหม่และออบเจ็กต์ DocumentBuilder ที่เกี่ยวข้อง มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การจัดแนวตาราง

ตอนนี้เราจะใช้การจัดแนวตารางกับย่อหน้าเฉพาะและแบบอักษรที่ใช้ในย่อหน้า มีวิธีดังนี้:

```csharp
// เปิดใช้งานการจัดแนวตารางสำหรับย่อหน้า
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// เขียนข้อความในย่อหน้า
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// เปิดใช้งานการจัดแนวตารางสำหรับแบบอักษรที่ใช้ในย่อหน้า
par.Runs[0].Font.SnapToGrid = true;
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Snap To Grid โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับคุณสมบัติ Snap to Grid พร้อม Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// ปรับเค้าโครงให้เหมาะสมเมื่อพิมพ์อักขระเอเชีย
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

ด้วยโค้ดนี้ คุณจะสามารถจัดแนวข้อความของคุณให้เป็นตารางและปรับลักษณะที่ปรากฏของเอกสารของคุณให้เหมาะสมโดยใช้ Aspose.Words สำหรับ .NET


## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการใช้ฟีเจอร์จัดชิดตารางในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ คุณสามารถเปิดใช้งานการจัดแนวตารางสำหรับย่อหน้าและแบบอักษรได้ ทำให้มั่นใจได้ว่าเค้าโครงเอกสารจะดูสวยงามและมีการจัดระเบียบอย่างดี

### คำถามที่พบบ่อย

#### ถาม: Snap to Grid ในเอกสาร Word คืออะไร

ตอบ: จัดชิดตารางเป็นฟีเจอร์ในเอกสาร Word ที่จะจัดแนววัตถุ เช่น ข้อความและรูปภาพ เข้ากับระบบตาราง ช่วยให้มั่นใจได้ถึงการวางตำแหน่งที่แม่นยำและการจัดตำแหน่งที่เรียบร้อย โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับเลย์เอาต์ที่ซับซ้อนหรืออักขระเอเชีย

#### ถาม: Snap to Grid ปรับปรุงรูปลักษณ์ของเอกสารอย่างไร

ตอบ: จัดชิดตารางจะปรับปรุงลักษณะที่ปรากฏของเอกสารโดยรักษาการจัดแนววัตถุให้สอดคล้องกัน ช่วยป้องกันไม่ให้ข้อความและองค์ประกอบอื่นๆ ปรากฏไม่ตรงแนวหรือทับซ้อนกัน ส่งผลให้ได้เลย์เอาต์ที่สวยงามและเป็นมืออาชีพ

#### ถาม: ฉันสามารถใช้ Snap to Grid กับย่อหน้าหรือแบบอักษรเฉพาะในเอกสารของฉันได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้ Snap to Grid กับย่อหน้าหรือแบบอักษรเฉพาะในเอกสารของคุณได้ โดยเปิดใช้งาน`ParagraphFormat.SnapToGrid` และ`Font.SnapToGrid` คุณสมบัติ คุณสามารถควบคุมการจัดแนวตารางตามย่อหน้าหรือต่อแบบอักษรได้

#### ถาม: Aspose.Words สำหรับ .NET เป็นเพียงโซลูชันเดียวสำหรับ Snap to Grid ในเอกสาร Word หรือไม่

ตอบ: Aspose.Words สำหรับ .NET เป็นหนึ่งในโซลูชันที่พร้อมใช้งานสำหรับการใช้งาน Snap to Grid ในเอกสาร Word มีวิธีและเครื่องมืออื่นๆ แต่ Aspose.Words สำหรับ .NET มี API และฟีเจอร์ที่มีประสิทธิภาพสำหรับการทำงานกับเอกสาร Word โดยทางโปรแกรม

#### ถาม: ฉันสามารถใช้ Aspose.Words สำหรับ .NET เพื่อทำงานร่วมกับคุณสมบัติเอกสารอื่นๆ ได้หรือไม่

ตอบ: ใช่ Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการทำงานกับเอกสาร Word มันมีฟังก์ชันสำหรับการจัดการข้อความ เค้าโครงหน้า ตาราง รูปภาพ และอื่นๆ คุณสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

---
title: การจัดรูปแบบรายการหลายระดับในเอกสาร Word
linktitle: การจัดรูปแบบรายการหลายระดับในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างรายการหลายระดับและใช้การจัดรูปแบบที่กำหนดเองในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/document-formatting/multilevel-list-formatting/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีใช้การจัดรูปแบบรายการหลายระดับในฟีเจอร์เอกสารเวิร์ดด้วย Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและใช้การเปลี่ยนแปลง

## ขั้นตอนที่ 1: การสร้างและกำหนดค่าเอกสาร

ในการเริ่มต้น ให้สร้างเอกสารใหม่และออบเจ็กต์ DocumentBuilder ที่เกี่ยวข้อง มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การจัดรูปแบบรายการหลายระดับ

ตอนนี้เราจะใช้การจัดรูปแบบรายการหลายระดับโดยใช้วิธีการที่มีอยู่ในออบเจ็กต์ DocumentBuilder มีวิธีดังนี้:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการจัดรูปแบบรายการหลายระดับโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับคุณลักษณะการจัดรูปแบบรายการหลายระดับด้วย Aspose.Words สำหรับ .NET:


```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

ด้วยโค้ดนี้ คุณจะสามารถสร้างรายการหลายระดับและใช้การจัดรูปแบบที่เหมาะสมกับแต่ละระดับโดยใช้ Aspose.Words สำหรับ .NET


## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการใช้ฟีเจอร์การจัดรูปแบบรายการหลายระดับในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET เมื่อทำตามขั้นตอนที่ระบุไว้ คุณจะสามารถสร้างรายการที่จัดระเบียบอย่างดีโดยมีหลายระดับ ช่วยเพิ่มโครงสร้างและความสามารถในการอ่านเอกสารของคุณ

### คำถามที่พบบ่อย

#### ถาม: รายการหลายระดับในเอกสาร Word คืออะไร

ตอบ: รายการหลายระดับในเอกสาร Word เป็นรายการแบบลำดับชั้นที่ช่วยให้คุณสามารถจัดระเบียบรายการต่างๆ ให้เป็นรายการย่อยระดับต่างๆ ได้ ช่วยนำเสนอข้อมูลในลักษณะที่มีโครงสร้างทำให้ผู้อ่านเข้าใจเนื้อหาได้ง่ายขึ้น

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของรายการหลายระดับได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของรายการหลายระดับในเอกสาร Word ของคุณได้ ด้วยการปรับใช้สไตล์ที่แตกต่างกัน เช่น สัญลักษณ์แสดงหัวข้อย่อย ตัวเลข หรือตัวอักษร และการปรับการเยื้องและการเว้นวรรค คุณสามารถสร้างรายการที่มีรูปลักษณ์สวยงามและเป็นระเบียบได้

#### ถาม: Aspose.Words สำหรับ .NET รองรับตัวเลือกการจัดรูปแบบรายการอื่นๆ หรือไม่

ตอบ: ใช่ Aspose.Words สำหรับ .NET มีชุดคุณลักษณะที่ครอบคลุมสำหรับการจัดรูปแบบรายการ รองรับรายการประเภทต่างๆ รวมถึงรายการสัญลักษณ์แสดงหัวข้อย่อย รายการที่เรียงลำดับเลข และรายการหลายระดับ คุณสามารถจัดการการจัดรูปแบบของรายการ เพิ่มหรือลบรายการ และปรับแต่งลักษณะที่ปรากฏได้

#### ถาม: ฉันสามารถใช้ Aspose.Words สำหรับ .NET เพื่อทำงานกับองค์ประกอบเอกสารอื่นๆ ได้หรือไม่

ตอบ: ใช่ Aspose.Words สำหรับ .NET มีความสามารถมากมายสำหรับการทำงานกับองค์ประกอบเอกสารต่างๆ เช่น ย่อหน้า ตาราง รูปภาพ และอื่นๆ ช่วยให้คุณสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรม ซึ่งทำให้งานการประมวลผลเอกสารมีความคล่องตัวมากขึ้น
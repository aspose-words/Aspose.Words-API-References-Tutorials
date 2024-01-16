---
title: แทรกฟิลด์รวมข้อความโดยไม่มีตัวสร้างเอกสาร
linktitle: แทรก FieldIncludeText โดยไม่มีตัวสร้างเอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกฟิลด์ FieldIncludeText ในเอกสาร Word ของคุณด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fields/insert-field-include-text-without-document-builder/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่าง ซึ่งใช้ฟังก์ชัน "แทรกฟิลด์ FieldIncludeText" ของ Aspose.Words สำหรับ .NET อย่าลืมปฏิบัติตามแต่ละขั้นตอนอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีเอกสาร

ในโค้ดที่ให้มา คุณต้องระบุไดเร็กทอรีของเอกสารของคุณ แทนที่ค่า "YOUR DOCUMENT DIRECTORY" ด้วยเส้นทางที่เหมาะสมไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: การสร้างเอกสารและย่อหน้า

เราเริ่มต้นด้วยการสร้างเอกสารใหม่และเตรียมใช้งานย่อหน้า

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## ขั้นตอนที่ 3: การแทรกฟิลด์ FieldIncludeText

 เราใช้`AppendField()` วิธีการแทรกฟิลด์ FieldIncludeText ลงในย่อหน้า

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

จากนั้นเรากำหนดค่าคุณสมบัติของฟิลด์ FieldIncludeText โดยการระบุชื่อของบุ๊กมาร์กและชื่อของไฟล์ต้นฉบับ

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

ต่อไป เราจะเพิ่มย่อหน้าลงในเนื้อหาของเอกสาร

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 ในที่สุดเราก็เรียกว่า`Update()` วิธีการอัพเดตสนาม

```csharp
fieldIncludeText.Update();
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกฟิลด์ FieldIncludeText ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและย่อหน้า
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// แทรกฟิลด์ FieldIncludeText
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

ในตัวอย่างนี้ เราได้สร้างเอกสารใหม่ เริ่มต้นย่อหน้า แทรก FieldIncludeTexten ที่ระบุชื่อบุ๊กมาร์กและชื่อไฟล์ต้นฉบับ และบันทึกเอกสารด้วยชื่อไฟล์ที่ระบุ

นี่เป็นการสรุปคำแนะนำของเราเกี่ยวกับการใช้ฟีเจอร์ "แทรก FieldIncludeText" กับ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะระบุไฟล์ต้นฉบับสำหรับฟิลด์การรวมข้อความใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการระบุไฟล์ต้นฉบับสำหรับฟิลด์การรวมข้อความใน Aspose.Words สำหรับ .NET คุณสามารถใช้`FieldIncludeText.SourceFullName`คุณสมบัติเพื่อกำหนดเส้นทางแบบเต็มของไฟล์ต้นฉบับ ตรวจสอบให้แน่ใจว่าไฟล์ต้นฉบับสามารถเข้าถึงได้และมีเนื้อหาที่คุณต้องการรวมไว้ในฟิลด์การรวมข้อความ

#### ถาม: ฉันสามารถรวมข้อความจากแมโครลงในช่องรวมข้อความด้วย Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถรวมข้อความจากแมโครในช่องรวมข้อความด้วย Aspose.Words สำหรับ .NET ได้ คุณสามารถใช้`FieldIncludeText.IncludeText` คุณสมบัติเพื่อระบุชื่อของแมโครที่ควรรวมเนื้อหาไว้ในฟิลด์

#### ถาม: การแทรกข้อความรวมถึงฟิลด์ที่ไม่มีตัวสร้างเอกสารส่งผลต่อโครงสร้างเอกสาร Word ที่ใช้ Aspose.Words สำหรับ .NET หรือไม่

ตอบ: การแทรกฟิลด์รวมข้อความโดยไม่มีตัวสร้างเอกสารจะไม่ส่งผลโดยตรงต่อโครงสร้างของเอกสาร Word อย่างไรก็ตาม จะเพิ่มองค์ประกอบฟิลด์ใหม่ให้กับเนื้อหาเอกสาร คุณสามารถจัดการโครงสร้างเอกสารได้โดยการเพิ่ม ลบ หรือแก้ไของค์ประกอบที่มีอยู่ตามความต้องการของคุณ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของฟิลด์การรวมข้อความในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้หรือไม่

ตอบ: ฟิลด์การรวมข้อความไม่ได้กำหนดลักษณะที่ปรากฏโดยตรงในเอกสาร Word อย่างไรก็ตาม คุณสามารถจัดรูปแบบข้อความที่รวมไว้ได้โดยใช้คุณสมบัติย่อหน้า คุณสมบัติแบบอักษร และวัตถุการจัดรูปแบบอื่นๆ ที่มีอยู่ใน Aspose.Words สำหรับ .NET
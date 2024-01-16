---
title: Word แทนที่ข้อความที่มีอักขระ Meta
linktitle: Word แทนที่ข้อความที่มีอักขระ Meta
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทนที่ข้อความที่มีอักขระเมตาในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/find-and-replace-text/replace-text-containing-meta-characters/
---
ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Word แทนที่ข้อความที่มีอักขระ Meta ใน Aspose.Words สำหรับไลบรารี .NET คุณลักษณะนี้ช่วยให้คุณสามารถแทนที่ข้อความบางส่วนในเอกสารที่มีอักขระเมตาเฉพาะได้

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: การสร้างเอกสารใหม่

 ก่อนที่เราจะเริ่มใช้การแทนที่ข้อความเมตาอักขระ เราจำเป็นต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ขั้นตอนที่ 2: แทรกข้อความลงในเอกสาร

 เมื่อได้เอกสารแล้ว เราก็สามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ในตัวอย่างของเรา เราใช้`Writeln` วิธีการแทรกข้อความหลายย่อหน้าลงในส่วนต่างๆ:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกค้นหาและแทนที่

 ตอนนี้เราจะกำหนดค่าตัวเลือกการค้นหาและแทนที่โดยใช้`FindReplaceOptions` วัตถุ. ในตัวอย่างของเรา เราตั้งค่าการจัดตำแหน่งของย่อหน้าที่ถูกแทนที่เป็น "กึ่งกลาง":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## ขั้นตอนที่ 4: การแทนที่ข้อความที่มี MetaCharacters

 เราใช้`Range.Replace`วิธีการดำเนินการแทนที่ข้อความที่มีอักขระเมตา ในตัวอย่างของเรา เราจะแทนที่คำว่า "section" แต่ละครั้ง ตามด้วยตัวแบ่งย่อหน้าด้วยคำเดียวกัน ตามด้วยเครื่องหมายขีดกลางหลายอัน และตัวแบ่งย่อหน้าใหม่:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## ขั้นตอนที่ 5: การแทนที่แท็กข้อความที่กำหนดเอง

 เรายังใช้`Range.Replace` วิธีการแทนที่แบบกำหนดเอง "{insert-section}แท็กข้อความที่มีตัวแบ่งส่วน ในตัวอย่างของเรา เราจะแทนที่ "{insert-section}" ด้วย "&b" เพื่อแทรกตัวแบ่งส่วน:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข

สุดท้าย เราจะบันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทนที่ข้อความที่มีอักขระ Meta โดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการใช้การแทนที่ข้อความที่มีอักขระเมตาด้วย Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// เพิ่มการแบ่งย่อหน้าเป็นสองเท่าหลังคำว่า "ส่วน" เพิ่มการขีดเส้นใต้และทำให้อยู่กึ่งกลาง
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// แทรกตัวแบ่งส่วนแทนแท็กข้อความที่กำหนดเอง
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟีเจอร์แทนที่ข้อความที่มีอักขระ Meta ของ Aspose.Words สำหรับ .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่อสร้างเอกสาร แทรกข้อความ แทนที่ข้อความที่มีอักขระเมตา และบันทึกเอกสารที่แก้ไข

### คำถามที่พบบ่อย

#### ถาม: ฟังก์ชันแทนที่ข้อความที่มีอักขระ Meta ใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะการแทนที่ข้อความที่มีอักขระ Meta ใน Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถแทนที่ข้อความบางส่วนในเอกสารที่มีอักขระ meta ที่ระบุได้ คุณสามารถใช้คุณสมบัตินี้เพื่อทำการแทนที่ขั้นสูงในเอกสารของคุณโดยคำนึงถึงอักขระเมตา

#### ถาม: จะสร้างเอกสารใหม่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ก่อนที่จะใช้ฟังก์ชันแทนที่ข้อความที่มีอักขระ Meta คุณต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุ. นี่คือโค้ดตัวอย่างเพื่อสร้างเอกสารใหม่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### ถาม: จะแทรกข้อความลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อคุณมีเอกสารแล้ว คุณสามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ในตัวอย่างของเรา เราใช้`Writeln` วิธีการแทรกข้อความหลายย่อหน้าลงในส่วนต่างๆ:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### ถาม: จะกำหนดค่าตัวเลือกการค้นหาและแทนที่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ตอนนี้เราจะกำหนดค่าการค้นหาและแทนที่ตัวเลือกโดยใช้`FindReplaceOptions` วัตถุ. ในตัวอย่างของเรา เราตั้งค่าการจัดตำแหน่งของย่อหน้าที่ถูกแทนที่เป็น "กึ่งกลาง":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### ถาม: จะแทนที่ข้อความที่มีอักขระเมตาในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เราใช้`Range.Replace` วิธีการดำเนินการแทนที่ข้อความที่มีอักขระเมตา ในตัวอย่างของเรา เราจะแทนที่คำว่า "section" แต่ละครั้ง ตามด้วยตัวแบ่งย่อหน้าด้วยคำเดียวกัน ตามด้วยเครื่องหมายขีดกลางหลายอัน และตัวแบ่งย่อหน้าใหม่:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### ถาม: จะแทนที่แท็กข้อความแบบกำหนดเองที่มีอักขระเมตาในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เรายังใช้`Range.Replace` วิธีการแทนที่แบบกำหนดเอง "{insert-section}แท็กข้อความที่มีตัวแบ่งส่วน ในตัวอย่างของเรา เราจะแทนที่ "{insert-section}" ด้วย "&b" เพื่อแทรกตัวแบ่งส่วน:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อคุณทำการเปลี่ยนแปลงเอกสารแล้ว คุณสามารถบันทึกลงในไดเร็กทอรีที่ระบุได้โดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```
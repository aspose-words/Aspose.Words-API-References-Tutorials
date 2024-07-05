---
title: ค้นหาข้อความอย่างง่ายและแทนที่ใน Word
linktitle: ค้นหาข้อความอย่างง่ายและแทนที่ใน Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีดำเนินการค้นหาและแทนที่ข้อความอย่างง่ายในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/find-and-replace-text/simple-find-replace/
---
ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้การค้นหาข้อความอย่างง่ายและแทนที่ในไลบรารี Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถแทนที่ข้อความอย่างง่ายโดยการค้นหาสตริงอักขระเฉพาะและแทนที่ด้วยสตริงอักขระอื่นในเอกสาร Word

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: การสร้างเอกสารใหม่

 ก่อนที่เราจะเริ่มใช้การค้นหาและแทนที่แบบง่าย เราจำเป็นต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ขั้นตอนที่ 2: แทรกข้อความลงในเอกสาร

 เมื่อได้เอกสารแล้ว เราก็สามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ในตัวอย่างของเรา เราใช้`Writeln` วิธีการแทรกคำว่า “สวัสดี._CustomerName_-

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## ขั้นตอนที่ 3: การเปลี่ยนข้อความอย่างง่าย

 เราใช้`Range.Replace` วิธีการแทนที่ข้อความอย่างง่าย ในตัวอย่างของเรา เราแทนที่สตริงทั้งหมดที่เกิดขึ้น "_ClientName_ " กับ "เจมส์ บอนด์" โดยใช้`FindReplaceOptions` ตัวเลือกด้วย`FindReplaceDirection.Forward` ทิศทางการค้นหา:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข

สุดท้าย เราจะบันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Simple Find Refplace โดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการใช้การค้นหาอย่างง่ายและแทนที่ด้วย Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// บันทึกเอกสารที่แก้ไข
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Simple Find Refplace ของ Aspose.Words สำหรับ .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่อสร้างเอกสาร แทรกข้อความ ดำเนินการแทนที่ข้อความอย่างง่าย และบันทึกเอกสารที่แก้ไข

### คำถามที่พบบ่อย

#### ถาม: ฟังก์ชันการค้นหาและแทนที่ข้อความอย่างง่ายใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะการค้นหาและแทนที่ข้อความอย่างง่ายใน Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถแทนที่ข้อความอย่างง่ายในเอกสาร Word ได้ ช่วยให้คุณสามารถค้นหาสตริงอักขระเฉพาะและแทนที่ด้วยสตริงอักขระอื่น สิ่งนี้มีประโยชน์เมื่อคุณต้องการทำการเปลี่ยนแปลงส่วนกลางในเอกสาร เช่น การเปลี่ยนชื่อ วันที่ หรือข้อมูลอื่นๆ

#### ถาม: จะสร้างเอกสารใหม่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ก่อนที่จะใช้ฟังก์ชันค้นหาและแทนที่ข้อความอย่างง่าย คุณต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุ. นี่คือโค้ดตัวอย่างเพื่อสร้างเอกสารใหม่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### ถาม: จะแทรกข้อความลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อคุณมีเอกสารแล้ว คุณสามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ในตัวอย่างของเรา เราใช้`Writeln` วิธีการแทรกคำว่า “สวัสดี._CustomerName_-

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### ถาม: ฉันจะทำการแทนที่ข้อความอย่างง่ายในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการทำการแทนที่ข้อความอย่างง่าย คุณสามารถใช้`Range.Replace` วิธี. ในตัวอย่างของเรา เราแทนที่สตริงทั้งหมดที่เกิดขึ้น "_ClientName_ " กับ "เจมส์ บอนด์" โดยใช้`FindReplaceOptions` ตัวเลือกด้วย`FindReplaceDirection.Forward` ทิศทางการค้นหา:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อคุณทำการแทนที่ข้อความแล้ว คุณสามารถบันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุได้โดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```
---
title: อักขระ Meta ในรูปแบบการค้นหา
linktitle: อักขระ Meta ในรูปแบบการค้นหา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้อักขระเมตาในรูปแบบการค้นหาด้วย Aspose.Words สำหรับ .NET เพื่อจัดการเอกสาร Word
type: docs
weight: 10
url: /th/net/find-and-replace-text/meta-characters-in-search-pattern/
---
ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Meta Character In Search Pattern ใน Aspose.Words สำหรับไลบรารี .NET คุณลักษณะนี้ช่วยให้คุณใช้อักขระเมตาพิเศษเพื่อทำการค้นหาขั้นสูงและแทนที่ในเอกสาร Word

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: การสร้างเอกสารใหม่

 ก่อนที่เราจะเริ่มใช้อักขระเมตาในรูปแบบการค้นหา เราจำเป็นต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุ:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## ขั้นตอนที่ 2: แทรกข้อความลงในเอกสาร

 เมื่อได้เอกสารแล้ว เราก็สามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ในตัวอย่างของเรา เราใช้`Writeln` และ`Write` วิธีการแทรกข้อความสองบรรทัด:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## ขั้นตอนที่ 3: ค้นหาและแทนที่ข้อความด้วยอักขระเมตา

 ตอนนี้เราจะใช้`Range.Replace` ฟังก์ชั่นการค้นหาและแทนที่ข้อความโดยใช้รูปแบบการค้นหาที่มีอักขระเมตาพิเศษ ในตัวอย่างของเรา เราแทนที่วลี "นี่คือบรรทัด 1&pนี่คือบรรทัด 2" ด้วย "บรรทัดนี้ถูกแทนที่" โดยใช้`&p` meta character เพื่อแสดงตัวแบ่งย่อหน้า:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## ขั้นตอนที่ 4: การแทรกตัวแบ่งหน้าในเอกสาร

 เพื่อแสดงให้เห็นการใช้ meta character อื่น เราจะแทรกตัวแบ่งหน้าลงในเอกสารโดยใช้`InsertBreak` วิธีการด้วย`BreakType.PageBreak` พารามิเตอร์. ก่อนอื่นเราเลื่อนเคอร์เซอร์จาก`DocumentBuilder` ที่ท้ายเอกสาร จากนั้นเราจะแทรกตัวแบ่งหน้าและบรรทัดข้อความใหม่:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## ขั้นตอนที่ 5: ค้นหาและแทนที่ด้วย meta character อื่น

 ตอนนี้เราจะทำการค้นหาอีกครั้งและแทนที่โดยใช้`&m` meta character เพื่อแสดงตัวแบ่งหน้า เราแทนที่วลี "นี่คือบรรทัด 1&mนี่คือบรรทัด 2" ด้วย "ตัวแบ่งหน้าถูกแทนที่ด้วยข้อความใหม่" : :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข

สุดท้าย เราจะบันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับอักขระ Meta ในรูปแบบการค้นหาโดยใช้ Aspose.Words สำหรับ .NET

ต่อไปนี้คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการใช้อักขระเมตาในรูปแบบการค้นหาด้วย Aspose.Words สำหรับ .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้อักขระเมตาในรูปแบบการค้นหาของ Aspose.Words สำหรับ .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่อสร้างเอกสาร แทรกข้อความ ทำการค้นหาและแทนที่โดยใช้อักขระเมตาพิเศษ แทรกตัวแบ่งหน้า และบันทึกเอกสารที่แก้ไข

### คำถามที่พบบ่อย

#### ถาม: ฟีเจอร์ Meta Character In Search Pattern ใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะ Meta อักขระในรูปแบบการค้นหาใน Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถใช้อักขระ meta พิเศษเพื่อทำการค้นหาขั้นสูงและการแทนที่ในเอกสาร Word อักขระเมตาเหล่านี้ช่วยให้คุณสามารถแสดงตัวแบ่งย่อหน้า ตัวแบ่งส่วน ตัวแบ่งหน้า และองค์ประกอบพิเศษอื่นๆ ในรูปแบบการค้นหาของคุณ

#### ถาม: จะสร้างเอกสารใหม่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ก่อนที่จะใช้อักขระเมตาในเทมเพลตการค้นหา คุณต้องสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุ. นี่คือโค้ดตัวอย่างเพื่อสร้างเอกสารใหม่:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### ถาม: จะแทรกข้อความลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อคุณมีเอกสารแล้ว คุณสามารถแทรกข้อความโดยใช้ a`DocumentBuilder` วัตถุ. ในตัวอย่างของเรา เราใช้`Writeln` และ`Write` วิธีการแทรกข้อความสองบรรทัด:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### ถาม: จะค้นหาและแทนที่ข้อความด้วยอักขระเมตาในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการค้นหาและแทนที่ข้อความด้วยอักขระเมตา คุณสามารถใช้`Range.Replace` วิธี. ในตัวอย่างของเรา เราแทนที่วลี "นี่คือบรรทัด 1&pนี่คือบรรทัด 2" ด้วย "บรรทัดนี้ถูกแทนที่" โดยใช้`&p` meta character เพื่อแสดงตัวแบ่งย่อหน้า:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### ถาม: จะแทรกตัวแบ่งหน้าในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: เพื่อแสดงให้เห็นการใช้ meta character อื่น เราจะแทรกตัวแบ่งหน้าลงในเอกสารโดยใช้`InsertBreak` วิธีการด้วย`BreakType.PageBreak` พารามิเตอร์. ก่อนอื่นเราเลื่อนเคอร์เซอร์จาก`DocumentBuilder` ที่ท้ายเอกสาร จากนั้นเราจะแทรกตัวแบ่งหน้าและบรรทัดข้อความใหม่:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### ถาม: จะค้นหาและแทนที่ด้วย meta character อื่นในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ตอนนี้เราจะทำการค้นหาอีกครั้งและแทนที่โดยใช้`&m` meta character เพื่อแสดงตัวแบ่งหน้า เราแทนที่วลี "นี่คือบรรทัด 1&mนี่คือบรรทัด 2" ด้วย "ตัวแบ่งหน้าถูกแทนที่ด้วยข้อความใหม่" : :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อคุณทำการเปลี่ยนแปลงเอกสารแล้ว คุณสามารถบันทึกลงในไดเร็กทอรีที่ระบุได้โดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```
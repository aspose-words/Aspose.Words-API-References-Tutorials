---
title: ย้ายไปที่ส่วนในเอกสาร Word
linktitle: ย้ายไปที่ส่วนในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการใช้ฟีเจอร์ย้ายไปยังส่วนในเอกสาร Word ของ Aspose.Words สำหรับ .NET จัดการส่วนและย่อหน้าในเอกสาร Word
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/move-to-section/
---
ในตัวอย่างนี้ เราจะแนะนำวิธีใช้ฟีเจอร์ Move To Section ในเอกสาร word ของ Aspose.Words สำหรับ .NET ทีละขั้นตอนโดยใช้ซอร์สโค้ด C# ที่ให้มา คุณลักษณะนี้ช่วยให้คุณสามารถนำทางและจัดการส่วนต่างๆ ภายในเอกสาร Word ได้ ทำตามขั้นตอนด้านล่างเพื่อรวมฟังก์ชันนี้เข้ากับแอปพลิเคชันของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และเพิ่มส่วน

ขั้นแรก เราต้องสร้างเอกสารใหม่และเพิ่มส่วนลงไป ใช้รหัสต่อไปนี้เพื่อทำขั้นตอนนี้ให้สำเร็จ:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

รหัสนี้จะสร้างเอกสารว่างใหม่และเพิ่มส่วนให้กับเอกสารนี้

## ขั้นตอนที่ 2: ย้าย DocumentBuilder ไปยังส่วนที่สองและเพิ่มข้อความ

ต่อไป เราต้องย้าย DocumentBuilder ไปยังส่วนที่สองของเอกสารและเพิ่มข้อความที่นั่น ใช้รหัสต่อไปนี้เพื่อดำเนินการขั้นตอนนี้:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

โค้ดนี้จะสร้าง DocumentBuilder จากเอกสารที่มีอยู่ จากนั้นย้ายเคอร์เซอร์จาก DocumentBuilder ไปยังส่วนที่สองของเอกสาร สุดท้ายจะเพิ่มข้อความที่ระบุในส่วนนี้

## ขั้นตอนที่ 3: โหลดเอกสารด้วยย่อหน้าที่มีอยู่

หากคุณต้องการทำงานกับเอกสารที่มีอยู่ซึ่งมีย่อหน้า คุณสามารถโหลดเอกสารนี้โดยใช้โค้ดต่อไปนี้:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

รหัสนี้โหลดเอกสารที่ระบุ (แทนที่ "MyDir + "Paragraphs.docx"" ด้วยเส้นทางจริงไปยังเอกสารของคุณ) และเข้าถึงคอลเลกชันของย่อหน้าจากส่วนแรกของเอกสาร เส้น`Assert.AreEqual(22, paragraphs.Count);` ตรวจสอบว่าเอกสารมี 22 ย่อหน้า

## ขั้นตอนที่ 4: สร้าง DocumentBuilder สำหรับเอกสาร

คุณสามารถสร้างเคอร์เซอร์ DocumentBuilder ไปยังย่อหน้าเฉพาะได้โดยใช้ดัชนีตำแหน่ง

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## ขั้นตอนที่ 5: เลื่อนเคอร์เซอร์ไปยังย่อหน้าที่ต้องการ


คุณสามารถย้ายเคอร์เซอร์ DocumentBuilder ไปยังย่อหน้าเฉพาะได้โดยใช้ดัชนีตำแหน่ง ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

โค้ดนี้จะย้ายเคอร์เซอร์ของ DocumentBuilder ไปที่ย่อหน้าที่สามของส่วนที่สอง (ย่อหน้าที่ดัชนี 2) และไปที่ตำแหน่ง 10 จากนั้นจะเพิ่มย่อหน้าใหม่พร้อมข้อความบางส่วน และตรวจสอบว่าเคอร์เซอร์อยู่ในตำแหน่งที่ดีบนย่อหน้าใหม่นี้

### ตัวอย่างซอร์สโค้ดสำหรับ Move To Move To Section โดยใช้ Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// ย้าย DocumentBuilder ไปยังส่วนที่สองและเพิ่มข้อความ
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// สร้างเอกสารที่มีย่อหน้า
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// เมื่อเราสร้าง DocumentBuilder สำหรับเอกสาร เคอร์เซอร์จะอยู่ที่จุดเริ่มต้นของเอกสารตามค่าเริ่มต้น
// และเนื้อหาใด ๆ ที่เพิ่มโดย DocumentBuilder จะถูกเพิ่มไว้ข้างหน้าเอกสาร
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//คุณสามารถย้ายเคอร์เซอร์ไปที่ตำแหน่งใดก็ได้ในย่อหน้า
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

นั่นคือทั้งหมดที่ ! ตอนนี้คุณเข้าใจวิธีใช้ฟังก์ชันการย้ายไปยังส่วนของ Aspose.Words สำหรับ .NET โดยใช้ซอร์สโค้ดที่ให้มาแล้ว ตอนนี้คุณสามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชันของคุณเอง และจัดการส่วนและย่อหน้าของเอกสาร Word ของคุณแบบไดนามิกได้

## บทสรุป

ในตัวอย่างนี้ เราได้สำรวจฟีเจอร์ Move To Section ของ Aspose.Words สำหรับ .NET เราเรียนรู้วิธีสร้างเอกสารใหม่ เพิ่มส่วนต่างๆ และใช้คลาส DocumentBuilder เพื่อนำทางไปยังส่วนและย่อหน้าเฉพาะภายในเอกสาร Word คุณสมบัตินี้ช่วยให้นักพัฒนามีเครื่องมืออันทรงพลังในการจัดการเนื้อหาและโครงสร้างของเอกสาร Word โดยทางโปรแกรมโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อยสำหรับการย้ายไปยังส่วนในเอกสาร word

#### ถาม: จุดประสงค์ของฟีเจอร์ Move To Section ใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะการย้ายไปยังส่วนใน Aspose.Words สำหรับ .NET ช่วยให้นักพัฒนาสามารถนำทางไปยังและจัดการส่วนต่างๆ ภายในเอกสาร Word โดยทางโปรแกรม โดยให้ความสามารถในการแทรก แก้ไข หรือลบเนื้อหาในส่วนเฉพาะของเอกสาร

#### ถาม: ฉันจะย้าย DocumentBuilder ไปยังส่วนเฉพาะในเอกสาร Word ได้อย่างไร

ตอบ: เมื่อต้องการย้าย DocumentBuilder ไปยังส่วนเฉพาะในเอกสาร Word คุณสามารถใช้เมธอด MoveToSection ของคลาส DocumentBuilder เมธอดนี้ใช้ดัชนีของส่วนเป้าหมายเป็นพารามิเตอร์ และวางเคอร์เซอร์ไว้ที่จุดเริ่มต้นของส่วนนั้น

#### ถาม: ฉันสามารถเพิ่มหรือแก้ไขเนื้อหาหลังจากย้ายไปยังส่วนใดส่วนหนึ่งโดยใช้ฟีเจอร์ย้ายไปยังส่วนได้หรือไม่

ตอบ: ได้ เมื่อ DocumentBuilder อยู่ในตำแหน่งที่ต้องการโดยใช้ MoveToSection คุณจะสามารถใช้วิธีต่างๆ ของคลาส DocumentBuilder เช่น Writeln, Write หรือ InsertHtml เพื่อเพิ่มหรือแก้ไขเนื้อหาของส่วนนั้นได้

#### ถาม: ฉันจะทำงานกับย่อหน้าที่มีอยู่ในเอกสารโดยใช้ฟีเจอร์ย้ายไปยังส่วนได้อย่างไร

ตอบ: คุณสามารถโหลดเอกสารที่มีอยู่ซึ่งมีย่อหน้าได้โดยใช้ตัวสร้างเอกสาร จากนั้นเข้าถึงคอลเลกชันของย่อหน้าจากส่วนที่ต้องการโดยใช้คุณสมบัติ FirstSection.Body.Paragraphs

#### ถาม: ฉันสามารถย้ายเคอร์เซอร์ DocumentBuilder ไปยังย่อหน้าเฉพาะภายในส่วนโดยใช้คุณสมบัติย้ายไปยังส่วนได้หรือไม่

ตอบ: ได้ คุณสามารถย้ายเคอร์เซอร์ DocumentBuilder ไปยังย่อหน้าเฉพาะภายในส่วนได้โดยใช้วิธี MoveToParagraph วิธีการนี้จะใช้ดัชนีของย่อหน้าเป้าหมายและตำแหน่งอักขระ (ออฟเซ็ต) ภายในย่อหน้าเป็นพารามิเตอร์
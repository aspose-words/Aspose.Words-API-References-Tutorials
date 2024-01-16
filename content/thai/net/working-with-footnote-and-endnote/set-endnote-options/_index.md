---
title: ตั้งค่าตัวเลือกอ้างอิงท้ายเรื่อง
linktitle: ตั้งค่าตัวเลือกอ้างอิงท้ายเรื่อง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าตัวเลือกอ้างอิงท้ายเรื่องในเอกสาร Word โดยใช้ Aspose.Words for .NET บทช่วยสอนทีละขั้นตอนพร้อมซอร์สโค้ดตัวอย่าง
type: docs
weight: 10
url: /th/net/working-with-footnote-and-endnote/set-endnote-options/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีใช้ Aspose.Words สำหรับ .NET เพื่อตั้งค่าตัวเลือกอ้างอิงท้ายเรื่องในเอกสาร Word เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ .NET และตั้งค่าในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดำเนินการ ให้ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Releases]https://releases.aspose.com/words/net/

## ขั้นตอนที่ 1: การเริ่มต้นวัตถุเอกสาร

 ขั้นแรกให้เริ่มต้น`Document` วัตถุโดยระบุเส้นทางไปยังเอกสารต้นฉบับของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## ขั้นตอนที่ 2: การเริ่มต้นวัตถุ DocumentBuilder

 ถัดไป เริ่มต้น`DocumentBuilder` วัตถุเพื่อดำเนินการกับเอกสาร:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: การเพิ่มข้อความและอ้างอิงท้ายเรื่อง

 ใช้`Write` วิธีการของ`DocumentBuilder` วัตถุเพื่อเพิ่มข้อความลงในเอกสารและ`InsertFootnote` วิธีการแทรกอ้างอิงท้ายเรื่อง:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## ขั้นตอนที่ 4: การตั้งค่าตัวเลือกอ้างอิงท้ายเรื่อง

 เข้าถึง`EndnoteOptions` คุณสมบัติของเอกสารเพื่อแก้ไขตัวเลือกอ้างอิงท้ายเรื่อง ในตัวอย่างนี้ เราตั้งค่ากฎการรีสตาร์ทเพื่อรีสตาร์ทในแต่ละหน้าและตำแหน่งที่ส่วนท้ายของส่วน:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารที่แก้ไข:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

แค่นั้นแหละ! คุณได้ตั้งค่าตัวเลือกอ้างอิงท้ายเรื่องในเอกสาร Word โดยใช้ Aspose.Words for .NET เรียบร้อยแล้ว

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าตัวเลือก Endnote โดยใช้ Aspose.Words สำหรับ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

คุณสามารถใช้โค้ดนี้ในโครงการของคุณเองและแก้ไขได้ตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะจัดสไตล์อ้างอิงท้ายเรื่องใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการจัดสไตล์อ้างอิงท้ายเรื่องใน Aspose.Words คุณสามารถใช้`EndnoteOptions` ชั้นเรียนและ`SeparatorNoteTextStyle` คุณสมบัติ. คุณสามารถระบุลักษณะแบบอักษร ขนาด สี ฯลฯ สำหรับอ้างอิงท้ายเรื่องได้โดยใช้คุณสมบัตินี้

#### ถาม: เป็นไปได้หรือไม่ที่จะกำหนดหมายเลขอ้างอิงท้ายเรื่องในเอกสาร

 ตอบ: ได้ คุณสามารถกำหนดหมายเลขอ้างอิงท้ายเรื่องในเอกสารได้ คุณสามารถใช้`RestartRule` และ`NumberStyle` คุณสมบัติของ`EndnoteOptions` คลาสเพื่อกำหนดกฎการรีสตาร์ทเฉพาะและสไตล์การกำหนดหมายเลข

#### ถาม: ฉันจะวางตำแหน่งอ้างอิงท้ายเรื่องในเอกสารได้อย่างไร

 ตอบ: หากต้องการวางตำแหน่งอ้างอิงท้ายเรื่องในเอกสาร คุณสามารถใช้`Position` ทรัพย์สินของ`EndnoteOptions` ระดับ. คุณสามารถระบุได้ว่าควรวางอ้างอิงท้ายเรื่องไว้ที่ด้านล่างของแต่ละหน้า ที่ส่วนท้ายของแต่ละส่วน หรือที่ส่วนท้ายของเอกสาร

#### ถาม: ฉันสามารถปรับแต่งรูปแบบการกำหนดหมายเลขอ้างอิงท้ายเรื่องได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งรูปแบบของการกำหนดหมายเลขอ้างอิงท้ายเรื่องใน Aspose.Words ได้ ใช้`NumberFormat` ทรัพย์สินของ`EndnoteOptions` คลาสเพื่อกำหนดรูปแบบที่ต้องการ เช่น เลขอารบิก เลขโรมัน ตัวอักษร เป็นต้น

#### ถาม: เป็นไปได้หรือไม่ที่จะกำหนดหมายเลขอ้างอิงท้ายเรื่องระหว่างส่วนต่างๆ ของเอกสารต่อไป

 ตอบ: ได้ คุณสามารถกำหนดหมายเลขอ้างอิงท้ายเรื่องต่อระหว่างส่วนต่างๆ ของเอกสารได้ ใช้`RestartRule` ทรัพย์สินของ`EndnoteOptions` ชั้นเรียนและตั้งค่าเป็น`RestartContinuous` เพื่อให้การเรียงลำดับหมายเลขดำเนินต่อไประหว่างส่วนต่างๆ
---
title: แทรกสารบัญในเอกสาร Word
linktitle: แทรกสารบัญในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกสารบัญในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/insert-table-of-contents/
---
ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีแทรกสารบัญลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ ในตอนท้ายของคู่มือนี้ คุณจะสามารถสร้างสารบัญที่มีส่วนหัวและหมายเลขหน้าที่เหมาะสมได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และ DocumentBuilder
ในการเริ่มต้น ให้สร้างเอกสารใหม่โดยใช้คลาส Document และเตรียมใช้งานอ็อบเจ็กต์ DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: แทรกสารบัญ
จากนั้น ใช้เมธอด InsertTableOfContents ของคลาส DocumentBuilder เพื่อแทรกสารบัญ ระบุตัวเลือกการจัดรูปแบบที่ต้องการภายในวิธีการ:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## ขั้นตอนที่ 3: เพิ่มเนื้อหาเอกสาร
หลังจากแทรกสารบัญแล้ว ให้เพิ่มเนื้อหาเอกสารจริง ตั้งค่ารูปแบบส่วนหัวที่เหมาะสมโดยใช้ StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## ขั้นตอนที่ 4: อัปเดตสารบัญ
สารบัญที่แทรกใหม่จะว่างเปล่าในตอนแรก หากต้องการเติมข้อมูล ให้อัปเดตฟิลด์ในเอกสาร:

```csharp
doc.UpdateFields();
```

## ขั้นตอนที่ 5: บันทึกเอกสาร
หลังจากแทรกสารบัญและอัปเดตฟิลด์แล้ว ให้บันทึกเอกสารลงในไฟล์โดยใช้วิธีบันทึกของคลาสเอกสาร:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกสารบัญโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการแทรกสารบัญโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// เริ่มต้น DocumentBuilder ด้วยวัตถุ Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// แทรกสารบัญ
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// เริ่มต้นเนื้อหาเอกสารจริงในหน้าที่สอง
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// สารบัญที่แทรกใหม่จะว่างเปล่าในตอนแรก
// จำเป็นต้องเติมข้อมูลโดยการอัปเดตฟิลด์ในเอกสาร
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีแทรกสารบัญลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้ซอร์สโค้ดที่ให้มา คุณสามารถสร้างสารบัญที่มีส่วนหัวและหมายเลขหน้าที่เหมาะสมสำหรับเอกสารของคุณได้แล้ว

### คำถามที่พบบ่อยสำหรับการแทรกสารบัญในเอกสารคำ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของสารบัญได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของสารบัญได้โดยการแก้ไขตัวเลือกการจัดรูปแบบที่ระบุใน`InsertTableOfContents` วิธี. พารามิเตอร์ช่วยให้คุณควบคุมหมายเลขหน้า การเยื้อง และสไตล์อื่นๆ

#### ถาม: จะเกิดอะไรขึ้นหากฉันต้องการรวมระดับหัวเรื่องเฉพาะเจาะจงในสารบัญ

 ตอบ: คุณสามารถระบุระดับหัวเรื่องที่ต้องการรวมไว้ในสารบัญได้โดยการปรับค่าภายใน`InsertTableOfContents` วิธี. เช่น การใช้`"\\o \"1-3\""` จะรวมส่วนหัวระดับ 1 ถึง 3

#### ถาม: ฉันสามารถอัปเดตสารบัญโดยอัตโนมัติได้หรือไม่หากฉันเปลี่ยนแปลงเนื้อหาเอกสาร

 ตอบ: ได้ คุณสามารถอัปเดตสารบัญได้โดยอัตโนมัติโดยการโทรไปที่`UpdateFields` วิธีการในเอกสาร เพื่อให้แน่ใจว่าการเปลี่ยนแปลงใดๆ ที่เกิดขึ้นกับเนื้อหาเอกสาร เช่น การเพิ่มหรือการลบส่วนหัว จะสะท้อนให้เห็นในสารบัญ

#### ถาม: ฉันจะจัดรูปแบบระดับหัวข้อในสารบัญให้แตกต่างออกไปได้อย่างไร

 ตอบ: คุณสามารถจัดสไตล์ระดับหัวเรื่องให้แตกต่างกันได้โดยใช้สไตล์ย่อหน้าที่แตกต่างกันสำหรับหัวเรื่องแต่ละระดับ โดยมอบหมายงานต่างๆ`StyleIdentifier` ค่าให้กับ`ParagraphFormat` ของ`DocumentBuilder`คุณสามารถสร้างสไตล์ที่แตกต่างกันสำหรับส่วนหัวแต่ละระดับได้

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มการจัดรูปแบบเพิ่มเติมให้กับส่วนหัวในสารบัญ

 ตอบ: ได้ คุณสามารถเพิ่มการจัดรูปแบบเพิ่มเติมให้กับส่วนหัวในสารบัญได้ เช่น สไตล์ฟอนต์ สี หรือคุณสมบัติอื่นๆ โดยการปรับ`Font` คุณสมบัติของ`DocumentBuilder`คุณสามารถใช้การจัดรูปแบบแบบกำหนดเองกับส่วนหัวได้
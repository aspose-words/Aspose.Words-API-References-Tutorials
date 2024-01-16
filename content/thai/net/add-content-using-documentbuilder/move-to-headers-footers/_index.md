---
title: ย้ายไปที่ส่วนท้ายของส่วนหัวในเอกสาร Word
linktitle: ย้ายไปที่ส่วนท้ายของส่วนหัวในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อนำทางและแก้ไขส่วนหัวและส่วนท้ายในเอกสาร Word ด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/move-to-headers-footers/
---
ในตัวอย่างนี้ เราจะสำรวจฟีเจอร์ Move To Headers Footers ของ Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารีจัดการเอกสารที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรม คุณลักษณะการย้ายไปยังส่วนหัว/ท้ายกระดาษช่วยให้เราสามารถนำทางไปยังส่วนหัวและส่วนท้ายต่างๆ ภายในเอกสารและเพิ่มเนื้อหาลงในเอกสารได้

มาดูซอร์สโค้ดทีละขั้นตอนเพื่อทำความเข้าใจวิธีใช้ฟีเจอร์ย้ายไปยังส่วนหัว/ท้ายกระดาษโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: การเริ่มต้นเอกสารและตัวสร้างเอกสาร

ขั้นแรก ให้เตรียมใช้งานอ็อบเจ็กต์ Document และ DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การกำหนดค่าส่วนหัวและส่วนท้าย

ระบุการตั้งค่าส่วนหัว/ส่วนท้ายสำหรับเอกสาร ในตัวอย่างนี้ เราตั้งค่าส่วนหัวและส่วนท้ายให้แตกต่างกันสำหรับหน้าแรกและสำหรับหน้าคี่/คู่:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## ขั้นตอนที่ 3: การสร้างส่วนหัวสำหรับหน้าต่างๆ

ย้ายไปยังส่วนหัวแต่ละประเภทและเพิ่มเนื้อหาลงไป ในตัวอย่างนี้ เราสร้างส่วนหัวสำหรับหน้าแรก หน้าคู่ และหน้าอื่นๆ ทั้งหมด:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## ขั้นตอนที่ 4: การสร้างหน้าในเอกสาร
เพิ่มเนื้อหาลงในเอกสารเพื่อสร้างหลายหน้า ตัวอย่างเช่น:

```csharp
// สร้างสองหน้าในเอกสาร
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## ขั้นตอนที่ 5: บันทึกเอกสาร

บันทึกเอกสารที่แก้ไขไปยังตำแหน่งที่ต้องการ:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางและรูปแบบไฟล์ที่เหมาะสม (เช่น DOCX)

### ตัวอย่างซอร์สโค้ดสำหรับ Move To Headers/Footers โดยใช้ Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ระบุว่าเราต้องการให้ส่วนหัวและส่วนท้ายแตกต่างกันสำหรับหน้าแรก หน้าคู่ และหน้าคี่
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// สร้างส่วนหัว
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// สร้างสองหน้าในเอกสาร
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## บทสรุป

ในตัวอย่างนี้ เราได้สำรวจฟีเจอร์ Move To Headers/Footers ของ Aspose.Words สำหรับ .NET เราเรียนรู้วิธีนำทางไปยังส่วนหัวและส่วนท้ายต่างๆ ภายในเอกสาร Word และเพิ่มเนื้อหาโดยใช้คลาส DocumentBuilder คุณลักษณะนี้ช่วยให้นักพัฒนาสามารถปรับแต่งส่วนหัวและส่วนท้ายสำหรับหน้าหรือส่วนเฉพาะได้ โดยให้ความยืดหยุ่นในการสร้างเอกสารระดับมืออาชีพและมีโครงสร้าง Aspose.Words สำหรับ .NET มอบชุดเครื่องมืออันทรงพลังสำหรับการจัดการเอกสาร Word โดยทางโปรแกรม ทำให้กลายเป็นไลบรารีที่จำเป็นสำหรับแอปพลิเคชันการประมวลผลเอกสาร

### คำถามที่พบบ่อยสำหรับการย้ายไปยังส่วนท้ายของส่วนหัวในเอกสาร word

#### ถาม: จุดประสงค์ของฟีเจอร์ Move To Headers/Footers ใน Aspose.Words for .NET คืออะไร

ตอบ: คุณลักษณะการย้ายไปยังส่วนหัว/ท้ายกระดาษใน Aspose.Words สำหรับ .NET ช่วยให้นักพัฒนาสามารถนำทางไปยังส่วนหัวและส่วนท้ายต่างๆ ภายในเอกสาร Word และเพิ่มเนื้อหาลงในรายการเหล่านั้นโดยทางโปรแกรม ซึ่งจะมีประโยชน์เมื่อคุณต้องการปรับแต่งหัวกระดาษและท้ายกระดาษสำหรับหน้าหรือส่วนต่างๆ ในเอกสาร

#### ถาม: ฉันสามารถมีส่วนหัวและส่วนท้ายที่แตกต่างกันสำหรับหน้าต่างๆ ในเอกสารได้หรือไม่

ตอบ: ได้ คุณสามารถระบุส่วนหัวและส่วนท้ายที่แตกต่างกันสำหรับหน้าแรก หน้าคู่ และหน้าคี่ได้โดยใช้คุณสมบัติ PageSetup.DifferentFirstPageHeaderFooter และ PageSetup.OddAndEvenPagesHeaderFooter ตามลำดับ

#### ถาม: ฉันจะเพิ่มเนื้อหาลงในส่วนหัวและส่วนท้ายที่ต้องการได้อย่างไร

ตอบ: หากต้องการเพิ่มเนื้อหาลงในส่วนหัวและส่วนท้ายที่เฉพาะเจาะจง ให้ใช้เมธอด MoveToHeaderFooter ของคลาส DocumentBuilder คุณสามารถย้ายไปยังส่วนหัว HeaderFirst, HeaderEven และ HeaderPrimary หรือ FooterFirst, FooterEven และ FooterPrimary ได้ตามความต้องการของคุณ

#### ถาม: ฉันสามารถสร้างส่วนหัวและส่วนท้ายสำหรับส่วนใดส่วนหนึ่งในเอกสารได้หรือไม่

ตอบ: ได้ คุณสามารถใช้เมธอด MoveToSection ของคลาส DocumentBuilder เพื่อย้ายไปยังส่วนเฉพาะในเอกสาร จากนั้นสร้างส่วนหัวและส่วนท้ายภายในส่วนนั้น

#### ถาม: ฉันจะบันทึกเอกสารที่แก้ไขลงในไฟล์โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: คุณสามารถบันทึกเอกสารที่แก้ไขไปยังตำแหน่งและรูปแบบที่ต้องการได้โดยใช้วิธีบันทึกของคลาสเอกสาร ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์และรูปแบบไฟล์ที่เหมาะสม (เช่น DOCX)
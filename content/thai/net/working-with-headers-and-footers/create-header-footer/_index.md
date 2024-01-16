---
title: สร้างส่วนท้ายของส่วนหัว
linktitle: สร้างส่วนท้ายของส่วนหัว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างส่วนหัวและส่วนท้ายในเอกสาร Word ของคุณด้วย Aspose.Words for .NET ปรับแต่งส่วนหัวและส่วนท้ายสำหรับแต่ละหน้า
type: docs
weight: 10
url: /th/net/working-with-headers-and-footers/create-header-footer/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ต่อไปนี้เพื่อสร้างส่วนหัวและส่วนท้ายโดยใช้ฟังก์ชัน Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words ไว้ในโปรเจ็กต์ของคุณก่อนที่จะใช้โค้ดนี้

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารของคุณที่จะบันทึกเอกสารที่แก้ไข

## ขั้นตอนที่ 2: สร้างเอกสารและตัวสร้างเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ที่นี่เราสร้างอินสแตนซ์ของ`Document` คลาสและตัวอย่างของ`DocumentBuilder` คลาสซึ่งจะทำให้เราสามารถจัดการเอกสารและเพิ่มองค์ประกอบได้

## ขั้นตอนที่ 3: ตั้งค่าพารามิเตอร์ของหน้าและส่วนหัวแรก

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// ระบุว่าเราต้องการให้ส่วนหัว/ส่วนท้ายของหน้าแรกแตกต่างจากหน้าอื่นๆ หรือไม่
// คุณยังสามารถใช้คุณสมบัติ PageSetup.OddAndEvenPagesHeaderFooter เพื่อระบุได้
// ส่วนหัว/ส่วนท้ายที่แตกต่างกันสำหรับหน้าคี่และหน้าคู่
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

เราตั้งค่าพารามิเตอร์ของหน้า รวมถึงระยะห่างของส่วนหัว จากนั้นจึงย้ายไปยังส่วนหัวหลัก (`HeaderPrimary`). เราใช้ตัวสร้างเอกสารเพื่อเพิ่มข้อความและจัดรูปแบบส่วนหัว

## ขั้นตอนที่ 4: แทรกรูปภาพและข้อความในส่วนหัวหลัก

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

เราใช้โปรแกรมสร้างเอกสารเพื่อแทรกรูปภาพที่มุมซ้ายบนของส่วนหัวหลัก จากนั้นเราจะเพิ่มข้อความที่จัดชิดขวา

## ขั้นตอนที่ 5: แทรกตารางในส่วนท้ายหลัก

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## ขั้นตอนที่ 6: เพิ่มหน้าใหม่และตั้งค่าส่วนหัว/ส่วนท้าย

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// ส่วนนี้ไม่จำเป็นต้องมีส่วนหัว/ส่วนท้ายที่แตกต่างกันสำหรับหน้าแรก เราต้องการเพียงหน้าชื่อเรื่องในเอกสารเท่านั้น
//และส่วนหัว/ส่วนท้ายของหน้านี้ได้ถูกกำหนดไว้แล้วในส่วนก่อนหน้า
pageSetup.DifferentFirstPageHeaderFooter = false;

// ส่วนนี้จะแสดงส่วนหัว/ส่วนท้ายของส่วนก่อนหน้าตามค่าเริ่มต้น เรียก currentSection.HeadersFooters.LinkToPrevious(false) เพื่อตัดลิงก์นี้
// ความกว้างของหน้าจะแตกต่างกันสำหรับส่วนใหม่ ดังนั้นเราจึงจำเป็นต้องตั้งค่าความกว้างของเซลล์ที่แตกต่างกันสำหรับตารางส่วนท้าย
currentSection.HeadersFooters.LinkToPrevious(false);

// หากเราต้องการใช้ส่วนหัว/ส่วนท้ายที่มีอยู่แล้วสำหรับส่วนนี้
//แต่หากมีการเปลี่ยนแปลงเล็กๆ น้อยๆ เล็กน้อย การคัดลอกส่วนหัว/ส่วนท้ายก็อาจสมเหตุสมผล
// จากส่วนก่อนหน้าและใช้การเปลี่ยนแปลงที่จำเป็นในตำแหน่งที่เราต้องการ
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// บันทึกเอกสาร
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 เราเพิ่มตัวแบ่งหน้าและตัวแบ่งส่วนเพื่อสร้างหน้าใหม่ที่จะมองเห็นส่วนหัว/ส่วนท้ายหลักได้ เราตั้งค่าพารามิเตอร์สำหรับส่วนใหม่ จากนั้นเราใช้`CopyHeadersFootersFromPreviousSection` วิธีการคัดลอกส่วนหัว/ส่วนท้ายจากส่วนก่อนหน้า สุดท้ายนี้ เราตั้งค่าความกว้างของเซลล์ที่เหมาะสมสำหรับตารางส่วนท้ายหลักและบันทึกเอกสาร

### ตัวอย่างซอร์สโค้ดเพื่อสร้างส่วนหัวและส่วนท้ายด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// ระบุว่าเราต้องการให้ส่วนหัว/ส่วนท้ายของหน้าแรกแตกต่างจากหน้าอื่นๆ หรือไม่
// คุณยังสามารถใช้คุณสมบัติ PageSetup.OddAndEvenPagesHeaderFooter เพื่อระบุได้
// ส่วนหัว/ส่วนท้ายที่แตกต่างกันสำหรับหน้าคี่และหน้าคู่
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// แทรกรูปภาพที่จัดตำแหน่งไว้ที่มุมบน/ซ้ายของส่วนหัว
// ระยะห่างจากขอบบน/ซ้ายของหน้าตั้งค่าไว้ที่ 10 จุด
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// เราใช้ตารางที่มีสองเซลล์เพื่อสร้างส่วนหนึ่งของข้อความในบรรทัด (พร้อมหมายเลขหน้า)
// ให้จัดชิดซ้าย และส่วนอื่น ๆ ของข้อความ (ที่มีลิขสิทธิ์) ให้จัดชิดขวา
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// ใช้ฟิลด์ PAGE และ NUMPAGES เพื่อคำนวณหมายเลขหน้าปัจจุบันและหลายหน้าโดยอัตโนมัติ
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// แบ่งหน้าเพื่อสร้างหน้าที่สองที่ส่วนหัว/ท้ายกระดาษหลักจะปรากฏ
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// ส่วนนี้ไม่ต้องการส่วนหัว/ส่วนท้ายของหน้าแรกที่แตกต่างกัน เราจำเป็นต้องมีหน้าชื่อเรื่องเพียงหน้าเดียวในเอกสาร
//และส่วนหัว/ส่วนท้ายของหน้านี้ได้ถูกกำหนดไว้แล้วในส่วนก่อนหน้า
pageSetup.DifferentFirstPageHeaderFooter = false;

// ส่วนนี้จะแสดงส่วนหัว/ส่วนท้ายจากส่วนก่อนหน้า
// โดยค่าเริ่มต้น ให้เรียก currentSection.HeadersFooters.LinkToPrevious(false) เพื่อยกเลิกความกว้างของหน้านี้
// จะแตกต่างกันสำหรับส่วนใหม่ ดังนั้นเราจึงจำเป็นต้องตั้งค่าความกว้างของเซลล์ที่แตกต่างกันสำหรับตารางส่วนท้าย
currentSection.HeadersFooters.LinkToPrevious(false);

// หากเราต้องการใช้ชุดส่วนหัว/ส่วนท้ายที่มีอยู่แล้วสำหรับส่วนนี้
// แต่หากมีการแก้ไขเล็กน้อย ก็อาจสมควรคัดลอกส่วนหัว/ส่วนท้าย
// จากส่วนก่อนหน้าและใช้การแก้ไขที่จำเป็นตามที่เราต้องการ
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเพิ่มส่วนหัวให้กับเอกสารของฉันใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการเพิ่มส่วนหัวให้กับเอกสารของคุณใน Aspose.Words คุณสามารถใช้`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` วิธี. วิธีนี้จะเพิ่มส่วนหัวหลักในส่วนแรกของเอกสารของคุณ

#### ถาม: ฉันจะเพิ่มส่วนท้ายลงในเอกสารของฉันใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการเพิ่มส่วนท้ายให้กับเอกสารของคุณใน Aspose.Words คุณสามารถใช้`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`วิธี. วิธีการนี้จะเพิ่มส่วนท้ายหลักให้กับส่วนแรกของเอกสารของคุณ

#### ถาม: ฉันจะเพิ่มข้อความลงในส่วนหัวหรือส่วนท้ายใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการเพิ่มข้อความลงในส่วนหัวหรือส่วนท้ายของคุณใน Aspose.Words คุณสามารถใช้`HeaderFooter.Paragraphs` คุณสมบัติเพื่อรับคอลเลกชันย่อหน้าของส่วนหัวหรือส่วนท้าย จากนั้นเพิ่มย่อหน้าที่มีข้อความของคุณลงในคอลเลกชันนี้โดยใช้`ParagraphCollection.Add` วิธี.

#### ถาม: ฉันสามารถปรับแต่งเนื้อหาส่วนหัวหรือส่วนท้ายด้วยรูปภาพและหมายเลขหน้าใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งเนื้อหาส่วนหัวหรือส่วนท้ายด้วยรูปภาพและหมายเลขหน้าใน Aspose.Words คุณสามารถใช้วัตถุเช่น`Shape` เพื่อเพิ่มรูปภาพและวัตถุเช่น`Field` เพื่อเพิ่มหมายเลขหน้าลงในส่วนหัวหรือส่วนท้ายของคุณ

#### ถาม: ฉันสามารถเปลี่ยนแบบอักษร ขนาด และสีของข้อความในส่วนหัวหรือส่วนท้ายใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถเปลี่ยนแบบอักษร ขนาด และสีของข้อความในส่วนหัวหรือส่วนท้ายใน Aspose.Words ได้ คุณสามารถเข้าถึงคุณสมบัติการจัดรูปแบบข้อความเช่น`Font` เพื่อเปลี่ยนแบบอักษร`Size` เพื่อปรับขนาดและ`Color`เพื่อตั้งค่าสีข้อความ
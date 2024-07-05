---
title: สร้างส่วนท้ายของส่วนหัว
linktitle: สร้างส่วนท้ายของส่วนหัว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มและปรับแต่งส่วนหัวและส่วนท้ายในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอนนี้ช่วยให้มั่นใจได้ถึงการจัดรูปแบบเอกสารอย่างมืออาชีพ
type: docs
weight: 10
url: /th/net/working-with-headers-and-footers/create-header-footer/
---

การเพิ่มส่วนหัวและส่วนท้ายลงในเอกสารของคุณสามารถเพิ่มความเป็นมืออาชีพและความสามารถในการอ่านได้ ด้วย Aspose.Words สำหรับ .NET คุณสามารถสร้างและปรับแต่งส่วนหัวและส่วนท้ายสำหรับเอกสาร Word ของคุณได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถใช้คุณลักษณะเหล่านี้ได้อย่างราบรื่น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

-  Aspose.Words สำหรับ .NET: ดาวน์โหลดและติดตั้งจาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: เช่น Visual Studio เพื่อเขียนและรันโค้ดของคุณ
- ความรู้พื้นฐานเกี่ยวกับ C#: ความเข้าใจเกี่ยวกับกรอบงาน C# และ .NET
- เอกสารตัวอย่าง: เอกสารตัวอย่างเพื่อใช้ส่วนหัวและส่วนท้าย หรือสร้างเอกสารใหม่ตามที่แสดงในบทช่วยสอน

## นำเข้าเนมสเปซ

ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการของ Aspose.Words

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

กำหนดไดเร็กทอรีที่จะบันทึกเอกสารของคุณ ซึ่งจะช่วยในการจัดการเส้นทางได้อย่างมีประสิทธิภาพ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## ขั้นตอนที่ 2: สร้างเอกสารใหม่

 สร้างเอกสารใหม่และก`DocumentBuilder` เพื่ออำนวยความสะดวกในการเพิ่มเติมเนื้อหา

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: กำหนดค่าการตั้งค่าหน้า

ตั้งค่าการตั้งค่าหน้า รวมถึงว่าหน้าแรกจะมีส่วนหัว/ส่วนท้ายที่แตกต่างกันหรือไม่

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## ขั้นตอนที่ 4: เพิ่มส่วนหัวในหน้าแรก

ย้ายไปยังส่วนหัวของหน้าแรกและกำหนดค่าข้อความส่วนหัว

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## ขั้นตอนที่ 5: เพิ่มส่วนหัวหลัก

ย้ายไปยังส่วนหัวหลักแล้วแทรกรูปภาพและข้อความ

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// แทรกรูปภาพลงในส่วนหัว
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## ขั้นตอนที่ 6: เพิ่มส่วนท้ายหลัก

ย้ายไปยังส่วนท้ายกระดาษหลักและสร้างตารางเพื่อจัดรูปแบบเนื้อหาส่วนท้าย

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// เพิ่มเลขหน้า
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
```

## ขั้นตอนที่ 7: เพิ่มเนื้อหาและตัวแบ่งหน้า

ย้ายไปที่จุดสิ้นสุดของเอกสาร เพิ่มตัวแบ่งหน้า และสร้างส่วนใหม่ด้วยการตั้งค่าหน้าที่แตกต่างกัน

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## ขั้นตอนที่ 8: คัดลอกส่วนหัวและส่วนท้ายจากส่วนก่อนหน้า

หากคุณต้องการนำส่วนหัวและส่วนท้ายจากส่วนก่อนหน้ามาใช้ซ้ำ ให้คัดลอกและใช้การแก้ไขที่จำเป็น

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## บทสรุป

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มและปรับแต่งส่วนหัวและส่วนท้ายในเอกสาร Word ของคุณได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Words for .NET สิ่งนี้จะช่วยปรับปรุงรูปลักษณ์และความเป็นมืออาชีพของเอกสารของคุณ ทำให้อ่านง่ายและน่าดึงดูดยิ่งขึ้น

## คำถามที่พบบ่อย

### คำถามที่ 1: Aspose.Words สำหรับ .NET คืออะไร

Aspose.Words for .NET เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรมภายในแอปพลิเคชัน .NET

### คำถามที่ 2: ฉันสามารถเพิ่มรูปภาพในส่วนหัวหรือส่วนท้ายได้หรือไม่

 ใช่ คุณสามารถเพิ่มรูปภาพลงในส่วนหัวหรือส่วนท้ายได้อย่างง่ายดายโดยใช้`DocumentBuilder.InsertImage` วิธี.

### คำถามที่ 3: ฉันจะตั้งค่าส่วนหัวและส่วนท้ายที่แตกต่างกันสำหรับหน้าแรกได้อย่างไร

 คุณสามารถตั้งค่าส่วนหัวและส่วนท้ายที่แตกต่างกันสำหรับหน้าแรกได้โดยใช้`DifferentFirstPageHeaderFooter` ทรัพย์สินของ`PageSetup` ระดับ.

### คำถามที่ 4: ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Words ได้ที่ไหน

 คุณสามารถค้นหาเอกสารที่ครอบคลุมได้ที่[หน้าเอกสารประกอบ Aspose.Words API](https://reference.aspose.com/words/net/).

### คำถามที่ 5: Aspose.Words รองรับหรือไม่

 ใช่ Aspose ให้การสนับสนุนผ่านทางพวกเขา[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/words/8).

---
title: ส่วนหัวของข้อความ
linktitle: ส่วนหัวของข้อความ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ส่วนหัว Setext เพื่อจัดรูปแบบเอกสารของคุณด้วย Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/setext-heading/
---

ในบทช่วยสอนนี้ เราจะอธิบายวิธีใช้ฟีเจอร์ส่วนหัวของ Setext กับ Aspose.Words สำหรับ .NET Setext Heading เป็นอีกวิธีหนึ่งในการจัดรูปแบบชื่อเรื่องในเอกสาร Markdown

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: การใช้รูปแบบส่วนหัวของ Setext

เราจะใช้รูปแบบย่อหน้า "หัวเรื่อง 1" เริ่มต้นเพื่อสร้างหัวเรื่องระดับ 1 ในเอกสารของเรา

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## ขั้นตอนที่ 3: การรีเซ็ตสไตล์

เรารีเซ็ตสไตล์ฟอนต์ที่ใช้ก่อนหน้านี้เพื่อหลีกเลี่ยงการผสมผสานสไตล์ที่ไม่ต้องการระหว่างย่อหน้า

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## ขั้นตอนที่ 4: การปรับแต่งระดับหัวเรื่อง Setext

เราสามารถปรับแต่งระดับส่วนหัวของ Setext ได้โดยการเพิ่มรูปแบบย่อหน้าใหม่ตามรูปแบบส่วนหัวที่มีอยู่ ในตัวอย่างนี้ เรากำลังสร้างสไตล์ "SetextHeading1" ตามสไตล์ "Heading 1" เพื่อแสดงส่วนหัวระดับ 1 ในรูปแบบ Setext

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้ายเราสามารถบันทึกเอกสารในรูปแบบที่ต้องการได้

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### ตัวอย่างซอร์สโค้ดสำหรับชื่อ Setext ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// รีเซ็ตสไตล์จากย่อหน้าก่อนหน้าเพื่อไม่ให้รวมสไตล์ระหว่างย่อหน้า
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// รีเซ็ตสไตล์จากย่อหน้าก่อนหน้าเพื่อไม่ให้รวมสไตล์ระหว่างย่อหน้า
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// ระดับส่วนหัวของ Setex จะถูกรีเซ็ตเป็น 2 หากย่อหน้าฐานมีระดับส่วนหัวมากกว่า 2
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### คำถามที่พบบ่อย

#### ถาม: ส่วนหัว Setext Markdown คืออะไร

ตอบ: ส่วนหัว Setext Markdown เป็นอีกทางเลือกหนึ่งในการสร้างส่วนหัวในเอกสาร Markdown ใช้อักขระขีดล่าง (= หรือ -) เพื่อระบุระดับต่างๆ ของส่วนหัว

#### ถาม: จะใช้ส่วนหัว Setext Markdown ได้อย่างไร

ตอบ: หากต้องการใช้ส่วนหัว Setext Markdown ให้วางขีดล่างใต้ข้อความชื่อเรื่อง ใช้เครื่องหมายเท่ากับ (=) สำหรับส่วนหัวระดับ 1 และเครื่องหมายขีดกลาง (-) สำหรับส่วนหัวระดับ 2

#### ถาม: มีข้อจำกัดในการใช้ส่วนหัว Setext Markdown หรือไม่

ตอบ: ส่วนหัว Setext Markdown มีข้อจำกัดในแง่ของลำดับชั้นของส่วนหัว และไม่มีความแตกต่างทางสายตาเท่ากับส่วนหัว Markdown มาตรฐาน

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของส่วนหัว Setext Markdown ได้หรือไม่

ตอบ: ใน Markdown มาตรฐาน จะไม่สามารถปรับแต่งลักษณะที่ปรากฏของส่วนหัว Setext Markdown ได้ มีลักษณะที่กำหนดไว้ล่วงหน้าตามอักขระขีดล่างที่ใช้

#### ถาม: ส่วนหัว Setext Markdown รองรับโดยเครื่องมือแก้ไข Markdown ทั้งหมดหรือไม่

ตอบ: การรองรับส่วนหัว Setext Markdown อาจแตกต่างกันไปตามตัวแก้ไข Markdown ตรวจสอบเอกสารเฉพาะของผู้จัดพิมพ์ของคุณเพื่อให้แน่ใจ
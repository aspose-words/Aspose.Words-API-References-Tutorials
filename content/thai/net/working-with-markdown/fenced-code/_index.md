---
title: รหัสรั้ว
linktitle: รหัสรั้ว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ฟีเจอร์โค้ดแบบรั้วกับ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/fenced-code/
---

ในตัวอย่างนี้ เราจะแนะนำคุณเกี่ยวกับวิธีใช้ฟีเจอร์โค้ดที่ไม่รั้วกับ Aspose.Words สำหรับ .NET รหัสรั้วใช้เพื่อแสดงบล็อกของรหัสที่มีการจัดรูปแบบเฉพาะ

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: การเพิ่มสไตล์สำหรับโค้ดที่ไม่รั้ว

 เราจะเพิ่มสไตล์ที่กำหนดเองสำหรับโค้ดที่ไม่รั้วโดยใช้`Styles.Add` วิธีการของ`Document` วัตถุ วัตถุ ในตัวอย่างนี้ เรากำลังสร้างสไตล์ที่เรียกว่า "FencedCode" สำหรับโค้ดที่ไม่พอใจ

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## ขั้นตอนที่ 3: การเพิ่มโค้ดที่ไม่พอใจโดยไม่มีข้อมูล

ตอนนี้เราสามารถเพิ่มบล็อกโค้ดแบบมีรั้วกั้นโดยไม่มีสตริงข้อมูลโดยใช้สไตล์ที่กำหนดเอง "FencedCode"

```csharp
builder.Writeln("This is an fenced code");
```

## ขั้นตอนที่ 4: เพิ่มรหัสไม่พอใจด้วยสตริงข้อมูล

นอกจากนี้เรายังสามารถเพิ่มบล็อกโค้ดแบบรั้วพร้อมสตริงข้อมูลโดยใช้สไตล์ที่กำหนดเองอื่นได้ ในตัวอย่างนี้ เรากำลังสร้างสไตล์ที่เรียกว่า "FencedCode.C#" เพื่อแสดงบล็อกของโค้ด C#

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Fenced Code โดยใช้ Aspose.Words สำหรับ .NET

```csharp
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### คำถามที่พบบ่อย

#### ถาม: รหัสตัวคั่นใน Markdown คืออะไร

ตอบ: รหัสที่ใช้ตัวคั่นใน Markdown เป็นวิธีการจัดรูปแบบที่ใช้แสดงรหัสในเอกสาร Markdown ประกอบด้วยการกำหนดกรอบโค้ดด้วยตัวคั่นเฉพาะ

#### ถาม: โค้ดแบบมีตัวคั่นใน Markdown มีประโยชน์อย่างไร

ตอบ: โค้ดที่มีตัวคั่นใน Markdown ช่วยเพิ่มความสามารถในการอ่านโค้ด และทำให้ผู้อ่านเข้าใจได้ง่ายขึ้น นอกจากนี้ยังอนุญาตให้รักษาการเน้นไวยากรณ์ในโปรแกรมแก้ไข Markdown บางตัว

#### ถาม: อะไรคือความแตกต่างระหว่างโค้ดที่มีตัวคั่นและเยื้องใน Markdown

ตอบ: โค้ดที่ใช้ตัวคั่นจะใช้ตัวคั่นเฉพาะเพื่อล้อมรอบโค้ด ในขณะที่โค้ดที่เยื้องเกี่ยวข้องกับการเยื้องโค้ดแต่ละบรรทัดด้วยการเว้นวรรคหรือแท็บ

#### ถาม: รหัสที่ใช้ตัวคั่นใน Markdown รองรับโดยโปรแกรมแก้ไข Markdown ทั้งหมดหรือไม่

ตอบ: การรองรับโค้ดแบบมีตัวคั่นใน Markdown อาจแตกต่างกันไปตามตัวแก้ไข Markdown ตรวจสอบเอกสารเฉพาะของผู้จัดพิมพ์ของคุณเพื่อให้แน่ใจ


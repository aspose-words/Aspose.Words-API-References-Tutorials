---
title: อ้าง
linktitle: อ้าง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้เครื่องหมายคำพูดกับ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/quote/
---

ในตัวอย่างนี้ เราจะอธิบายวิธีใช้คุณลักษณะเครื่องหมายคำพูดกับ Aspose.Words for .NET Quote ใช้เพื่อเน้นส่วนของข้อความโดยล้อมรอบด้วยเส้นขอบพิเศษ

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: การใช้รูปแบบการอ้างอิงเริ่มต้น

เราจะใช้รูปแบบย่อหน้าเริ่มต้นที่เรียกว่า "เครื่องหมายคำพูด" เพื่อใช้การจัดรูปแบบเครื่องหมายคำพูดกับข้อความ

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## ขั้นตอนที่ 3: การสร้างสไตล์สำหรับระดับที่ซ้อนกัน

 เราสามารถสร้างสไตล์สำหรับระดับที่ซ้อนกันโดยใช้`Styles.Add` วิธีการของ`Document` วัตถุ. ในตัวอย่างนี้ เรากำลังสร้างสไตล์ที่เรียกว่า "Quote1" เพื่อแสดงระดับใบเสนอราคาที่ซ้อนกัน

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### ตัวอย่างซอร์สโค้ดสำหรับการอ้างอิงด้วย Aspose.Words สำหรับ .NET


```csharp
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

// ตามค่าเริ่มต้น เอกสารจะจัดเก็บสไตล์ blockquote สำหรับระดับแรก
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// สร้างสไตล์สำหรับระดับที่ซ้อนกันผ่านการสืบทอดสไตล์
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้คุณลักษณะการอ้างอิงกับ Aspose.Words สำหรับ .NET แล้ว


### คำถามที่พบบ่อย

#### ถาม: การอ้างอิงใน Markdown คืออะไร

ตอบ: คำพูดใน Markdown เป็นวิธีการเน้นข้อความจากแหล่งอื่นหรืออ้างอิงคำพูดที่มีชื่อเสียง

#### ถาม: จะใช้เครื่องหมายคำพูดใน Markdown ได้อย่างไร

ตอบ: หากต้องการใช้เครื่องหมายคำพูดใน Markdown ให้ใส่ข้อความของเครื่องหมายคำพูดในวงเล็บมุม (`>`- การอ้างอิงแต่ละบรรทัดต้องขึ้นต้นด้วยเครื่องหมายบั้ง

#### ถาม: ราคา Markdown รองรับแอตทริบิวต์หรือไม่

ตอบ: การอ้างอิง Markdown ไม่รองรับแอตทริบิวต์เฉพาะ พวกเขาถูกเน้นโดยการจัดรูปแบบของข้อความที่ยกมา

#### ถาม: คุณสามารถฝังเครื่องหมายคำพูดใน Markdown ได้หรือไม่

ตอบ: ได้ คุณสามารถซ้อนเครื่องหมายคำพูดใน Markdown ได้โดยการเพิ่มวงเล็บเหลี่ยมระดับพิเศษ (`>`-
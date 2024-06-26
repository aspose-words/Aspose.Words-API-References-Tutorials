---
title: รหัสเยื้อง
linktitle: รหัสเยื้อง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้โค้ดที่เยื้องกับ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/indented-code/
---

ในตัวอย่างนี้ เราจะอธิบายวิธีใช้ฟีเจอร์โค้ดเยื้องกับ Aspose.Words สำหรับ .NET รหัสที่เยื้องถูกใช้เพื่อแสดงบล็อกของโค้ดด้วยการจัดรูปแบบเฉพาะ

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: เพิ่มสไตล์สำหรับโค้ดที่เยื้อง

เราจะเพิ่มสไตล์ที่กำหนดเองสำหรับโค้ดที่เยื้องโดยใช้`Styles.Add` วิธีการของ`Document` วัตถุ วัตถุ ในตัวอย่างนี้ เรากำลังสร้างสไตล์ที่เรียกว่า "IndentedCode" สำหรับโค้ดที่มีการเยื้อง

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## ขั้นตอนที่ 3: เพิ่มโค้ดที่เยื้อง

ตอนนี้เราสามารถเพิ่มบล็อกโค้ดที่เยื้องโดยใช้สไตล์ที่กำหนดเอง "IndentedCode"

```csharp
builder.Writeln("This is an indented code block");
```

### ตัวอย่างซอร์สโค้ดสำหรับโค้ดเยื้องด้วย Aspose.Words สำหรับ .NET

```csharp
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้ฟีเจอร์โค้ดเยื้องกับ Aspose.Words สำหรับ .NET แล้ว


### คำถามที่พบบ่อย

#### ถาม: รหัสเยื้องใน Markdown คืออะไร

ตอบ: รหัสที่เยื้องใน Markdown เป็นวิธีการจัดรูปแบบที่ใช้แสดงรหัสในเอกสาร Markdown ประกอบด้วยการเยื้องโค้ดแต่ละบรรทัดด้วยการเว้นวรรคหรือแท็บ

#### ถาม: จะใช้โค้ดเยื้องใน Markdown ได้อย่างไร

ตอบ: หากต้องการใช้โค้ดที่มีการเยื้องใน Markdown ให้เยื้องโค้ดแต่ละบรรทัดด้วยการเว้นวรรคหรือแท็บ

#### ถาม: ข้อดีของโค้ดเยื้องใน Markdown คืออะไร

ตอบ: โค้ดที่เยื้องใน Markdown ช่วยเพิ่มความสามารถในการอ่านโค้ด และทำให้ผู้อ่านเข้าใจได้ง่ายขึ้น

#### ถาม: อะไรคือความแตกต่างระหว่างโค้ดที่เยื้องและบล็อกโค้ดใน Markdown

ตอบ: โค้ดที่เยื้องจะใช้สำหรับโค้ดขนาดเล็กที่แทรกลงในข้อความ ในขณะที่โค้ดบล็อกจะใช้เพื่อแสดงโค้ดขนาดใหญ่ในการจัดรูปแบบแยกกัน

#### ถาม: โค้ดเยื้องใน Markdown ได้รับการสนับสนุนโดยโปรแกรมแก้ไข Markdown ทั้งหมดหรือไม่

ตอบ: การรองรับโค้ดที่เยื้องใน Markdown อาจแตกต่างกันไปตามโปรแกรมแก้ไข Markdown ตรวจสอบเอกสารเฉพาะของผู้จัดพิมพ์ของคุณเพื่อให้แน่ใจ
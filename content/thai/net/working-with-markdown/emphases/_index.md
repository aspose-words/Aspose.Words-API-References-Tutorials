---
title: เน้นย้ำ
linktitle: เน้นย้ำ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้การเน้น (ตัวหนาและตัวเอียง) ด้วย Aspose.Words for .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/emphases/
---

ในตัวอย่างนี้ เราจะอธิบายวิธีใช้การเน้นด้วย Aspose.Words สำหรับ .NET การเน้นใช้เพื่อเน้นบางส่วนของข้อความ เช่น ตัวหนาและตัวเอียง

## ขั้นตอนที่ 1: การเริ่มต้นเอกสาร

 ขั้นแรก เราจะเริ่มต้นเอกสารโดยการสร้างอินสแตนซ์ของ`Document` ชั้นเรียน

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## ขั้นตอนที่ 2: การใช้ตัวสร้างเอกสาร

ต่อไป เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: เพิ่มข้อความด้วยการเน้น

เราสามารถเพิ่มข้อความเน้นโดยการเปลี่ยนคุณสมบัติแบบอักษรของตัวสร้างเอกสาร ในตัวอย่างนี้ เราใช้ตัวหนาและตัวเอียงเพื่อเน้นส่วนต่างๆ ของข้อความ

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## ขั้นตอนที่ 4: บันทึกเอกสาร

 สุดท้ายเราสามารถบันทึกเอกสารในรูปแบบที่ต้องการได้ ในตัวอย่างนี้ เรากำลังใช้`.md` ส่วนขยายสำหรับรูปแบบ Markdown

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้การเน้นกับ Aspose.Words สำหรับ .NET แล้ว

### ตัวอย่างซอร์สโค้ดสำหรับ Emphases โดยใช้ Aspose.Words สำหรับ .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเน้นข้อความโดยใช้ Markdown ได้อย่างไร

ตอบ: หากต้องการเน้นข้อความโดยใช้ Markdown เพียงล้อมรอบข้อความด้วยสัญลักษณ์ที่เหมาะสม ใช้`*` หรือ`_` สำหรับตัวเอียง`**` หรือ`__` สำหรับตัวหนาและ`~~` สำหรับการขีดฆ่า

#### ถาม: เราสามารถรวมไฮไลท์ต่างๆ ไว้ในข้อความเดียวกันได้หรือไม่

 ตอบ: ได้ คุณสามารถรวมไฮไลต์ต่างๆ ไว้ในข้อความเดียวกันได้ ตัวอย่างเช่น คุณสามารถทำให้คำเป็นตัวหนาและตัวเอียงได้โดยใช้ทั้งสองคำ`**` และ`*` รอบคำ

#### ถาม: Markdown มีตัวเลือกการเน้นอะไรบ้าง

ตอบ: ตัวเลือกการไฮไลต์ที่มีอยู่ใน Markdown เป็นตัวเอียง (`*` หรือ`_`), ตัวหนา (`**` หรือ`__`) และขีดทับ (`~~`-

#### ถาม: ฉันจะจัดการกรณีที่ข้อความมีอักขระพิเศษที่ Markdown ใช้เพื่อไฮไลต์ได้อย่างไร

 ตอบ: หากข้อความของคุณมีอักขระพิเศษที่ Markdown ใช้เพื่อไฮไลต์ คุณสามารถหลีกเลี่ยงอักขระเหล่านั้นได้โดยนำหน้าด้วย a`\` - ตัวอย่างเช่น,`\*` จะแสดงเครื่องหมายดอกจันตามตัวอักษร

#### ถาม: เราสามารถปรับแต่งลักษณะที่ปรากฏของการไฮไลต์โดยใช้ CSS ได้หรือไม่

ตอบ: การไฮไลต์ใน Markdown มักจะแสดงผลโดยใช้สไตล์เริ่มต้นของเบราว์เซอร์ หากคุณแปลง Markdown เป็น HTML คุณจะปรับแต่งลักษณะที่ปรากฏของการไฮไลต์ได้โดยใช้กฎ CSS
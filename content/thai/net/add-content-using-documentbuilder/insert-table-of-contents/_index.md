---
title: แทรกสารบัญในเอกสาร Word
linktitle: แทรกสารบัญในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกสารบัญใน Word โดยใช้ Aspose.Words สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการนำทางเอกสารที่ราบรื่น
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเพิ่มสารบัญ (TOC) ลงในเอกสาร Word ของคุณอย่างมีประสิทธิภาพโดยใช้ Aspose.Words สำหรับ .NET คุณสมบัตินี้จำเป็นสำหรับการจัดระเบียบและการนำทางเอกสารที่มีความยาว เพิ่มความสามารถในการอ่าน และให้ภาพรวมอย่างรวดเร็วของส่วนต่างๆ ของเอกสาร

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความเข้าใจพื้นฐานเกี่ยวกับกรอบงาน C# และ .NET
- ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว
-  Aspose.Words สำหรับไลบรารี .NET หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/net/).

## นำเข้าเนมสเปซ

ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ C# ของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

มาแบ่งกระบวนการออกเป็นขั้นตอนที่ชัดเจน:

## ขั้นตอนที่ 1: เริ่มต้นเอกสาร Aspose.Words และ DocumentBuilder

 ขั้นแรก เริ่มต้น Aspose.Words ใหม่`Document` วัตถุและก`DocumentBuilder` ที่จะทำงานร่วมกับ:

```csharp
// เริ่มต้นเอกสารและ DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: แทรกสารบัญ

 ตอนนี้ให้แทรกสารบัญโดยใช้`InsertTableOfContents` วิธี:

```csharp
// แทรกสารบัญ
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## ขั้นตอนที่ 3: เริ่มเนื้อหาเอกสารในหน้าใหม่

เพื่อให้แน่ใจว่ามีการจัดรูปแบบที่เหมาะสม ให้เริ่มเนื้อหาเอกสารจริงในหน้าใหม่:

```csharp
// แทรกตัวแบ่งหน้า
builder.InsertBreak(BreakType.PageBreak);
```

## ขั้นตอนที่ 4: จัดโครงสร้างเอกสารของคุณด้วยส่วนหัว

จัดระเบียบเนื้อหาเอกสารของคุณโดยใช้สไตล์หัวเรื่องที่เหมาะสม:

```csharp
// กำหนดรูปแบบหัวเรื่อง
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

## ขั้นตอนที่ 5: อัปเดตและเติมสารบัญ

อัปเดตสารบัญเพื่อแสดงโครงสร้างเอกสาร:

```csharp
// อัพเดตฟิลด์สารบัญ
doc.UpdateFields();
```

## ขั้นตอนที่ 6: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารของคุณไปยังไดเร็กทอรีที่ระบุ:

```csharp
// บันทึกเอกสาร
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## บทสรุป

การเพิ่มสารบัญโดยใช้ Aspose.Words สำหรับ .NET นั้นตรงไปตรงมาและช่วยเพิ่มความสามารถในการใช้งานเอกสารของคุณอย่างมาก เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถจัดระเบียบและนำทางผ่านเอกสารที่ซับซ้อนได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของสารบัญได้หรือไม่
ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏและลักษณะการทำงานของสารบัญได้โดยใช้ Aspose.Words สำหรับ .NET API

### Aspose.Words รองรับการอัปเดตฟิลด์โดยอัตโนมัติหรือไม่
ใช่ Aspose.Words ช่วยให้คุณสามารถอัปเดตฟิลด์ต่างๆ เช่น สารบัญ แบบไดนามิกตามการเปลี่ยนแปลงเอกสาร

### ฉันสามารถสร้างสารบัญหลายรายการในเอกสารเดียวได้หรือไม่
Aspose.Words รองรับการสร้างสารบัญหลายรายการด้วยการตั้งค่าที่แตกต่างกันภายในเอกสารเดียว

### Aspose.Words เข้ากันได้กับ Microsoft Word เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Words รับประกันความเข้ากันได้กับรูปแบบ Microsoft Word เวอร์ชันต่างๆ

### ฉันจะขอความช่วยเหลือและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Words ได้ที่ไหน
หากต้องการความช่วยเหลือเพิ่มเติม โปรดไปที่[ฟอรั่ม Aspose.Words](https://forum.aspose.com/c/words/8) หรือตรวจสอบ[เอกสารอย่างเป็นทางการ](https://reference.aspose.com/words/net/).
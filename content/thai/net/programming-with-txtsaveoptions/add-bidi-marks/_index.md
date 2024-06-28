---
title: เพิ่มเครื่องหมาย Bidi ในเอกสาร Word
linktitle: เพิ่มเครื่องหมาย Bidi ในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้การเพิ่ม Bidi Marks ลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET และสร้างเอกสารหลายภาษาระดับมืออาชีพ
type: docs
weight: 10
url: /th/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง แก้ไข และจัดการเอกสาร Word ในแอปพลิเคชัน C# หนึ่งในคุณสมบัติที่นำเสนอโดย Aspose.Words คือความสามารถในการเพิ่มเครื่องหมาย Bidi (สองทิศทาง) ลงในเอกสาร ในคู่มือนี้ เราจะอธิบายวิธีใช้ซอร์สโค้ด C# ของ Aspose.Words สำหรับ .NET เพื่อเพิ่ม Bidi Marks ลงในเอกสาร

## ทำความเข้าใจกับไลบรารี Aspose.Words

ก่อนที่จะเจาะลึกโค้ด สิ่งสำคัญคือต้องทำความเข้าใจไลบรารี Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารียอดนิยมที่ทำให้การประมวลผลคำด้วยเอกสาร Word ง่ายและมีประสิทธิภาพ มีฟีเจอร์มากมายสำหรับการสร้าง แก้ไข และจัดการเอกสาร Word รวมถึงการเพิ่ม Bidi Marks

## การสร้างเอกสารและเพิ่มเนื้อหา

ขั้นตอนแรกคือการสร้างเอกสารใหม่และเพิ่มเนื้อหาลงไป ใช้คลาสเอกสารเพื่อสร้างอินสแตนซ์เอกสารใหม่ จากนั้นใช้คลาส DocumentBuilder เพื่อเพิ่มข้อความลงในเอกสาร นี่คือตัวอย่าง:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

ในตัวอย่างนี้ เราสร้างเอกสารใหม่และใช้ DocumentBuilder เพื่อเพิ่มข้อความ เราได้เพิ่มข้อความสามบรรทัด: บรรทัดหนึ่งเป็นภาษาอังกฤษ หนึ่งบรรทัดเป็นภาษาฮีบรู และอีกหนึ่งบรรทัดเป็นภาษาอาหรับเพื่อสาธิตการเพิ่มเนื้อหาในภาษาต่างๆ

## เพิ่มเครื่องหมายร่างกาย

เมื่อเพิ่มเนื้อหาแล้ว เราก็สามารถเพิ่ม Bidi Marks ลงในเอกสารได้แล้ว สำหรับสิ่งนี้ เราใช้คลาส TxtSaveOptions และตั้งค่าคุณสมบัติ AddBidiMarks ให้เป็นจริง มีวิธีดังนี้:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

ในตัวอย่างนี้ เราสร้างอินสแตนซ์ของ TxtSaveOptions และตั้งค่าคุณสมบัติ AddBidiMarks เป็นจริง ต่อไป เราใช้วิธีบันทึกของคลาสเอกสารเพื่อบันทึกเอกสารด้วย Bidi Marks

### ตัวอย่างซอร์สโค้ดสำหรับฟังก์ชัน "เพิ่ม Bidi Marks" ด้วย Aspose.Words สำหรับ .NET

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและเพิ่มเนื้อหา
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// เพิ่มเครื่องหมาย Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## บทสรุป

ในคู่มือนี้ เราได้อธิบายวิธีใช้ Aspose.Words สำหรับ .NET เพื่อเพิ่ม Bidi Marks ลงในเอกสาร Word โดยใช้ซอร์สโค้ด C# ที่ให้มา เมื่อทำตามขั้นตอนที่ให้ไว้ คุณจะสามารถเพิ่ม Bidi Marks ลงในเอกสาร Word ในแอปพลิเคชัน C# ของคุณได้อย่างง่ายดาย Aspose.Words มอบความยืดหยุ่นและพลังมหาศาลสำหรับการประมวลผลคำด้วยการจัดรูปแบบข้อความและการจัดการภาษา ช่วยให้คุณสร้างเอกสารหลายภาษาอย่างมืออาชีพ

### คำถามที่พบบ่อย

#### ถาม: Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง แก้ไข และจัดการเอกสาร Word ในแอปพลิเคชัน C# มีคุณสมบัติมากมายสำหรับการประมวลผลคำด้วยเอกสาร Word รวมถึงการเพิ่มเครื่องหมาย Bidi (สองทิศทาง)

#### ถาม: Aspose.Words สำหรับ .NET นำเสนอฟีเจอร์อะไรบ้าง
Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการสร้าง แก้ไข และจัดการเอกสาร Word คุณสมบัติบางอย่างเหล่านี้รวมถึงการสร้างเอกสาร การเพิ่มเนื้อหา การจัดรูปแบบข้อความ การจัดการตาราง การรวมและการแยกเอกสาร การแปลงเอกสาร และอื่นๆ

#### ถาม: ฉันจะเพิ่ม Bidi Marks ลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร
คุณสามารถเพิ่ม Bidi Marks ลงในเอกสาร Word ได้โดยทำตามขั้นตอนเหล่านี้:

 สร้างเอกสารใหม่โดยใช้`Document` ชั้นเรียน

 ใช้`DocumentBuilder` คลาสเพื่อเพิ่มเนื้อหาลงในเอกสาร

 เมื่อคุณเพิ่มเนื้อหาแล้ว ให้ใช้`TxtSaveOptions` คลาสและตั้งค่า`AddBidiMarks`ทรัพย์สินเพื่อ`true`.

 บันทึกเอกสารด้วย Bidi Marks โดยใช้`Save` วิธีการของ`Document` ชั้นเรียน

#### ถาม: Aspose.Words รองรับหลายภาษาในการเพิ่ม Bidi Marks หรือไม่
ใช่ Aspose.Words รองรับหลายภาษาสำหรับการเพิ่ม Bidi Marks คุณสามารถเพิ่ม Bidi Marks ลงในข้อความในภาษาต่างๆ เช่น อังกฤษ ฮิบรู และอารบิก โดยใช้ Aspose.Words สำหรับ .NET

#### ถาม: มีตัวเลือกเพิ่มเติมในการบันทึกเอกสารด้วย Bidi Marks หรือไม่
 ได้ คุณสามารถระบุตัวเลือกอื่นๆ ได้เมื่อบันทึกเอกสารด้วย Bidi Marks โดยใช้`TxtSaveOptions` ชั้นเรียน ตัวอย่างเช่น คุณสามารถตั้งค่ารูปแบบการบันทึกเอกสาร ตัวเลือกการเข้ารหัส ฯลฯ
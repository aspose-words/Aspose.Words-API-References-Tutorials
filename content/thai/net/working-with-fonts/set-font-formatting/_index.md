---
title: ตั้งค่าการจัดรูปแบบตัวอักษร
linktitle: ตั้งค่าการจัดรูปแบบตัวอักษร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าการจัดรูปแบบแบบอักษรในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET และสร้างเอกสารที่น่าสนใจ
type: docs
weight: 10
url: /th/net/working-with-fonts/set-font-formatting/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีตั้งค่าการจัดรูปแบบแบบอักษรในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณจะได้เรียนรู้วิธีใช้สไตล์ต่างๆ เช่น ตัวหนา สี ตัวเอียง แบบอักษร ขนาด ระยะห่าง และการขีดเส้นใต้

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: สร้างและจัดรูปแบบเอกสาร
 สร้างอินสแตนซ์ของ`Document` ชั้นเรียนและ`DocumentBuilder` คลาสเพื่อสร้างเอกสาร ใช้`Font` ทรัพย์สินของ`DocumentBuilder`เพื่อเข้าถึงคุณสมบัติการจัดรูปแบบแบบอักษร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## ขั้นตอนที่ 3: บันทึกเอกสาร
 ใช้`Save` วิธีการบันทึกเอกสารโดยใช้การจัดรูปแบบแบบอักษร แทนที่`"WorkingWithFonts.SetFontFormatting.docx"` พร้อมชื่อไฟล์ที่ต้องการ

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าการจัดรูปแบบแบบอักษรโดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## บทสรุป
ขอแสดงความยินดี! ตอนนี้คุณรู้วิธีตั้งค่าการจัดรูปแบบแบบอักษรในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET แล้ว คุณสามารถสำรวจตัวเลือกการจัดรูปแบบแบบอักษรเพิ่มเติมและสร้างเอกสาร Word ที่เป็นส่วนตัวและน่าดึงดูดได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะใช้รูปแบบตัวหนากับแบบอักษรในเอกสาร Word โดยใช้ Aspose.Words ได้อย่างไร

ตอบ: หากต้องการใช้ลักษณะตัวหนากับแบบอักษรในเอกสาร Word โดยใช้ Aspose.Words คุณสามารถใช้ API เพื่อนำทางไปยังแบบอักษรที่ต้องการและตั้งค่าสไตล์เป็น "ตัวหนา" ซึ่งจะใช้รูปแบบตัวหนากับแบบอักษรที่ระบุ

#### ถาม: เป็นไปได้หรือไม่ที่จะใช้รูปแบบตัวเอียงกับส่วนใดส่วนหนึ่งของข้อความในเอกสาร Word ด้วย Aspose.Words

ตอบ: ได้ ด้วย Aspose.Words คุณสามารถนำลักษณะตัวเอียงไปใช้กับข้อความเฉพาะส่วนในเอกสาร Word ได้ คุณสามารถใช้ API เพื่อเลือกช่วงข้อความที่ต้องการและตั้งค่าสไตล์เป็น "ตัวเอียง"

#### ถาม: ฉันจะเปลี่ยนสีแบบอักษรในเอกสาร Word โดยใช้ Aspose.Words ได้อย่างไร

ตอบ: หากต้องการเปลี่ยนสีแบบอักษรในเอกสาร Word โดยใช้ Aspose.Words คุณสามารถเข้าถึงแบบอักษรที่ต้องการได้โดยใช้ API และตั้งค่าสีให้เป็นสีที่ต้องการ สิ่งนี้จะเปลี่ยนสีตัวอักษรในเอกสาร

#### ถาม: เป็นไปได้ไหมที่จะเปลี่ยนขนาดตัวอักษรในเอกสาร Word โดยใช้ Aspose.Words

ตอบ: ได้ คุณสามารถเปลี่ยนขนาดตัวอักษรในเอกสาร Word ได้โดยใช้ Aspose.Words API ช่วยให้คุณเข้าถึงแบบอักษรและกำหนดขนาดเป็นจุดหรือจุดมาตราส่วนได้ ขึ้นอยู่กับความต้องการของคุณ

#### ถาม: ฉันสามารถใช้รูปแบบฟอนต์หลายรูปแบบ เช่น ตัวหนาและตัวเอียง กับข้อความเดียวกันในเอกสาร Word ได้หรือไม่

ตอบ: ได้ ด้วย Aspose.Words คุณสามารถนำรูปแบบฟอนต์หลายรูปแบบ เช่น ตัวหนาและตัวเอียง ไปใช้กับข้อความเดียวกันในเอกสาร Word ได้ คุณสามารถใช้ API เพื่อตั้งค่าลักษณะแบบอักษรต่างๆ ที่คุณต้องการสำหรับส่วนต่างๆ ของข้อความ
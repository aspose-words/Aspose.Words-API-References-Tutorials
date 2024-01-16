---
title: เปิดคุณสมบัติประเภท
linktitle: เปิดคุณสมบัติประเภท
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเปิดใช้งานและใช้คุณสมบัติ Open Type ใน Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/enable-opentype-features/open-type-features/
---

ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีเปิดใช้งานและใช้คุณสมบัติ Open Type ใน Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ ในตอนท้ายของคู่มือนี้ คุณจะสามารถใช้งานฟีเจอร์ Open Type ในเอกสาร Word ของคุณได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: โหลดเอกสาร
ในการเริ่มต้น ให้โหลดเอกสารโดยใช้คลาสเอกสาร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## ขั้นตอนที่ 2: เปิดใช้งานคุณสมบัติประเภทเปิด
หากต้องการเปิดใช้งานคุณสมบัติ Open Type ให้ตั้งค่าคุณสมบัติ TextShaperFactory ของคลาส LayoutOptions เป็นอินสแตนซ์ของแฟกทอรี text shaper ที่ต้องการ ในตัวอย่างนี้ เราใช้ HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## ขั้นตอนที่ 3: บันทึกเอกสาร
หลังจากเปิดใช้งานคุณสมบัติ Open Type แล้ว ให้บันทึกเอกสารในรูปแบบเอาต์พุตที่ต้องการ เช่น PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับคุณสมบัติประเภทเปิดโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการใช้คุณสมบัติ Open Type ใน Aspose.Words สำหรับ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเปิดใช้งานและใช้คุณสมบัติ Open Type ใน Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา ตอนนี้คุณสามารถทำงานกับฟีเจอร์ Open Type ในเอกสาร Word ของคุณได้

คุณสมบัติ Open Type นำเสนอความสามารถในการพิมพ์และการจัดรูปแบบข้อความที่ได้รับการปรับปรุง ช่วยให้คุณสร้างเอกสารที่ดึงดูดสายตาและดูเป็นมืออาชีพ ทดลองใช้โรงงานเครื่องมือจัดรูปแบบข้อความต่างๆ และสำรวจความเป็นไปได้ของฟีเจอร์ Open Type ในโปรเจ็กต์ของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเปิดใช้งานคุณสมบัติ OpenType ใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการเปิดใช้งานคุณสมบัติ OpenType ใน Aspose.Words สำหรับ .NET คุณต้องทำตามขั้นตอนที่กล่าวถึงในบทช่วยสอน

#### ถาม: Aspose.Words สำหรับ .NET รองรับฟีเจอร์ OpenType ใดบ้าง

ตอบ: Aspose.Words สำหรับ .NET รองรับคุณสมบัติ OpenType หลายประการ เช่น ตัวอักษรควบ รูปแบบสัญลักษณ์ การแทนที่ตามบริบท และอื่นๆ

#### ถาม: ฉันจะตรวจสอบได้อย่างไรว่าฟีเจอร์ OpenType ได้รับการรองรับในแบบอักษรเฉพาะหรือไม่

ตอบ: คุณสามารถตรวจสอบว่าฟีเจอร์ OpenType ได้รับการสนับสนุนในแบบอักษรเฉพาะหรือไม่โดยใช้`Font.OpenTypeFeatures` วิธีการใน Aspose.Words สำหรับ .NET

#### ถาม: Aspose.Words สำหรับ .NET รองรับฟีเจอร์การจัดรูปแบบข้อความอื่นๆ ใดบ้าง

ตอบ: นอกเหนือจากฟีเจอร์ OpenType แล้ว Aspose.Words สำหรับ .NET ยังรองรับฟีเจอร์การจัดรูปแบบข้อความอื่นๆ เช่น การจัดรูปแบบย่อหน้า การสร้างตาราง การเพิ่มรูปภาพ เป็นต้น

#### ถาม: ฉันสามารถใช้ฟีเจอร์ OpenType ใน Aspose.Words สำหรับ .NET ทุกเวอร์ชันได้หรือไม่

ตอบ: คุณสมบัติ OpenType ได้รับการสนับสนุนใน Aspose.Words สำหรับ .NET เวอร์ชันใหม่กว่า ตรวจสอบให้แน่ใจว่าคุณใช้เวอร์ชันที่เข้ากันได้เพื่อรับประโยชน์จากคุณสมบัติเหล่านี้
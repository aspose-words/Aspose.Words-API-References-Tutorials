---
title: รูปแบบกฎแนวนอนในเอกสาร Word
linktitle: รูปแบบกฎแนวนอนในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีจัดรูปแบบกฎแนวนอนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/horizontal-rule-format/
---
ในตัวอย่างที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีจัดรูปแบบกฎแนวนอนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ ในตอนท้ายของคู่มือนี้ คุณจะสามารถปรับแต่งการจัดตำแหน่ง ความกว้าง ความสูง สี และคุณสมบัติอื่นๆ ของกฎแนวนอนได้

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้าง DocumentBuilder และแทรกกฎแนวนอน
ในการเริ่มต้น ให้สร้างออบเจ็กต์ DocumentBuilder และใช้เมธอด InsertHorizontalRule เพื่อแทรกกฎแนวนอน:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## ขั้นตอนที่ 2: เข้าถึงรูปแบบกฎแนวนอน
จากนั้น เข้าถึงคุณสมบัติ HorizonRuleFormat ของออบเจ็กต์ Shape เพื่อเรียกตัวเลือกการจัดรูปแบบ:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## ขั้นตอนที่ 3: ปรับแต่งตัวเลือกการจัดรูปแบบ
ตอนนี้คุณสามารถปรับแต่งตัวเลือกการจัดรูปแบบต่างๆ สำหรับกฎแนวนอนได้ ตัวอย่างเช่น คุณสามารถปรับการจัดตำแหน่ง ความกว้าง ความสูง สี และการแรเงาได้:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
หลังจากจัดรูปแบบกฎแนวนอนแล้ว ให้บันทึกเอกสารลงในไฟล์โดยใช้วิธีบันทึกของออบเจ็กต์ Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับรูปแบบกฎแนวนอนโดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการจัดรูปแบบกฎแนวนอนโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

อย่าลืมปรับโค้ดตามความต้องการเฉพาะของคุณ และปรับปรุงด้วยฟังก์ชันเพิ่มเติมตามความจำเป็น

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีจัดรูปแบบกฎแนวนอนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถปรับแต่งลักษณะที่ปรากฏของกฎแนวนอนเพื่อปรับปรุงเค้าโครงภาพของเอกสารของคุณได้

ทดลองใช้ตัวเลือกการจัดรูปแบบต่างๆ เพื่อให้ได้สไตล์และเอฟเฟกต์ที่ต้องการสำหรับกฎแนวนอนของคุณ

### คำถามที่พบบ่อยเกี่ยวกับรูปแบบกฎแนวนอนในเอกสาร word

#### ถาม: ฉันสามารถใช้สีที่ต่างกันกับกฎแนวนอนได้หรือไม่

ตอบ: แน่นอน! ด้วย Aspose.Words สำหรับ .NET คุณสามารถปรับแต่งสีของกฎแนวนอนได้อย่างง่ายดายโดยการตั้งค่าคุณสมบัติสีให้เป็นค่าสีที่ต้องการ ซึ่งจะทำให้คุณสามารถจับคู่กฎแนวนอนกับการออกแบบโดยรวมของเอกสารได้

#### ถาม: สามารถปรับความกว้างและความสูงของกฎแนวนอนได้หรือไม่

ตอบ: ได้ คุณสามารถควบคุมความกว้างและความสูงของกฎแนวนอนได้อย่างเต็มที่ ด้วยการปรับเปลี่ยนคุณสมบัติ widthPercent และ Height คุณจะได้ขนาดที่ต้องการสำหรับกฎแนวนอน

#### ถาม: ฉันสามารถเปลี่ยนการจัดแนวของเส้นแนวนอนภายในเอกสารได้หรือไม่

ตอบ: แน่นอน! Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถระบุการจัดตำแหน่งของกฎแนวนอนโดยใช้คุณสมบัติ Alignment คุณสามารถเลือกจากตัวเลือกต่างๆ เช่น กึ่งกลาง ซ้าย ขวา และชิดขอบ

#### ถาม: ฉันสามารถใช้การแรเงาหรือสีพื้นหลังกับกฎแนวนอนได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มการแรเงาหรือสีพื้นหลังให้กับกฎแนวนอนได้ ตามค่าเริ่มต้น คุณสมบัติ NoShade จะถูกตั้งค่าเป็น true แต่คุณสามารถตั้งค่าเป็น false และกำหนดการแรเงาโดยใช้วิธีการที่เหมาะสมได้

#### ถาม: ฉันสามารถแทรกกฎแนวนอนหลายกฎในเอกสารเดียวได้หรือไม่

ตอบ: แน่นอน! คุณสามารถแทรกกฎแนวนอนหลายกฎในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เพียงทำซ้ำขั้นตอนในบทช่วยสอนตามที่จำเป็นเพื่อเพิ่มกฎแนวนอนได้มากเท่าที่คุณต้องการ
---
title: รูปแบบกฎแนวนอนในเอกสาร Word
linktitle: รูปแบบกฎแนวนอนในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกกฎแนวนอนที่ปรับแต่งได้ลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ปรับปรุงระบบอัตโนมัติของเอกสารของคุณ
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## การแนะนำ

ในขอบเขตของการพัฒนา .NET การจัดการและการจัดรูปแบบเอกสาร Word โดยทางโปรแกรมอาจเป็นงานที่น่ากังวล โชคดีที่ Aspose.Words สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพ ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการเอกสารโดยอัตโนมัติได้อย่างง่ายดาย บทความนี้จะเจาะลึกถึงคุณลักษณะที่สำคัญประการหนึ่ง นั่นคือ การแทรกกฎแนวนอนลงในเอกสาร Word ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้นด้วย Aspose.Words การเรียนรู้ความสามารถนี้จะช่วยปรับปรุงกระบวนการสร้างเอกสารของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้กฎแนวนอนโดยใช้ Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- Visual Studio: ติดตั้ง Visual Studio IDE สำหรับการพัฒนา .NET
- Aspose.Words สำหรับ .NET: ดาวน์โหลดและติดตั้ง Aspose.Words สำหรับ .NET จาก[ที่นี่](https://releases.aspose.com/words/net/).
- ความรู้พื้นฐาน C#: ความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#
-  คลาส DocumentBuilder: ความเข้าใจเกี่ยวกับ`DocumentBuilder` คลาสใน Aspose คำสำหรับการจัดการเอกสาร

## นำเข้าเนมสเปซ

ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ C# ของคุณ:

```csharp
using Aspose.Words;
using System.Drawing;
```

เนมสเปซเหล่านี้ให้การเข้าถึงคลาส Aspose.Words สำหรับการจัดการเอกสารและคลาส .NET มาตรฐานสำหรับการจัดการสี

เรามาแจกแจงขั้นตอนการเพิ่มกฎแนวนอนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ให้เป็นขั้นตอนที่ครอบคลุม:

## ขั้นตอนที่ 1: เริ่มต้น DocumentBuilder และตั้งค่าไดเรกทอรี

 ขั้นแรก ให้เริ่มต้น a`DocumentBuilder` object และกำหนดเส้นทางไดเรกทอรีที่จะบันทึกเอกสาร

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: แทรกกฎแนวนอน

 ใช้`InsertHorizontalRule()` วิธีการของ`DocumentBuilder` คลาสเพื่อเพิ่มกฎแนวนอน

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## ขั้นตอนที่ 3: ปรับแต่งรูปแบบกฎแนวนอน

 เข้าถึง`HorizontalRuleFormat` คุณสมบัติของรูปร่างที่แทรกไว้เพื่อปรับแต่งลักษณะที่ปรากฏของกฎแนวนอน

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- การจัดตำแหน่ง: ระบุการจัดตำแหน่งของกฎแนวนอน (`HorizontalRuleAlignment.Center` ในตัวอย่างนี้)
- widthPercent: ตั้งค่าความกว้างของกฎแนวนอนเป็นเปอร์เซ็นต์ของความกว้างของหน้า (70% ในตัวอย่างนี้)
- ความสูง: กำหนดความสูงของกฎแนวนอนเป็นจุด (3 จุดในตัวอย่างนี้)
- สี: ตั้งค่าสีของกฎแนวนอน (`Color.Blue` ในตัวอย่างนี้)
- NoShade: ระบุว่ากฎแนวนอนควรมีเงา (`true` ในตัวอย่างนี้)

## ขั้นตอนที่ 4: บันทึกเอกสาร

 สุดท้าย ให้บันทึกเอกสารที่แก้ไขโดยใช้ไฟล์`Save` วิธีการของ`Document` วัตถุ วัตถุ

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## บทสรุป

การเรียนรู้การแทรกกฎแนวนอนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET จะช่วยเพิ่มความสามารถด้านเอกสารอัตโนมัติของคุณ ด้วยการใช้ประโยชน์จากความยืดหยุ่นและพลังของ Aspose.Words นักพัฒนาจึงสามารถปรับปรุงกระบวนการสร้างและจัดรูปแบบเอกสารได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words for .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับเอกสาร Word โดยทางโปรแกรมในแอปพลิเคชัน .NET

### ฉันจะดาวน์โหลด Aspose.Words สำหรับ .NET ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Words สำหรับ .NET ได้จาก[ที่นี่](https://releases.aspose.com/words/net/).

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของกฎแนวนอนใน Aspose.Words ได้หรือไม่
ใช่ คุณสามารถปรับแต่งแง่มุมต่างๆ ได้ เช่น การจัดตำแหน่ง ความกว้าง ความสูง สี และการแรเงาของกฎแนวนอนโดยใช้ Aspose.Words

### Aspose.Words เหมาะสำหรับการประมวลผลเอกสารระดับองค์กรหรือไม่
ใช่ Aspose.Words ถูกนำมาใช้กันอย่างแพร่หลายในสภาพแวดล้อมขององค์กรสำหรับความสามารถในการจัดการเอกสารที่มีประสิทธิภาพ

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 สำหรับการสนับสนุนและการมีส่วนร่วมของชุมชน โปรดไปที่[ฟอรั่ม Aspose.Words](https://forum.aspose.com/c/words/8).

---
title: รหัสรั้ว
linktitle: รหัสรั้ว
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มรหัสที่ไม่รั้วและสตริงข้อมูลลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET รวมคำแนะนำทีละขั้นตอน พัฒนาทักษะการจัดรูปแบบเอกสารของคุณ
type: docs
weight: 10
url: /th/net/working-with-markdown/fenced-code/
---
## การแนะนำ

สวัสดีเพื่อนผู้เขียนโค้ด! วันนี้ เรากำลังดำดิ่งสู่โลกของ Aspose.Words สำหรับ .NET เพื่อฝึกฝนศิลปะในการเพิ่มโค้ดแบบมีรั้วและโค้ดแบบมีรั้วด้วยสตริงข้อมูลลงในเอกสาร Word ของคุณ ลองนึกภาพเอกสาร Word ของคุณเป็นผืนผ้าใบ และคุณซึ่งเป็นศิลปิน กำลังจะวาดภาพด้วยความแม่นยำของนักพัฒนาผู้ช่ำชอง ด้วย Aspose.Words คุณจะได้รับพลังในการปรับปรุงเอกสารของคุณโดยทางโปรแกรมด้วยบล็อกโค้ดที่มีโครงสร้างและจัดรูปแบบ ทำให้เอกสารทางเทคนิคของคุณโดดเด่นด้วยความเป็นมืออาชีพและชัดเจน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเข้าสู่บทช่วยสอน เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:

- ความรู้พื้นฐานของ C#: ความเข้าใจทั่วไปเกี่ยวกับ C# จะช่วยให้คุณเข้าใจแนวคิดต่างๆ ได้อย่างรวดเร็ว
-  Aspose.Words สำหรับ .NET: คุณต้องติดตั้ง Aspose.Words สำหรับ .NET ถ้ายังไม่มีก็คว้าไว้เลย[ที่นี่](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: Visual Studio หรือ C# IDE อื่น ๆ ที่คุณคุ้นเคย

## นำเข้าเนมสเปซ

ก่อนอื่น คุณต้องนำเข้าเนมสเปซที่จำเป็นก่อน นี่เหมือนกับการรวบรวมเครื่องมือทั้งหมดของคุณก่อนเริ่มโปรเจ็กต์

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

ตอนนี้เรามาแบ่งกระบวนการทีละขั้นตอนกัน

## ขั้นตอนที่ 1: การตั้งค่าโครงการของคุณ

ก่อนที่เราจะสร้างบล็อกโค้ดที่มีรูปแบบสวยงามในเอกสาร Word ของเราได้ เราจำเป็นต้องตั้งค่าโปรเจ็กต์ใหม่ใน Visual Studio

1. สร้างโครงการใหม่: เปิด Visual Studio และสร้างแอปพลิเคชันคอนโซล C# ใหม่
2. เพิ่มการอ้างอิง Aspose.Words: ติดตั้ง Aspose.Words ผ่าน NuGet Package Manager คุณสามารถทำได้โดยคลิกขวาที่โปรเจ็กต์ของคุณใน Solution Explorer เลือก "จัดการแพ็คเกจ NuGet" และค้นหา Aspose.Words

## ขั้นตอนที่ 2: เริ่มต้น DocumentBuilder

ตอนนี้โปรเจ็กต์ของคุณได้รับการตั้งค่าแล้ว มาเริ่มต้น DocumentBuilder ซึ่งจะเป็นเครื่องมือหลักในการเพิ่มเนื้อหาลงในเอกสาร Word

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 3: สร้างสไตล์สำหรับโค้ด Fence

หากต้องการเพิ่มโค้ดแบบมีรั้ว เราต้องสร้างสไตล์ก่อน คิดว่านี่เป็นการตั้งค่าธีมสำหรับบล็อคโค้ดของเรา

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## ขั้นตอนที่ 4: เพิ่มรหัส Fenced ลงในเอกสาร

เมื่อสไตล์ของเราพร้อมแล้ว ตอนนี้เราสามารถเพิ่มบล็อกโค้ดแบบมีรั้วกั้นให้กับเอกสารได้

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## ขั้นตอนที่ 5: สร้างสไตล์สำหรับโค้ด Fence ด้วยสตริงข้อมูล

บางครั้ง คุณอาจต้องการระบุภาษาการเขียนโปรแกรมหรือเพิ่มข้อมูลเพิ่มเติมให้กับบล็อกโค้ดของคุณ มาสร้างสไตล์สำหรับสิ่งนั้นกันดีกว่า

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## ขั้นตอนที่ 6: เพิ่มรหัส Fenced พร้อมสตริงข้อมูลลงในเอกสาร

ตอนนี้ เรามาเพิ่มบล็อกโค้ดที่ล้อมรั้วด้วยสตริงข้อมูลเพื่อระบุว่าเป็นโค้ด C#

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## บทสรุป

ยินดีด้วย! คุณเพิ่งเพิ่มบล็อกโค้ดแบบรั้วและโค้ดแบบรั้วพร้อมสตริงข้อมูลลงในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET นี่เป็นเพียงส่วนเล็กของภูเขาน้ำแข็ง ด้วย Aspose.Words คุณสามารถทำให้การประมวลผลเอกสารของคุณเป็นอัตโนมัติและปรับปรุงไปอีกขั้น สำรวจและเขียนโค้ดอย่างมีความสุข!

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร Word โดยทางโปรแกรมได้

### ฉันสามารถใช้ Aspose.Words กับภาษาการเขียนโปรแกรมอื่นได้หรือไม่
Aspose.Words รองรับภาษา .NET เป็นหลัก แต่มีเวอร์ชันสำหรับ Java, Python และภาษาอื่นๆ

### Aspose.Words ใช้งานได้ฟรีหรือไม่?
 Aspose.Words เป็นผลิตภัณฑ์เชิงพาณิชย์ แต่คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/)เพื่อสำรวจคุณลักษณะต่างๆ

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากชุมชน Aspose และนักพัฒนาได้[ที่นี่](https://forum.aspose.com/c/words/8).

### Aspose.Words มีคุณสมบัติอื่นใดอีกบ้าง?
Aspose.Words นำเสนอคุณสมบัติที่หลากหลาย รวมถึงการแปลงเอกสาร การสร้างเอกสารตามเทมเพลต การรายงาน และอื่นๆ อีกมากมาย
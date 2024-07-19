---
title: แทรกเขตข้อมูลผสานโดยใช้ DOM
linktitle: แทรกเขตข้อมูลผสานโดยใช้ DOM
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกและกำหนดค่าเขตข้อมูลผสานในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยบทช่วยสอนที่ครอบคลุมทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/net/working-with-fields/insert-merge-field-using-dom/
---

หากคุณกำลังทำงานกับการประมวลผลเอกสารใน .NET คุณอาจเจอกับ Aspose.Words ไลบรารีอันทรงพลังนี้นำเสนอฟีเจอร์มากมายสำหรับการจัดการเอกสาร Word โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะเน้นไปที่ฟีเจอร์เฉพาะอย่างหนึ่ง นั่นคือ การแทรกฟิลด์ผสานโดยใช้ Document Object Model (DOM) ใน Aspose.Words สำหรับ .NET คู่มือนี้จะแนะนำคุณในทุกขั้นตอน ตั้งแต่การตั้งค่าสภาพแวดล้อมของคุณไปจนถึงการแทรกและอัปเดตฟิลด์ผสานในเอกสาร Word

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่จำเป็นในการปฏิบัติตามพร้อมกับบทช่วยสอนนี้

1. **Basic Knowledge of C#:** คุณควรจะคุ้นเคยกับการเขียนโปรแกรม C#
2. **Visual Studio Installed:** ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio หรือ C# IDE อื่น ๆ บนเครื่องของคุณ
3. **Aspose.Words for .NET:** ดาวน์โหลดและติดตั้ง Aspose.Words สำหรับ .NET เวอร์ชันล่าสุดจาก[ข่าวประชาสัมพันธ์](https://releases.aspose.com/words/net/).
4. **Valid License:** หากคุณไม่มีใบอนุญาตคุณสามารถรับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผล

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ก่อนอื่น มาตั้งค่าโปรเจ็กต์ใหม่ใน Visual Studio กันก่อน

1. **Open Visual Studio.**
2. **Create a New Project:** ไปที่ ไฟล์ > ใหม่ > โครงการ เลือกแอปคอนโซล C#
3. **Name Your Project:** ตั้งชื่อโครงการของคุณให้มีความหมายแล้วคลิกสร้าง

## ขั้นตอนที่ 2: ติดตั้ง Aspose.Words

หากต้องการใช้ Aspose.Words คุณต้องเพิ่มลงในโปรเจ็กต์ของคุณ ซึ่งสามารถทำได้ผ่าน NuGet Package Manager

1. **Open NuGet Package Manager:** คลิกขวาที่โปรเจ็กต์ของคุณใน Solution Explorer จากนั้นเลือก จัดการแพ็คเกจ NuGet
2. **Search for Aspose.Words:** ใน NuGet Package Manager ให้ค้นหา "Aspose.Words"
3. **Install the Package:** คลิกติดตั้งเพื่อเพิ่ม Aspose.Words ให้กับโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 3: นำเข้าเนมสเปซ

หากต้องการเริ่มใช้ Aspose.Words คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

## ขั้นตอนที่ 4: เริ่มต้นเอกสารของคุณ

ตอนนี้ทุกอย่างได้รับการตั้งค่าแล้ว มาสร้างเอกสาร Word ใหม่และเริ่มต้น DocumentBuilder กัน

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// สร้างเอกสารและ DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 5: เลื่อนเคอร์เซอร์ไปที่ย่อหน้าเฉพาะ

ต่อไป เราต้องย้ายเคอร์เซอร์ไปยังย่อหน้าเฉพาะในเอกสารที่เราต้องการแทรกช่องผสาน

```csharp
Paragraph para = (Paragraph) doc.GetChild(NodeType.Paragraph, 0, true);
builder.MoveTo(para);
```

## ขั้นตอนที่ 6: แทรกฟิลด์ผสาน

 การแทรกเขตข้อมูลผสานนั้นตรงไปตรงมา เราจะใช้`InsertField` วิธีการของ`DocumentBuilder` ระดับ.

```csharp
// แทรกฟิลด์ผสานฟิลด์
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

## ขั้นตอนที่ 7: กำหนดค่าฟิลด์ผสาน

หลังจากแทรกฟิลด์ผสานแล้ว คุณสามารถตั้งค่าคุณสมบัติต่างๆ เพื่อกำหนดค่าได้ตามความต้องการของคุณ

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field.TextAfter = "Test3";
field.IsMapped = true;
field.IsVerticalFormatting = true;
```

## ขั้นตอนที่ 8: อัปเดตและบันทึกเอกสาร

สุดท้าย อัปเดตฟิลด์เพื่อให้แน่ใจว่ามีการใช้การตั้งค่าทั้งหมดและบันทึกเอกสาร

```csharp
// อัพเดทสนามครับ.
field.Update();

// บันทึกเอกสาร
doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

## บทสรุป

ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถแทรกและกำหนดค่าเขตข้อมูลผสานในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างง่ายดาย บทช่วยสอนนี้ครอบคลุมขั้นตอนสำคัญตั้งแต่การตั้งค่าสภาพแวดล้อมของคุณไปจนถึงการบันทึกเอกสารขั้นสุดท้าย ด้วย Aspose.Words คุณสามารถทำงานประมวลผลเอกสารที่ซับซ้อนได้โดยอัตโนมัติ ทำให้แอปพลิเคชัน .NET ของคุณมีประสิทธิภาพและประสิทธิผลมากขึ้น

## คำถามที่พบบ่อย

### 1. ฟิลด์ผสานคืออะไร?
ช่องผสานคือพื้นที่ที่สำรองไว้ในเอกสารที่สามารถแทนที่แบบไดนามิกด้วยข้อมูลจากแหล่งข้อมูล เช่น ฐานข้อมูลหรือไฟล์ CSV

### 2. ฉันสามารถใช้ Aspose.Words ได้ฟรีหรือไม่
 Aspose.Words ให้ทดลองใช้ฟรีซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/)- สำหรับการใช้งานระยะยาว คุณจะต้องซื้อใบอนุญาต

### 3. ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Words ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จากเว็บไซต์ Aspose[ที่นี่](https://purchase.aspose.com/temporary-license/).

### 4. Aspose.Words รองรับ .NET เวอร์ชันใดบ้าง
Aspose.Words รองรับ .NET หลายเวอร์ชัน รวมถึง .NET Framework, .NET Core และ .NET Standard

### 5. ฉันจะหาเอกสาร API สำหรับ Aspose.Words ได้ที่ไหน
 มีเอกสารประกอบ API[ที่นี่](https://reference.aspose.com/words/net/).
---
title: ขีดทับ
linktitle: ขีดทับ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้การจัดรูปแบบขีดทับกับข้อความโดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนของเรา พัฒนาทักษะการประมวลผลเอกสารของคุณ
type: docs
weight: 10
url: /th/net/working-with-markdown/strikethrough/
---
## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำโดยละเอียดเกี่ยวกับวิธีใช้การจัดรูปแบบขีดทับกับข้อความโดยใช้ Aspose.Words สำหรับ .NET หากคุณต้องการพัฒนาทักษะการประมวลผลเอกสารและเพิ่มความโดดเด่นให้กับข้อความของคุณ คุณมาถูกที่แล้ว มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

-  Aspose.Words สำหรับ .NET: ดาวน์โหลด[ที่นี่](https://releases.aspose.com/words/net/).
- .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนระบบของคุณ
- สภาพแวดล้อมการพัฒนา: IDE เช่น Visual Studio
- ความรู้พื้นฐานเกี่ยวกับ C#: จำเป็นต้องมีความคุ้นเคยกับการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็น สิ่งเหล่านี้จำเป็นสำหรับการเข้าถึงไลบรารี Aspose.Words และฟีเจอร์ต่างๆ

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: เริ่มต้น DocumentBuilder

 ที่`DocumentBuilder` class เป็นเครื่องมืออันทรงพลังใน Aspose.Words ที่ช่วยให้คุณสามารถเพิ่มเนื้อหาลงในเอกสารของคุณได้อย่างง่ายดาย

```csharp
// เริ่มต้น DocumentBuilder
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: ตั้งค่าคุณสมบัติขีดทับ

ตอนนี้ ลองใช้คุณสมบัติขีดทับกับข้อความของเรา สิ่งนี้เกี่ยวข้องกับการตั้งค่า`StrikeThrough` ทรัพย์สินของ`Font` คัดค้าน`true`.

```csharp
// ทำให้ข้อความขีดทับ
builder.Font.StrikeThrough = true;
```

## ขั้นตอนที่ 3: เขียนข้อความด้วยการขีดทับ

 ด้วยชุดคุณสมบัติขีดทับ ตอนนี้เราสามารถเพิ่มข้อความของเราได้แล้ว ที่`Writeln` method จะเพิ่มข้อความลงในเอกสาร

```csharp
// เขียนข้อความด้วยการขีดทับ
builder.Writeln("This text will be StrikeThrough");
```

## บทสรุป

และคุณก็ได้แล้ว! คุณได้เพิ่มการจัดรูปแบบขีดทับให้กับข้อความของคุณโดยใช้ Aspose.Words for .NET สำเร็จแล้ว ไลบรารีอันทรงพลังนี้เปิดโลกแห่งความเป็นไปได้สำหรับการประมวลผลและปรับแต่งเอกสาร ไม่ว่าคุณกำลังสร้างรายงาน จดหมาย หรือเอกสารประเภทอื่นๆ การใช้คุณสมบัติเหล่านี้อย่างเชี่ยวชาญจะช่วยเพิ่มผลผลิตและคุณภาพของผลลัพธ์ได้อย่างไม่ต้องสงสัย

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีการประมวลผลเอกสารที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงเอกสาร Word โดยทางโปรแกรมได้

### ฉันสามารถใช้ Aspose.Words สำหรับ .NET ในโครงการเชิงพาณิชย์ได้หรือไม่
 ได้ คุณสามารถใช้ Aspose.Words สำหรับ .NET ในโครงการเชิงพาณิชย์ได้ สำหรับตัวเลือกการซื้อโปรดไปที่[ซื้อหน้า](https://purchase.aspose.com/buy).

### มีการทดลองใช้ฟรีสำหรับ Aspose.Words สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words สำหรับ .NET ได้อย่างไร
คุณสามารถรับการสนับสนุนจากชุมชน Aspose และผู้เชี่ยวชาญเกี่ยวกับ[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/words/8).

### ฉันสามารถใช้ตัวเลือกการจัดรูปแบบข้อความอื่นโดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
อย่างแน่นอน! Aspose.Words สำหรับ .NET รองรับตัวเลือกการจัดรูปแบบข้อความที่หลากหลาย รวมถึงตัวหนา ตัวเอียง ขีดเส้นใต้ และอื่นๆ
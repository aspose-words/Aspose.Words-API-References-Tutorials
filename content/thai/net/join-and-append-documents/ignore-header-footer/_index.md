---
title: ละเว้นส่วนหัวส่วนท้าย
linktitle: ละเว้นส่วนหัวส่วนท้าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผสานเอกสาร Word โดยไม่สนใจส่วนหัวและส่วนท้ายโดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/net/join-and-append-documents/ignore-header-footer/
---
## การแนะนำ

การรวมเอกสาร Word บางครั้งอาจยุ่งยากเล็กน้อย โดยเฉพาะอย่างยิ่งเมื่อคุณต้องการเก็บบางส่วนให้เหมือนเดิมโดยไม่สนใจส่วนอื่นๆ เช่น ส่วนหัวและส่วนท้าย โชคดีที่ Aspose.Words สำหรับ .NET มอบวิธีที่ยอดเยี่ยมในการจัดการสิ่งนี้ ในบทช่วยสอนนี้ ฉันจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้แน่ใจว่าคุณจะเข้าใจทุกส่วน เราจะทำให้มันเบา สนทนาได้ และมีส่วนร่วม เช่นเดียวกับการพูดคุยกับเพื่อน พร้อม? มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าเรามีทุกสิ่งที่เราต้องการ:

-  Aspose.Words สำหรับ .NET: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/net/).
- Visual Studio: เวอร์ชันล่าสุดใด ๆ ควรใช้งานได้
- ความเข้าใจพื้นฐานของ C#: ไม่ต้องกังวล ฉันจะแนะนำโค้ดให้คุณทราบ
- เอกสาร Word สองฉบับ: เอกสารหนึ่งฉบับที่จะต่อท้ายเอกสารอีกฉบับหนึ่ง

## นำเข้าเนมสเปซ

ก่อนอื่น เราต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ C# ของเรา นี่เป็นสิ่งสำคัญเนื่องจากช่วยให้เราสามารถใช้คลาสและวิธีการของ Aspose.Words ได้โดยไม่ต้องอ้างอิงเนมสเปซแบบเต็มตลอดเวลา

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

### สร้างโครงการใหม่

เริ่มต้นด้วยการสร้างโครงการ Console App ใหม่ใน Visual Studio

1. เปิด Visual Studio
2. เลือก "สร้างโครงการใหม่"
3. เลือก "แอปคอนโซล (.NET Core)"
4. ตั้งชื่อโครงการของคุณแล้วคลิก "สร้าง"

### ติดตั้ง Aspose.Words สำหรับ .NET

ต่อไป เราต้องเพิ่ม Aspose.Words สำหรับ .NET ในโครงการของเรา คุณสามารถทำได้ผ่าน NuGet Package Manager:

1. คลิกขวาที่โครงการของคุณใน Solution Explorer
2. เลือก "จัดการแพ็คเกจ NuGet"
3. ค้นหา "Aspose.Words" และติดตั้ง

## ขั้นตอนที่ 2: โหลดเอกสารของคุณ

ตอนนี้โครงการของเราได้รับการตั้งค่าแล้ว มาโหลดเอกสาร Word ที่เราต้องการผสานกัน เพื่อประโยชน์ของบทช่วยสอนนี้ เราจะเรียกพวกเขาว่า "Document source.docx" และ "Northwind trader.docx"

ต่อไปนี้เป็นวิธีโหลดโดยใช้ Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

ข้อมูลโค้ดนี้จะกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณและโหลดเอกสารลงในหน่วยความจำ

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการนำเข้า

ก่อนที่จะรวมเอกสาร เราจำเป็นต้องตั้งค่าตัวเลือกการนำเข้าของเรา ขั้นตอนนี้มีความสำคัญเนื่องจากช่วยให้เราระบุได้ว่าเราต้องการละเว้นส่วนหัวและส่วนท้าย

นี่คือโค้ดสำหรับกำหนดค่าตัวเลือกการนำเข้า:

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = true };
```

 โดยการตั้งค่า`IgnoreHeaderFooter` ถึง`true`เรากำลังบอก Aspose.Words ให้ละเว้นส่วนหัวและส่วนท้ายในระหว่างกระบวนการผสาน

## ขั้นตอนที่ 4: รวมเอกสาร

เมื่อเอกสารของเราโหลดและกำหนดค่าตัวเลือกการนำเข้าแล้ว ก็ถึงเวลารวมเอกสาร

ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

บรรทัดโค้ดนี้จะผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางโดยยังคงรักษาการจัดรูปแบบต้นฉบับและไม่สนใจส่วนหัวและส่วนท้าย

## ขั้นตอนที่ 5: บันทึกเอกสารที่ผสาน

สุดท้ายเราจำเป็นต้องบันทึกเอกสารที่ผสาน 

นี่คือรหัสสำหรับบันทึกเอกสารที่ผสานของคุณ:

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

การดำเนินการนี้จะบันทึกเอกสารที่ผสานในไดเร็กทอรีที่ระบุด้วยชื่อไฟล์ "JoinAndAppendDocuments.IgnoreHeaderFooter.docx"

## บทสรุป

และคุณก็ได้แล้ว! คุณได้รวมเอกสาร Word สองเอกสารเข้าด้วยกันสำเร็จโดยไม่สนใจส่วนหัวและส่วนท้ายโดยใช้ Aspose.Words สำหรับ .NET วิธีการนี้มีประโยชน์สำหรับงานการจัดการเอกสารต่างๆ ซึ่งการดูแลส่วนเอกสารเฉพาะเป็นสิ่งสำคัญ

การทำงานร่วมกับ Aspose.Words สำหรับ .NET สามารถปรับปรุงเวิร์กโฟลว์การประมวลผลเอกสารของคุณได้อย่างมาก โปรดจำไว้ว่า หากคุณติดขัดหรือต้องการข้อมูลเพิ่มเติม คุณสามารถตรวจสอบได้ตลอดเวลา[เอกสารประกอบ](https://reference.aspose.com/words/net/).

## คำถามที่พบบ่อย

### ฉันสามารถเพิกเฉยต่อส่วนอื่นๆ ของเอกสารนอกเหนือจากส่วนหัวและส่วนท้ายได้หรือไม่

ใช่ Aspose.Words มีตัวเลือกมากมายในการปรับแต่งกระบวนการนำเข้า รวมถึงการละเว้นส่วนต่างๆ และการจัดรูปแบบ

### เป็นไปได้ไหมที่จะเก็บส่วนหัวและส่วนท้ายไว้แทนที่จะเพิกเฉย

 อย่างแน่นอน. เพียงตั้งค่า`IgnoreHeaderFooter` ถึง`false` ใน`ImportFormatOptions`.

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Words สำหรับ .NET หรือไม่

 ใช่ Aspose.Words สำหรับ .NET เป็นผลิตภัณฑ์เชิงพาณิชย์ คุณจะได้รับ[ทดลองใช้ฟรี](https://releases.aspose.com/) หรือซื้อใบอนุญาต[ที่นี่](https://purchase.aspose.com/buy).

### ฉันสามารถรวมเอกสารมากกว่าสองฉบับโดยใช้วิธีนี้ได้หรือไม่

 ใช่ คุณสามารถต่อท้ายเอกสารหลายชุดในวงเดียวได้โดยการทำซ้ำ`AppendDocument` วิธีการสำหรับเอกสารเพิ่มเติมแต่ละฉบับ

### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Words สำหรับ .NET ได้ที่ไหน

 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่[เว็บไซต์กำหนด](https://reference.aspose.com/words/net/).

---
title: เข้าร่วมอย่างต่อเนื่อง
linktitle: เข้าร่วมอย่างต่อเนื่อง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการรวมเอกสาร Word สองเอกสารได้อย่างราบรื่นโดยใช้ Aspose.Words สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการรวมเอกสารที่ราบรื่นและมีประสิทธิภาพ
type: docs
weight: 10
url: /th/net/join-and-append-documents/join-continuous/
---
## การแนะนำ

คุณกำลังมองหาการรวมเอกสาร Word สองเอกสารเป็นเอกสารเดียวได้อย่างราบรื่นโดยไม่มีการหยุดชะงักใช่หรือไม่? Aspose.Words สำหรับ .NET นำเสนอวิธีที่ยอดเยี่ยมในการบรรลุเป้าหมายนี้โดยใช้ฟีเจอร์ตัวแบ่งส่วนต่อเนื่อง บทช่วยสอนนี้จะแนะนำคุณทีละขั้นตอนตลอดกระบวนการ เพื่อให้มั่นใจว่าคุณสามารถรวมเอกสารได้อย่างง่ายดายโดยไม่ต้องยุ่งยาก มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:

-  Aspose.Words สำหรับ .NET: หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดและติดตั้ง[Aspose.Words สำหรับ .NET](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: คุณสามารถใช้ Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่น ๆ ได้
- เอกสารตัวอย่าง: เตรียมเอกสาร Word สองฉบับที่คุณต้องการผสาน

## นำเข้าเนมสเปซ

หากต้องการใช้ Aspose.Words สำหรับ .NET คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณ นี่คือวิธีการ:

```csharp
using Aspose.Words;
```

ตอนนี้ เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อความชัดเจน

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

ขั้นแรก เราต้องตั้งค่าไดเร็กทอรีสำหรับจัดเก็บเอกสารของคุณ นี่จะทำให้โค้ดของเราสามารถค้นหาไฟล์ที่เราต้องการรวมได้

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงในการจัดเก็บเอกสารของคุณ

## ขั้นตอนที่ 2: โหลดเอกสารต้นทางและปลายทาง

ต่อไปเราจะโหลดเอกสารต้นทางและปลายทางลงในโปรแกรมของเรา นี่คือเอกสารสองฉบับที่คุณต้องการผสาน

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

ตรวจสอบให้แน่ใจว่าชื่อไฟล์และเส้นทางตรงกับไฟล์จริงที่คุณต้องการใช้

## ขั้นตอนที่ 3: ตั้งค่าการเริ่มต้นส่วนเป็นแบบต่อเนื่อง

 เพื่อให้เนื้อหาของเอกสารต้นทางปรากฏขึ้นทันทีหลังจากเอกสารปลายทาง เราต้องตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`Continuous`.

```csharp
// ทำให้เอกสารปรากฏต่อจากเนื้อหาของเอกสารปลายทาง
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

เพื่อให้แน่ใจว่าไม่มีการหยุดพักระหว่างเอกสารเมื่อมีการรวมเข้าด้วยกัน

## ขั้นตอนที่ 4: ผนวกเอกสารต้นฉบับ

ตอนนี้เราผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง ขั้นตอนนี้ช่วยให้แน่ใจว่าเนื้อหาจากเอกสารต้นฉบับถูกเพิ่มที่ส่วนท้ายของเอกสารปลายทาง

```csharp
// ผนวกเอกสารต้นฉบับโดยใช้สไตล์ดั้งเดิมที่พบในเอกสารต้นฉบับ
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 โดยใช้`ImportFormatMode.KeepSourceFormatting` ตรวจสอบให้แน่ใจว่าการจัดรูปแบบจากเอกสารต้นฉบับจะยังคงอยู่ในเอกสารที่ผสานขั้นสุดท้าย

## ขั้นตอนที่ 5: บันทึกเอกสารที่ผสาน

สุดท้าย เราจะบันทึกเอกสารที่ผสานลงในไดเร็กทอรีที่ระบุ เป็นอันเสร็จสิ้นขั้นตอนการเข้าร่วมเอกสาร

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

ตรวจสอบให้แน่ใจว่าเส้นทางและชื่อไฟล์ถูกต้องตามความต้องการของคุณ

## บทสรุป

และคุณก็ได้แล้ว! ด้วยโค้ดเพียงไม่กี่บรรทัด คุณจะสามารถรวมเอกสาร Word สองฉบับเป็นเอกสารต่อเนื่องเดียวได้สำเร็จโดยใช้ Aspose.Words สำหรับ .NET กระบวนการนี้ไม่เพียงแต่เรียบง่าย แต่ยังมีประสิทธิภาพสูง เพื่อให้มั่นใจว่าเอกสารของคุณคงรูปแบบเดิมไว้

## คำถามที่พบบ่อย

### ฉันสามารถรวมเอกสารมากกว่าสองฉบับได้หรือไม่
ได้ คุณสามารถทำซ้ำขั้นตอนเพื่อรวมเอกสารหลายฉบับได้โดยการโหลดเอกสารเพิ่มเติมและผนวกเข้าด้วยกันตามลำดับ

### การจัดรูปแบบดั้งเดิมจะยังคงอยู่หรือไม่
 ใช่ ใช้`ImportFormatMode.KeepSourceFormatting` ช่วยให้มั่นใจได้ว่าการจัดรูปแบบจากเอกสารต้นฉบับจะยังคงอยู่

### Aspose.Words สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Words สำหรับ .NET เข้ากันได้กับทั้ง .NET Framework และ .NET Core

### ฉันสามารถรวมเอกสารที่มีการตั้งค่าหน้าต่างกันได้หรือไม่
ใช่ แต่คุณอาจต้องปรับคุณสมบัติการตั้งค่าหน้าเพื่อให้แน่ใจว่าจะผสานกันได้อย่างราบรื่น

### ฉันจะรับการสนับสนุนได้ที่ไหนหากฉันประสบปัญหา
 คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose[ที่นี่](https://forum.aspose.com/c/words/8).
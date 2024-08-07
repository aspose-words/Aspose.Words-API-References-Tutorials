---
title: สร้างบรรทัดลายเซ็นใหม่และตั้งค่ารหัสผู้ให้บริการ
linktitle: สร้างบรรทัดลายเซ็นใหม่และตั้งค่ารหัสผู้ให้บริการ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## การแนะนำ

สวัสดีผู้ชื่นชอบเทคโนโลยี! เคยสงสัยบ้างไหมว่าจะเพิ่มบรรทัดลายเซ็นในเอกสาร Word ของคุณโดยทางโปรแกรมได้อย่างไร? วันนี้เราจะมาเจาะลึกถึงการใช้ Aspose.Words สำหรับ .NET คู่มือนี้จะแนะนำคุณตลอดทุกขั้นตอน ทำให้ง่ายเหมือนการสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการในเอกสาร Word ของคุณ ไม่ว่าคุณจะทำให้การประมวลผลเอกสารเป็นอัตโนมัติหรือเพียงแค่ต้องการปรับปรุงขั้นตอนการทำงานของคุณ บทช่วยสอนนี้ก็ครอบคลุมทุกอย่าง

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเลอะมือ เรามาตรวจสอบให้แน่ใจก่อนว่าเรามีทุกสิ่งที่เราต้องการ:

1.  Aspose.Words สำหรับ .NET: หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลด[ที่นี่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ
3. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework แล้ว
4. ใบรับรอง PFX: สำหรับการลงนามในเอกสาร คุณจะต้องมีใบรับรอง PFX คุณสามารถรับได้จากผู้ออกใบรับรองที่เชื่อถือได้

## นำเข้าเนมสเปซ

ก่อนอื่น เรามานำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ C# ของคุณกันก่อน:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

เอาล่ะ มาลงลึกถึงเนื้อหาสำคัญกันดีกว่า ต่อไปนี้คือรายละเอียดของแต่ละขั้นตอนในการสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่

ในการเริ่มต้น เราต้องสร้างเอกสาร Word ใหม่ นี่จะเป็นผืนผ้าใบสำหรับบรรทัดลายเซ็นของเรา

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ในตัวอย่างนี้ เรากำลังเริ่มต้นใหม่`Document` และก`DocumentBuilder` - ที่`DocumentBuilder` ช่วยให้เราเพิ่มองค์ประกอบลงในเอกสารของเรา

## ขั้นตอนที่ 2: กำหนดตัวเลือกบรรทัดลายเซ็น

ต่อไป เราจะกำหนดตัวเลือกสำหรับบรรทัดลายเซ็นของเรา ซึ่งรวมถึงชื่อของผู้ลงนาม ตำแหน่ง อีเมล และรายละเอียดอื่นๆ

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

ตัวเลือกเหล่านี้ปรับแต่งบรรทัดลายเซ็น ทำให้ชัดเจนและเป็นมืออาชีพ

## ขั้นตอนที่ 3: แทรกบรรทัดลายเซ็น

ด้วยชุดตัวเลือกของเรา ตอนนี้เราสามารถแทรกบรรทัดลายเซ็นลงในเอกสารได้

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 นี่.`InsertSignatureLine` วิธีการเพิ่มบรรทัดลายเซ็นและเรากำหนด ID ผู้ให้บริการเฉพาะให้กับมัน

## ขั้นตอนที่ 4: บันทึกเอกสาร

หลังจากใส่บรรทัดลายเซ็นแล้ว มาบันทึกเอกสารกัน

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

วิธีนี้จะบันทึกเอกสารของคุณด้วยบรรทัดลายเซ็นที่เพิ่มใหม่

## ขั้นตอนที่ 5: ตั้งค่าตัวเลือกการลงชื่อ

ตอนนี้เราต้องตั้งค่าตัวเลือกสำหรับการลงนามในเอกสาร ซึ่งรวมถึง ID บรรทัดลายเซ็น ID ผู้ให้บริการ ความคิดเห็น และเวลาลงนาม

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

ตัวเลือกเหล่านี้ช่วยให้แน่ใจว่าเอกสารได้รับการลงนามด้วยรายละเอียดที่ถูกต้อง

## ขั้นตอนที่ 6: สร้างผู้ถือใบรับรอง

ในการลงนามในเอกสาร เราจะใช้ใบรับรอง PFX มาสร้างผู้ถือใบรับรองกันดีกว่า

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"morzal.pfx"` ด้วยไฟล์ใบรับรองจริงของคุณและ`"aw"` ด้วยรหัสผ่านใบรับรองของคุณ

## ขั้นตอนที่ 7: ลงนามในเอกสาร

สุดท้ายนี้ เราลงนามในเอกสารโดยใช้ยูทิลิตี้ลายเซ็นดิจิทัล

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

นี่เป็นการลงนามในเอกสารและบันทึกเป็นไฟล์ใหม่

## บทสรุป

และคุณก็ได้แล้ว! คุณสร้างบรรทัดลายเซ็นใหม่สำเร็จแล้วและตั้งค่า ID ผู้ให้บริการในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ไลบรารีอันทรงพลังนี้ทำให้การจัดการและทำให้งานการประมวลผลเอกสารเป็นอัตโนมัติเป็นเรื่องง่ายอย่างเหลือเชื่อ ลองใช้ดูเพื่อดูว่าจะปรับปรุงขั้นตอนการทำงานของคุณได้อย่างไร

## คำถามที่พบบ่อย

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของบรรทัดลายเซ็นได้หรือไม่
อย่างแน่นอน! คุณสามารถปรับแต่งตัวเลือกต่าง ๆ ได้ใน`SignatureLineOptions` เพื่อให้เหมาะกับความต้องการของคุณ

### จะเกิดอะไรขึ้นถ้าฉันไม่มีใบรับรอง PFX
คุณจะต้องขอใบรับรองจากผู้ออกใบรับรองที่เชื่อถือได้ จำเป็นสำหรับการเซ็นเอกสารแบบดิจิทัล

### ฉันสามารถเพิ่มบรรทัดลายเซ็นหลายบรรทัดลงในเอกสารได้หรือไม่
ได้ คุณสามารถเพิ่มบรรทัดลายเซ็นได้มากเท่าที่ต้องการโดยทำซ้ำขั้นตอนการแทรกด้วยตัวเลือกต่างๆ

### Aspose.Words สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ใช่ Aspose.Words สำหรับ .NET รองรับ .NET Core ทำให้มีความอเนกประสงค์สำหรับสภาพแวดล้อมการพัฒนาที่แตกต่างกัน

### ลายเซ็นดิจิทัลมีความปลอดภัยแค่ไหน?
ลายเซ็นดิจิทัลที่สร้างด้วย Aspose.Words มีความปลอดภัยสูง หากคุณใช้ใบรับรองที่ถูกต้องและเชื่อถือได้
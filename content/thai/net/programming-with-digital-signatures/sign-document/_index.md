---
title: ลงนามในเอกสาร Word
linktitle: ลงนามในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีลงนามในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนนี้ รักษาความปลอดภัยเอกสารของคุณได้อย่างง่ายดาย
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/sign-document/
---
## การแนะนำ

ในโลกดิจิทัลปัจจุบัน การรักษาความปลอดภัยให้กับเอกสารของคุณมีความสำคัญมากกว่าที่เคย ลายเซ็นดิจิทัลช่วยให้มั่นใจในความถูกต้องและความสมบูรณ์ของเอกสารของคุณ หากคุณต้องการลงนามในเอกสาร Word โดยทางโปรแกรมโดยใช้ Aspose.Words สำหรับ .NET แสดงว่าคุณมาถูกที่แล้ว คู่มือนี้จะแนะนำคุณตลอดกระบวนการทั้งหมดทีละขั้นตอนในลักษณะที่เรียบง่ายและน่าดึงดูด

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกโค้ด มีบางสิ่งที่คุณต้องเตรียม:

1.  Aspose.Words for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words for .NET เวอร์ชันล่าสุดแล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อม .NET: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET แล้ว (เช่น Visual Studio)
3. ใบรับรองดิจิทัล: รับใบรับรองดิจิทัล (เช่น ไฟล์ .pfx) สำหรับการลงนามในเอกสาร
4. เอกสารที่จะเซ็น: เตรียมเอกสาร Word ที่คุณต้องการเซ็นให้พร้อม

## นำเข้าเนมสเปซ

ก่อนอื่น คุณต้องนำเข้าเนมสเปซที่จำเป็นก่อน เพิ่มคำสั่งการใช้ต่อไปนี้ให้กับโครงการของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.Security.Cryptography.X509Certificates;
```

ตอนนี้ เรามาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้

## ขั้นตอนที่ 1: โหลดใบรับรองดิจิทัล

ขั้นตอนแรกคือการโหลดใบรับรองดิจิทัลจากไฟล์ ใบรับรองนี้จะใช้ในการลงนามในเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// โหลดใบรับรองดิจิทัล
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

### คำอธิบาย

- `dataDir`: นี่คือไดเร็กทอรีที่จัดเก็บใบรับรองและเอกสารของคุณ
- `CertificateHolder.Create` : วิธีการนี้จะโหลดใบรับรองจากเส้นทางที่ระบุ แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีของคุณและ`"morzal.pfx"` ด้วยชื่อไฟล์ใบรับรองของคุณ ที่`"aw"` คือรหัสผ่านสำหรับใบรับรอง

## ขั้นตอนที่ 2: โหลดเอกสาร Word

จากนั้นโหลดเอกสาร Word ที่คุณต้องการลงนาม

```csharp
// โหลดเอกสารที่จะลงนาม
Document doc = new Document(dataDir + "Digitally signed.docx");
```

### คำอธิบาย

- `Document` : คลาสนี้แสดงถึงเอกสาร Word แทนที่`"Digitally signed.docx"`พร้อมชื่อเอกสารของคุณ

## ขั้นตอนที่ 3: ลงนามในเอกสาร

 ตอนนี้ใช้`DigitalSignatureUtil.Sign` วิธีการลงนามในเอกสาร

```csharp
// ลงนามในเอกสาร
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx", certHolder);
```

### คำอธิบาย

- `DigitalSignatureUtil.Sign`: วิธีการนี้ลงนามในเอกสารโดยใช้ใบรับรองที่โหลด พารามิเตอร์แรกคือเส้นทางไปยังเอกสารต้นฉบับ พารามิเตอร์ที่สองคือเส้นทางไปยังเอกสารที่ลงนาม และพารามิเตอร์ที่สามคือผู้ถือใบรับรอง

## ขั้นตอนที่ 4: บันทึกเอกสารที่ลงนาม

สุดท้าย ให้บันทึกเอกสารที่ลงนามแล้วไปยังตำแหน่งที่ระบุ

```csharp
// บันทึกเอกสารที่ลงนามแล้ว
doc.Save(dataDir + "Document.Signed.docx");
```

### คำอธิบาย

- `doc.Save` : วิธีการนี้จะบันทึกเอกสารที่ลงนามแล้ว แทนที่`"Document.Signed.docx"` ด้วยชื่อที่ต้องการของเอกสารที่ลงนามของคุณ

## บทสรุป

และคุณก็ได้แล้ว! คุณได้ลงนามในเอกสาร Word เรียบร้อยแล้วโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถมั่นใจได้ว่าเอกสารของคุณได้รับการลงนามและรับรองความถูกต้องอย่างปลอดภัย โปรดจำไว้ว่า ลายเซ็นดิจิทัลเป็นเครื่องมือที่มีประสิทธิภาพในการปกป้องความสมบูรณ์ของเอกสารของคุณ ดังนั้นควรใช้ลายเซ็นดิจิทัลทุกครั้งที่จำเป็น

## คำถามที่พบบ่อย

### ลายเซ็นดิจิทัลคืออะไร?
ลายเซ็นดิจิทัลเป็นรูปแบบอิเล็กทรอนิกส์ของลายเซ็นที่สามารถใช้เพื่อตรวจสอบตัวตนของผู้ลงนามและรับรองว่าเอกสารจะไม่มีการเปลี่ยนแปลง

### เหตุใดฉันจึงต้องมีใบรับรองดิจิทัล
จำเป็นต้องมีใบรับรองดิจิทัลเพื่อสร้างลายเซ็นดิจิทัล ประกอบด้วยคีย์สาธารณะและข้อมูลระบุตัวตนของเจ้าของใบรับรอง ซึ่งให้วิธีการตรวจสอบลายเซ็น

### ฉันสามารถใช้ไฟล์ .pfx ในการเซ็นชื่อได้หรือไม่
ได้ ตราบใดที่ไฟล์ .pfx มีใบรับรองดิจิทัลที่ถูกต้อง และคุณมีรหัสผ่านในการเข้าถึง

### Aspose.Words สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 Aspose.Words สำหรับ .NET เป็นห้องสมุดเชิงพาณิชย์ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/) แต่คุณจะต้องซื้อใบอนุญาตจึงจะสามารถใช้งานได้เต็มรูปแบบ คุณสามารถซื้อได้[ที่นี่](https://purchase.aspose.com/buy).

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาเอกสารที่ครอบคลุม[ที่นี่](https://reference.aspose.com/words/net/) และการสนับสนุน[ที่นี่](https://forum.aspose.com/c/words/8).
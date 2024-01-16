---
title: ลงนามในเอกสาร Word
linktitle: ลงนามในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเซ็นชื่อในเอกสาร Word แบบดิจิทัลด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/sign-document/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการใช้คุณสมบัติการเซ็นเอกสารด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถลงนามในเอกสาร Word แบบดิจิทัลโดยใช้ใบรับรอง ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำลังโหลดใบรับรอง

เริ่มต้นด้วยการโหลดใบรับรองการลงนามโดยใช้คลาส CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังใบรับรองและรหัสผ่านที่เกี่ยวข้องของคุณ

## ขั้นตอนที่ 2: การลงนามในเอกสาร

ใช้คลาส DigitalSignatureUtil เพื่อลงนามในเอกสาร:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องสำหรับเอกสารต้นทางและเอกสารที่เซ็นชื่อ

### ตัวอย่างซอร์สโค้ดสำหรับการลงนามเอกสารโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการลงนามในเอกสารด้วย Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถลงนามในเอกสาร Word ด้วย Aspose.Words for .NET ได้อย่างง่ายดาย

## บทสรุป

 ในบทช่วยสอนนี้ เราได้สำรวจคุณสมบัติการลงนามเอกสารใน Aspose.Words สำหรับ .NET โดยการโหลดใบรับรองการลงนามและการใช้งาน`DigitalSignatureUtil.Sign` วิธีเราสามารถเซ็นชื่อในเอกสาร Word แบบดิจิทัลได้ การลงนามเอกสารให้การรับรองความถูกต้องและรับประกันความสมบูรณ์ของเนื้อหาของเอกสาร ทำให้เป็นคุณสมบัติที่มีคุณค่าสำหรับการจัดการเอกสารที่ปลอดภัยและเชื่อถือได้

### คำถามที่พบบ่อยสำหรับเอกสารคำลงนาม

#### ถาม: การลงนามเอกสารใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: การเซ็นเอกสารใน Aspose.Words สำหรับ .NET หมายถึงกระบวนการเซ็นเอกสาร Word แบบดิจิทัลโดยใช้ใบรับรอง คุณลักษณะนี้จะเพิ่มลายเซ็นดิจิทัลให้กับเอกสาร โดยให้ความถูกต้อง ความสมบูรณ์ และการไม่ปฏิเสธเนื้อหาของเอกสาร

#### ถาม: ฉันจะโหลดใบรับรองการลงนามใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการโหลดใบรับรองการลงนามใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`CertificateHolder` ระดับ. สร้างอินสแตนซ์ของ`CertificateHolder` โดยระบุเส้นทางไปยังไฟล์ใบรับรองและรหัสผ่านที่เกี่ยวข้อง นี่คือตัวอย่าง:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังใบรับรองของคุณและรหัสผ่านที่เกี่ยวข้อง

#### ถาม: ฉันจะลงนามในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการลงนามในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`DigitalSignatureUtil` ระดับ. โทรหา`Sign` วิธีการระบุเส้นทางไปยังเอกสารต้นฉบับ เส้นทางไปยังเอกสารที่ลงนาม (เอาต์พุต) และ`CertificateHolder` วัตถุ. นี่คือตัวอย่าง:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

ตรวจสอบให้แน่ใจว่าคุณได้ระบุเส้นทางที่ถูกต้องสำหรับเอกสารต้นทางและเอกสารที่ลงนาม (เอาต์พุต)

#### ถาม: จุดประสงค์ของการเซ็นเอกสารคืออะไร?

ตอบ: การลงนามเอกสารเป็นวิธีหนึ่งในการรับรองความถูกต้องและความสมบูรณ์ของเอกสาร ด้วยการลงนามในเอกสารแบบดิจิทัล คุณสามารถแสดงหลักฐานแหล่งที่มา ตรวจสอบว่าเนื้อหาในเอกสารไม่มีการเปลี่ยนแปลง และสร้างการไม่ปฏิเสธได้ การลงนามเอกสารมักใช้สำหรับเอกสารทางกฎหมาย การเงิน และเอกสารละเอียดอ่อน

#### ถาม: ฉันสามารถใช้ใบรับรองใดๆ สำหรับการลงนามเอกสารใน Aspose.Words สำหรับ .NET ได้หรือไม่

ตอบ: สำหรับการลงนามเอกสารใน Aspose.Words สำหรับ .NET คุณต้องใช้ใบรับรอง X.509 ที่ถูกต้อง สามารถรับใบรับรองนี้ได้จากผู้ออกใบรับรองที่เชื่อถือได้ (CA) หรือใบรับรองที่ลงนามด้วยตนเองสามารถใช้เพื่อการทดสอบได้

#### ถาม: Aspose.Words สำหรับ .NET รองรับการเซ็นเอกสารในรูปแบบไฟล์ใด

 ตอบ: Aspose.Words สำหรับ .NET รองรับการเซ็นเอกสารสำหรับเอกสาร Word ในรูปแบบไฟล์ DOCX คุณสามารถลงนามไฟล์ DOCX โดยใช้นามสกุลไฟล์`DigitalSignatureUtil` ชั้นเรียนและใบรับรองที่เหมาะสม

#### ถาม: ฉันสามารถลงนามในเอกสาร Word หลายฉบับโดยใช้ใบรับรองเดียวกันได้หรือไม่

ตอบ: ได้ คุณสามารถลงนามในเอกสาร Word หลายฉบับโดยใช้ใบรับรองเดียวกันได้ เมื่อคุณโหลดใบรับรองโดยใช้ไฟล์`CertificateHolder` คุณสามารถนำมาใช้ซ้ำเพื่อลงนามในเอกสารหลายฉบับได้โดยการเรียก`DigitalSignatureUtil.Sign` วิธีการที่มีแหล่งที่แตกต่างกันและเส้นทางเอกสารที่ลงนาม

#### ถาม: การเซ็นเอกสารแก้ไขเอกสารต้นฉบับหรือไม่

ตอบ: การลงนามเอกสารด้วย Aspose.Words สำหรับ .NET ไม่ได้แก้ไขเอกสารต้นฉบับ แต่จะสร้างสำเนาของเอกสารที่เซ็นชื่อแบบดิจิทัลแทน โดยปล่อยให้เอกสารต้นฉบับไม่เสียหาย สำเนาที่ลงนามแบบดิจิทัลจะมีลายเซ็นดิจิทัลเพิ่มเติม เพื่อให้มั่นใจถึงความสมบูรณ์ของเนื้อหาของเอกสาร

#### ถาม: ฉันสามารถตรวจสอบลายเซ็นดิจิทัลของเอกสารที่ลงนามโดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ใช่ Aspose.Words สำหรับ .NET มีฟังก์ชันในการตรวจสอบลายเซ็นดิจิทัลของเอกสารที่ลงนาม คุณสามารถใช้`DigitalSignatureUtil.Verify` วิธีการตรวจสอบความถูกต้องและความถูกต้องของลายเซ็นดิจิทัล
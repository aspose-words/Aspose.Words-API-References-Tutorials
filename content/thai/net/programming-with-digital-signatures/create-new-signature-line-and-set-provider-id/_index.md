---
title: สร้างบรรทัดลายเซ็นใหม่และตั้งค่ารหัสผู้ให้บริการ
linktitle: สร้างบรรทัดลายเซ็นใหม่และตั้งค่ารหัสผู้ให้บริการ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการใช้ฟีเจอร์สร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถแทรกบรรทัดลายเซ็นในเอกสาร Word ตั้งค่าตัวเลือกแบบกำหนดเอง และลงนามในเอกสาร ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: การสร้างเอกสารและเครื่องมือสร้าง

เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาส Document และอ็อบเจ็กต์ DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การตั้งค่าตัวเลือกบรรทัดลายเซ็น

สร้างอินสแตนซ์ของคลาส SignatureLineOptions และตั้งค่าตัวเลือกที่ต้องการ:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## ขั้นตอนที่ 3: การแทรกบรรทัดลายเซ็น

ใช้เมธอด InsertSignatureLine() ของอ็อบเจ็กต์ DocumentBuilder เพื่อแทรกบรรทัดลายเซ็นลงในเอกสาร:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## ขั้นตอนที่ 4: ตั้งค่า ID ผู้ให้บริการ

ตั้งค่า ID ผู้ให้บริการสำหรับบรรทัดลายเซ็นโดยใช้คุณสมบัติ ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

อย่าลืมระบุรหัสผู้ให้บริการที่ถูกต้องสำหรับกรณีการใช้งานของคุณ

## ขั้นตอนที่ 5: บันทึกเอกสาร

บันทึกเอกสารที่แก้ไข:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกเอกสาร

## ขั้นตอนที่ 6: การลงนามในเอกสาร

ในการลงนามในเอกสาร คุณต้องตั้งค่าตัวเลือกลายเซ็นและใช้คลาส DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องสำหรับเอกสาร ใบรับรอง และเอกสารที่ลงนาม

### ตัวอย่างซอร์สโค้ดสำหรับสร้างบรรทัดลายเซ็นใหม่และตั้งค่ารหัสผู้ให้บริการโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์เพื่อสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการด้วย Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

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

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการในเอกสาร Word ของคุณด้วย Aspose.Words for .NET ได้อย่างง่ายดาย

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจคุณลักษณะของการสร้างบรรทัดลายเซ็นใหม่และการตั้งค่า ID ผู้ให้บริการในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถแทรกบรรทัดลายเซ็นพร้อมตัวเลือกแบบกำหนดเอง และเชื่อมโยงกับผู้ให้บริการเฉพาะโดยใช้รหัสผู้ให้บริการได้อย่างง่ายดาย การเพิ่มบรรทัดลายเซ็นและการปรับแต่งผู้ให้บริการข้อมูลจะช่วยเพิ่มความถูกต้องและความน่าเชื่อถือของเอกสารของคุณ Aspose.Words สำหรับ .NET มอบ API ที่มีประสิทธิภาพสำหรับการประมวลผลคำพร้อมบรรทัดลายเซ็นและใบรับรองดิจิทัลในเอกสาร Word ช่วยให้คุณสามารถทำให้กระบวนการลงนามเป็นอัตโนมัติและรับประกันความถูกต้องของเอกสารของคุณ

### คำถามที่พบบ่อย

#### ถาม: ID ผู้ให้บริการในบรรทัดลายเซ็นคืออะไร

ตอบ: ID ผู้ให้บริการในบรรทัดลายเซ็นคือตัวระบุเฉพาะที่แสดงถึงผู้ให้บริการลายเซ็นดิจิทัล ช่วยระบุแหล่งที่มาหรือองค์กรที่รับผิดชอบลายเซ็น

#### ถาม: ฉันจะสร้างบรรทัดลายเซ็นใหม่ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการสร้างบรรทัดลายเซ็นใหม่ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  สร้างอินสแตนซ์ของ`Document` คลาสและก`DocumentBuilder` วัตถุ วัตถุ
2.  สร้างอินสแตนซ์ของ`SignatureLineOptions` และตั้งค่าตัวเลือกบรรทัดลายเซ็นที่ต้องการ
3.  ใช้`InsertSignatureLine` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกบรรทัดลายเซ็นลงในเอกสาร

#### ถาม: ฉันสามารถปรับแต่งตัวเลือกของบรรทัดลายเซ็น เช่น ชื่อผู้ลงนาม ตำแหน่ง และคำแนะนำได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งตัวเลือกของบรรทัดลายเซ็นได้ ที่`SignatureLineOptions` class จัดเตรียมคุณสมบัติเพื่อตั้งค่าตัวเลือกที่ต้องการ เช่น`Signer`, `SignerTitle`, `Instructions`, `AllowComments`ฯลฯ คุณสามารถแก้ไขคุณสมบัติเหล่านี้ได้ก่อนที่จะแทรกบรรทัดลายเซ็น

#### ถาม: จุดประสงค์ของการตั้งค่า ID ผู้ให้บริการสำหรับบรรทัดลายเซ็นคืออะไร

ตอบ: การตั้งค่า ID ผู้ให้บริการสำหรับบรรทัดลายเซ็นจะช่วยระบุแหล่งที่มาหรือองค์กรที่รับผิดชอบลายเซ็นดิจิทัล ช่วยให้คุณสามารถเชื่อมโยงลายเซ็นกับผู้ให้บริการหรือหน่วยงานเฉพาะ โดยให้ข้อมูลเพิ่มเติมเกี่ยวกับที่มาและความน่าเชื่อถือของลายเซ็น

#### ถาม: ฉันจะตั้งค่า ID ผู้ให้บริการสำหรับบรรทัดลายเซ็นโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการตั้งค่า ID ผู้ให้บริการสำหรับบรรทัดลายเซ็นโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  หลังจากแทรกบรรทัดลายเซ็นแล้ว ให้เข้าถึง`ProviderId` ทรัพย์สินของ`SignatureLine` วัตถุ วัตถุ
2.  ตั้ง`ProviderId` คุณสมบัติเป็นค่า ID ผู้ให้บริการที่ต้องการโดยใช้`Guid` ประเภทข้อมูล.

#### ถาม: ฉันสามารถลงนามในเอกสารหลังจากสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการได้หรือไม่

 ตอบ: ได้ หลังจากสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการแล้ว คุณสามารถลงนามในเอกสารได้ ในการลงนามในเอกสาร คุณต้องตั้งค่าตัวเลือกลายเซ็น รวมถึง ID บรรทัดลายเซ็น ID ผู้ให้บริการ ความคิดเห็น และเวลาลงนาม จากนั้นใช้`DigitalSignatureUtil.Sign` วิธีการลงนามเอกสารโดยใช้ใบรับรองดิจิทัล

#### ถาม: ฉันสามารถระบุ ID ผู้ให้บริการเฉพาะสำหรับแต่ละบรรทัดลายเซ็นในเอกสาร Word ได้หรือไม่

ตอบ: ได้ คุณสามารถระบุ ID ผู้ให้บริการเฉพาะสำหรับแต่ละบรรทัดลายเซ็นในเอกสาร Word ได้ หลังจากแทรกบรรทัดลายเซ็นแต่ละบรรทัดแล้ว คุณสามารถตั้งค่า ID ผู้ให้บริการสำหรับบรรทัดลายเซ็นนั้นๆ ได้โดยเข้าไปที่`ProviderId` ทรัพย์สินของบุคคลนั้น ๆ`SignatureLine` วัตถุ วัตถุ

#### ถาม: ฉันจะบันทึกเอกสารที่แก้ไขได้อย่างไรหลังจากสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการแล้ว

 ตอบ: หากต้องการบันทึกเอกสารที่แก้ไขหลังจากสร้างบรรทัดลายเซ็นใหม่และตั้งค่า ID ผู้ให้บริการ คุณสามารถใช้`Save` วิธีการของ`Document` วัตถุ วัตถุ ระบุเส้นทางและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกเอกสาร

#### ถาม: Aspose.Words สำหรับ .NET รองรับการสร้างและลงนามบรรทัดลายเซ็นในรูปแบบไฟล์ใด

ตอบ: Aspose.Words สำหรับ .NET รองรับการสร้างและการลงนามบรรทัดลายเซ็นในรูปแบบไฟล์ DOCX คุณสามารถสร้างและลงนามบรรทัดลายเซ็นในไฟล์ DOCX โดยใช้วิธีการและคลาสที่ให้มา

#### ถาม: ฉันสามารถแก้ไข ID ผู้ให้บริการหรือตัวเลือกอื่น ๆ ของบรรทัดลายเซ็นหลังจากลงนามแล้วได้หรือไม่

ตอบ: เมื่อลงนามบรรทัดลายเซ็นแล้ว บรรทัดดังกล่าวจะเป็นส่วนหนึ่งของเนื้อหาของเอกสารและไม่สามารถแก้ไขได้แยกกัน การแก้ไขบรรทัดลายเซ็นใดๆ เช่น การเปลี่ยน ID ผู้ให้บริการหรือตัวเลือกอื่นๆ จะต้องลบลายเซ็นที่มีอยู่ออกและสร้างบรรทัดลายเซ็นใหม่
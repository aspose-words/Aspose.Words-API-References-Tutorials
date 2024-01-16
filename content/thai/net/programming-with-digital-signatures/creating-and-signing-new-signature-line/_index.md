---
title: การสร้างและการลงนามบรรทัดลายเซ็นใหม่
linktitle: การสร้างและการลงนามบรรทัดลายเซ็นใหม่
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างและลงนามบรรทัดลายเซ็นใหม่ในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการใช้ฟีเจอร์สร้างและลงนามบรรทัดลายเซ็นใหม่ด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถแทรกบรรทัดลายเซ็นในเอกสาร Word ตั้งค่าตัวเลือกแบบกำหนดเอง และลงนามในเอกสาร ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: การสร้างเอกสารและเครื่องมือสร้าง

เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาส Document และอ็อบเจ็กต์ DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การแทรกบรรทัดลายเซ็น

ใช้เมธอด InsertSignatureLine() ของอ็อบเจ็กต์ DocumentBuilder เพื่อแทรกบรรทัดลายเซ็นใหม่ลงในเอกสาร:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

บันทึกเอกสารที่แก้ไข:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้องเพื่อบันทึกเอกสาร

## ขั้นตอนที่ 4: การลงนามในเอกสาร

ในการลงนามในเอกสาร คุณต้องตั้งค่าตัวเลือกลายเซ็นและใช้คลาส DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องสำหรับเอกสาร รูปภาพบรรทัดลายเซ็น และเอกสารที่เซ็นชื่อ

### ตัวอย่างซอร์สโค้ดสำหรับการสร้างและการลงนามบรรทัดลายเซ็นใหม่โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์เพื่อสร้างและลงนามในบรรทัดลายเซ็นใหม่ด้วย Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างและลงนามในบรรทัดลายเซ็นใหม่ในเอกสาร Word ของคุณด้วย Aspose.Words for .NET ได้อย่างง่ายดาย

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างและลงนามบรรทัดลายเซ็นใหม่ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถแทรกบรรทัดลายเซ็นลงในเอกสารของคุณ ปรับแต่งตัวเลือก และลงนามในเอกสารโดยใช้ใบรับรองดิจิทัลได้อย่างง่ายดาย การเพิ่มบรรทัดลายเซ็นและลายเซ็นดิจิทัลลงในเอกสารของคุณช่วยเพิ่มความถูกต้องและความสมบูรณ์ ทำให้เอกสารมีความปลอดภัยและเชื่อถือได้มากขึ้น Aspose.Words สำหรับ .NET มอบ API ที่ทรงพลังสำหรับการประมวลผลคำพร้อมลายเซ็นและใบรับรองดิจิทัลในเอกสาร Word ช่วยให้คุณสามารถทำให้กระบวนการลงนามเป็นอัตโนมัติและรับประกันความถูกต้องของเอกสารของคุณ

### คำถามที่พบบ่อย

#### ถาม: บรรทัดลายเซ็นในเอกสาร Word คืออะไร

ตอบ: บรรทัดลายเซ็นในเอกสาร Word คือพื้นที่ที่สำรองไว้ซึ่งระบุว่าควรวางลายเซ็นไว้ที่ใด โดยทั่วไปจะประกอบด้วยชื่อ ชื่อเรื่อง และวันที่ และมีพื้นที่สำหรับลายเซ็นที่เขียนด้วยลายมือหรือดิจิทัล

#### ถาม: ฉันจะสร้างบรรทัดลายเซ็นในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการสร้างบรรทัดลายเซ็นในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  สร้างอินสแตนซ์ของ`Document` คลาสและก`DocumentBuilder` วัตถุ.
2.  ใช้`InsertSignatureLine` วิธีการของ`DocumentBuilder` วัตถุเพื่อแทรกบรรทัดลายเซ็นใหม่ลงในเอกสาร
3. บันทึกเอกสารที่แก้ไข

#### ถาม: ฉันสามารถปรับแต่งตัวเลือกบรรทัดลายเซ็น เช่น ชื่อ ชื่อ และวันที่ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งตัวเลือกบรรทัดลายเซ็นได้ ที่`SignatureLineOptions` class จัดเตรียมคุณสมบัติเพื่อตั้งค่าตัวเลือกที่ต้องการ เช่น`Signer`, `SignerTitle`, `ShowDate`ฯลฯ คุณสามารถแก้ไขคุณสมบัติเหล่านี้ได้ก่อนที่จะแทรกบรรทัดลายเซ็น

#### ถาม: ฉันจะลงนามในเอกสารหลังจากสร้างบรรทัดลายเซ็นได้อย่างไร

 ตอบ: หากต้องการลงนามในเอกสารหลังจากสร้างบรรทัดลายเซ็น คุณต้องตั้งค่าตัวเลือกลายเซ็นและใช้`DigitalSignatureUtil` ระดับ. นี่คือขั้นตอน:
1.  ตั้ง`SignatureLineId` ทรัพย์สินใน`SignOptions` คัดค้าน ID ของบรรทัดลายเซ็น
2.  ตั้ง`SignatureLineImage` ทรัพย์สินใน`SignOptions` คัดค้านรูปภาพของลายเซ็นที่คุณต้องการใช้
3.  โหลดใบรับรองการลงนามโดยใช้ไฟล์`CertificateHolder` ระดับ.
4.  ใช้`DigitalSignatureUtil.Sign` วิธีการลงนามในเอกสารโดยระบุพารามิเตอร์ที่จำเป็น

#### ถาม: ฉันสามารถใช้รูปภาพลายเซ็นดิจิทัลเพื่อลงนามในเอกสารได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้รูปภาพลายเซ็นดิจิทัลเพื่อลงนามในเอกสารได้ ในการดำเนินการนี้ คุณจะต้องจัดเตรียมไฟล์รูปภาพในรูปแบบ`SignOptions` วัตถุโดยใช้`SignatureLineImage`คุณสมบัติ. รูปภาพสามารถอยู่ในรูปแบบรูปภาพที่รองรับ เช่น JPEG, PNG หรือ EMF

#### ถาม: จุดประสงค์ของการสร้างและลงนามบรรทัดลายเซ็นใหม่ในเอกสาร Word คืออะไร

ตอบ: การสร้างและการลงนามบรรทัดลายเซ็นใหม่ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถเพิ่มพื้นที่ที่สำรองไว้สำหรับลายเซ็น จากนั้นลงนามในเอกสารโดยใช้ใบรับรองดิจิทัล กระบวนการนี้รับประกันความถูกต้องและความสมบูรณ์ของเอกสาร โดยจัดเตรียมหลักฐานการอนุมัติหรือข้อตกลง

#### ถาม: ฉันสามารถสร้างและเซ็นลายเซ็นหลายบรรทัดในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้หรือไม่

ตอบ: ได้ คุณสามารถสร้างและลงนามหลายบรรทัดลายเซ็นในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET แต่ละบรรทัดลายเซ็นสามารถมี ID และตัวเลือกเฉพาะของตัวเองได้ คุณสามารถทำซ้ำขั้นตอนเพื่อสร้างและลงนามบรรทัดลายเซ็นเพิ่มเติมในเอกสารได้

#### ถาม: ฉันสามารถแก้ไขบรรทัดลายเซ็นหรือเพิ่มข้อมูลเพิ่มเติมหลังจากลงนามแล้วได้หรือไม่

ตอบ: เมื่อลงนามบรรทัดลายเซ็นแล้ว บรรทัดดังกล่าวจะเป็นส่วนหนึ่งของเนื้อหาของเอกสารและไม่สามารถแก้ไขได้แยกกัน อย่างไรก็ตาม คุณสามารถเพิ่มข้อมูลหรือเนื้อหาเพิ่มเติมหลังบรรทัดลายเซ็นที่ลงนามได้

#### ถาม: ฉันสามารถตรวจสอบลายเซ็นดิจิทัลของเอกสารที่มีบรรทัดลายเซ็นได้หรือไม่

 ตอบ: ใช่ Aspose.Words สำหรับ .NET มีฟังก์ชันในการตรวจสอบลายเซ็นดิจิทัลของเอกสารที่มีบรรทัดลายเซ็น คุณสามารถใช้`DigitalSignatureUtil.Verify` วิธีการตรวจสอบความถูกต้องและความถูกต้องของลายเซ็นดิจิทัล

#### ถาม: Aspose.Words สำหรับ .NET รองรับการสร้างและลงนามบรรทัดลายเซ็นในรูปแบบไฟล์ใด

ตอบ: Aspose.Words สำหรับ .NET รองรับการสร้างและการลงนามบรรทัดลายเซ็นในรูปแบบไฟล์ DOCX คุณสามารถสร้างและลงนามบรรทัดลายเซ็นในไฟล์ DOCX โดยใช้วิธีการและคลาสที่ให้มา
---
title: การลงนามบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word
linktitle: การลงนามบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีลงนามบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/signing-existing-signature-line/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการใช้คุณลักษณะลายเซ็นของบรรทัดลายเซ็นที่มีอยู่กับ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเซ็นชื่อแบบดิจิทัลในบรรทัดลายเซ็นที่มีอยู่แล้วในเอกสาร Word ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำลังโหลดเอกสารและเข้าถึงบรรทัดลายเซ็น

เริ่มต้นด้วยการอัปโหลดเอกสารที่มีบรรทัดลายเซ็นที่มีอยู่:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## ขั้นตอนที่ 2: การตั้งค่าตัวเลือกลายเซ็น

สร้างอินสแตนซ์ของคลาส SignOptions และตั้งค่าตัวเลือกลายเซ็น รวมถึง ID บรรทัดลายเซ็นและรูปภาพบรรทัดลายเซ็น:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังรูปภาพบรรทัดลายเซ็น

## ขั้นตอนที่ 3: กำลังโหลดใบรับรอง

เริ่มต้นด้วยการโหลดใบรับรองการลงนามโดยใช้คลาส CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังใบรับรองและรหัสผ่านที่เกี่ยวข้องของคุณ

## ขั้นตอนที่ 4: การลงนามในบรรทัดลายเซ็นที่มีอยู่

ใช้คลาส DigitalSignatureUtil เพื่อลงนามในบรรทัดลายเซ็นที่มีอยู่:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องสำหรับเอกสารต้นทาง เอกสารที่ลงนาม และใบรับรอง

### ตัวอย่างซอร์สโค้ดสำหรับการลงนามบรรทัดลายเซ็นที่มีอยู่โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์เพื่อลงนามในบรรทัดลายเซ็นที่มีอยู่ด้วย Aspose.Words สำหรับ .NET:


```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถเซ็นชื่อบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word ด้วย Aspose.Words for .NET ได้อย่างง่ายดาย

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีลงนามในบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถโหลดเอกสาร เข้าถึงบรรทัดลายเซ็นที่มีอยู่ ตั้งค่าตัวเลือกการลงนาม และลงนามในเอกสารได้อย่างง่ายดาย ความสามารถในการลงนามบรรทัดลายเซ็นที่มีอยู่เป็นวิธีที่สะดวกในการเพิ่มลายเซ็นดิจิทัลลงในพื้นที่ที่กำหนดไว้ล่วงหน้าในเอกสาร Word ของคุณ ช่วยให้มั่นใจในความสมบูรณ์ของเอกสารและการรับรองความถูกต้อง Aspose.Words สำหรับ .NET นำเสนอ API ที่มีประสิทธิภาพสำหรับการประมวลผลคำพร้อมลายเซ็นดิจิทัล ช่วยให้คุณปรับแต่งกระบวนการลงนามและเพิ่มความปลอดภัยของเอกสาร Word ของคุณได้

### คำถามที่พบบ่อย

#### ถาม: บรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word คืออะไร

ตอบ: บรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word เป็นพื้นที่ที่กำหนดไว้ล่วงหน้าซึ่งสามารถวางลายเซ็นได้ โดยทั่วไปจะแสดงด้วยรูปร่างหรือวัตถุในเอกสาร และทำหน้าที่เป็นพื้นที่ที่กำหนดสำหรับผู้ลงนามในการเพิ่มลายเซ็นดิจิทัลของตน

#### ถาม: ฉันจะลงนามบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

ตอบ: หากต้องการลงนามบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  โหลดเอกสารโดยใช้`Document` และระบุเส้นทางไปยังไฟล์เอกสาร
2.  เข้าถึงบรรทัดลายเซ็นที่มีอยู่โดยใช้วิธีการหรือคุณสมบัติที่เหมาะสม ตัวอย่างเช่นคุณสามารถใช้`GetChild` วิธีการดึงรูปร่างเส้นลายเซ็น
3.  สร้างอินสแตนซ์ของ`SignOptions` คลาสและตั้งค่า`SignatureLineId` คุณสมบัติเป็น ID ของบรรทัดลายเซ็นที่มีอยู่
4.  ตั้ง`SignatureLineImage` ทรัพย์สินของ`SignOptions` คลาสให้กับรูปภาพที่แสดงลายเซ็นดิจิทัล
5.  โหลดใบรับรองการลงนามโดยใช้ไฟล์`CertificateHolder` และจัดเตรียมใบรับรองและรหัสผ่านที่จำเป็น
6.  ใช้`DigitalSignatureUtil.Sign` วิธีการลงนามในเอกสาร โดยระบุพารามิเตอร์ที่จำเป็นรวมถึง`SignOptions` วัตถุ.

#### ถาม: ฉันจะเข้าถึงบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

 ตอบ: ในการเข้าถึงบรรทัดลายเซ็นที่มีอยู่ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้วิธีการหรือคุณสมบัติที่เหมาะสมเพื่อดึงรูปร่างเส้นลายเซ็นจากโครงสร้างของเอกสารได้ ตัวอย่างเช่น คุณสามารถใช้`GetChild` วิธีการที่มีพารามิเตอร์ที่เหมาะสมเพื่อให้ได้รูปร่างเส้นลายเซ็นที่ต้องการ

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลในบรรทัดลายเซ็นที่มีอยู่ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของลายเซ็นดิจิทัลในบรรทัดลายเซ็นที่มีอยู่ได้โดยการจัดเตรียมไฟล์รูปภาพที่แสดงถึงลายเซ็น รูปภาพอาจเป็นโลโก้ ลายเซ็นที่เขียนด้วยลายมือ หรือการแสดงลายเซ็นแบบกราฟิกอื่นๆ คุณสามารถตั้งค่า`SignatureLineImage` ทรัพย์สินของ`SignOptions` คลาสเป็นไบต์ของไฟล์รูปภาพ

#### ถาม: ฉันสามารถลงนามบรรทัดลายเซ็นที่มีอยู่หลายบรรทัดในเอกสาร Word ได้หรือไม่
 ตอบ: ได้ คุณสามารถลงนามบรรทัดลายเซ็นที่มีอยู่หลายบรรทัดในเอกสาร Word ได้ คุณต้องทำตามขั้นตอนสำหรับบรรทัดลายเซ็นแต่ละบรรทัดแยกกัน โดยตั้งค่าให้เหมาะสม`SignatureLineId` และ`SignatureLineImage` ค่าใน`SignOptions` วัตถุสำหรับแต่ละบรรทัดลายเซ็น

#### ถาม: ไฟล์รูปภาพควรเป็นรูปแบบใดสำหรับลายเซ็นดิจิทัลในบรรทัดลายเซ็นที่มีอยู่

 ตอบ: ไฟล์รูปภาพสำหรับลายเซ็นดิจิทัลในบรรทัดลายเซ็นที่มีอยู่สามารถมีได้หลายรูปแบบ เช่น PNG, JPEG, BMP หรือ GIF คุณสามารถระบุเส้นทางของไฟล์หรืออ่านไบต์ของไฟล์รูปภาพและกำหนดให้กับ`SignatureLineImage` ทรัพย์สินของ`SignOptions` ระดับ.
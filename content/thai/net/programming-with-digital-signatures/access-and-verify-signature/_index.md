---
title: เข้าถึงและตรวจสอบลายเซ็นในเอกสาร Word
linktitle: เข้าถึงและตรวจสอบลายเซ็นในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการเข้าถึงและตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-digital-signatures/access-and-verify-signature/
---
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการใช้คุณสมบัติการเข้าถึงและการตรวจสอบลายเซ็นของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณเข้าถึงลายเซ็นดิจิทัลในเอกสาร Word และตรวจสอบความถูกต้องได้ ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำลังโหลดเอกสารและเข้าถึงลายเซ็น

เริ่มต้นด้วยการอัปโหลดเอกสารที่มีลายเซ็นดิจิทัล:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## ขั้นตอนที่ 2: เรียกดูลายเซ็นดิจิทัล

ใช้การวนซ้ำเพื่อวนซ้ำลายเซ็นดิจิทัลทั้งหมดในเอกสาร:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// เข้าถึงข้อมูลลายเซ็น
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// คุณสมบัตินี้มีอยู่ในเอกสาร MS Word เท่านั้น
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

อย่าลืมปรับแต่งข้อความที่แสดงตามความต้องการของคุณ

### ตัวอย่างซอร์สโค้ดสำหรับการเข้าถึงและตรวจสอบลายเซ็นโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการเข้าถึงและการตรวจสอบลายเซ็นโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
	
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// คุณสมบัตินี้มีอยู่ในเอกสาร MS Word เท่านั้น
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเข้าถึงและตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word ของคุณได้อย่างง่ายดายด้วย Aspose.Words for .NET

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจคุณลักษณะของการเข้าถึงและการตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถโหลดเอกสาร เข้าถึงลายเซ็นดิจิทัล และตรวจสอบความถูกต้องได้อย่างง่ายดาย ความสามารถในการเข้าถึงและตรวจสอบลายเซ็นดิจิทัลช่วยให้มั่นใจในความสมบูรณ์และความถูกต้องของเอกสาร Word ของคุณ Aspose.Words สำหรับ .NET นำเสนอ API ที่มีประสิทธิภาพสำหรับการประมวลผลคำพร้อมลายเซ็นดิจิทัล ช่วยให้คุณสามารถทำให้กระบวนการตรวจสอบเป็นอัตโนมัติและเพิ่มความปลอดภัยของเอกสารของคุณ

### คำถามที่พบบ่อย

#### ถาม: ลายเซ็นดิจิทัลในเอกสาร Word คืออะไร

ตอบ: ลายเซ็นดิจิทัลในเอกสาร Word คือลายเซ็นอิเล็กทรอนิกส์ที่ให้วิธีการตรวจสอบความสมบูรณ์และที่มาของเอกสาร สร้างขึ้นโดยใช้ใบรับรองดิจิทัลและอัลกอริธึมการเข้ารหัส ช่วยให้ผู้รับตรวจสอบได้ว่าเอกสารไม่มีการเปลี่ยนแปลงและมาจากแหล่งที่เชื่อถือได้

#### ถาม: ฉันจะเข้าถึงลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

ตอบ: หากต้องการเข้าถึงลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  โหลดเอกสารโดยใช้`Document` และระบุเส้นทางไปยังไฟล์เอกสาร
2.  ใช้การวนซ้ำเพื่อวนซ้ำผ่าน`DigitalSignatures` การรวบรวมเอกสาร การวนซ้ำแต่ละครั้งแสดงถึงลายเซ็นดิจิทัล

#### ถาม: ฉันสามารถเข้าถึงข้อมูลใดบ้างจากลายเซ็นดิจิทัลในเอกสาร Word

ตอบ: จากลายเซ็นดิจิทัลในเอกสาร Word คุณสามารถเข้าถึงข้อมูลต่างๆ ได้ เช่น:
- ความถูกต้อง: ตรวจสอบว่าลายเซ็นถูกต้องหรือไม่
- หมายเหตุ: ขอเหตุผลในการลงนามที่ผู้ลงนามระบุ
- Sign Time: รับเวลาที่ลงนามเอกสาร
- ชื่อหัวเรื่อง: เรียกค้นชื่อของผู้ลงนามหรือหัวเรื่องใบรับรอง
- ชื่อผู้ออก: รับชื่อของผู้ออกใบรับรอง

#### ถาม: ฉันสามารถตรวจสอบความถูกต้องของลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถตรวจสอบความถูกต้องของลายเซ็นดิจิทัลในเอกสาร Word ได้โดยใช้ Aspose.Words for .NET โดยเข้าไปที่`IsValid` ทรัพย์สินของ`DigitalSignature` วัตถุ คุณสามารถระบุได้ว่าลายเซ็นนั้นถูกต้องหรือไม่

#### ถาม: ฉันจะตรวจสอบความถูกต้องของลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: เมื่อต้องการตรวจสอบความถูกต้องของลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:
1.  เข้าถึง`DigitalSignatures` การรวบรวมเอกสาร
2.  ทำซ้ำผ่านแต่ละ`DigitalSignature` วัตถุในคอลเลกชัน
3.  ใช้`IsValid` ทรัพย์สินของ`DigitalSignature` วัตถุเพื่อตรวจสอบว่าลายเซ็นถูกต้องหรือไม่

#### ถาม: ฉันสามารถดึงความคิดเห็นของผู้ลงนามหรือเหตุผลในการเซ็นจากลายเซ็นดิจิทัลในเอกสาร Word ได้หรือไม่

ตอบ: ได้ คุณสามารถดึงความคิดเห็นของผู้ลงนามหรือเหตุผลในการเซ็นชื่อจากลายเซ็นดิจิทัลในเอกสาร Word ได้ ที่`Comments` ทรัพย์สินของ`DigitalSignature` วัตถุให้การเข้าถึงความคิดเห็นที่ระบุโดยผู้ลงนามในระหว่างกระบวนการลงนาม

#### ถาม: คุณสมบัติการตรวจสอบลายเซ็นรองรับเอกสารประเภทใดใน Aspose.Words สำหรับ .NET

ตอบ: คุณสมบัติการตรวจสอบลายเซ็นใน Aspose.Words สำหรับ .NET รองรับการตรวจสอบลายเซ็นดิจิทัลในเอกสาร Word ด้วยรูปแบบไฟล์ DOCX คุณสามารถใช้คุณสมบัตินี้เพื่อตรวจสอบลายเซ็นในไฟล์ DOCX

#### ถาม: ฉันจะเข้าถึงรายละเอียดใบรับรองของลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเข้าถึงรายละเอียดใบรับรองของลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถเข้าถึง`CertificateHolder` ทรัพย์สินของ`DigitalSignature` วัตถุ. จาก`CertificateHolder` วัตถุ คุณสามารถดึงรายละเอียดต่างๆ ของใบรับรอง เช่น ชื่อเรื่องและชื่อผู้ออกใบรับรอง

#### ถาม: ฉันสามารถปรับแต่งการแสดงหรือการประมวลผลลายเซ็นดิจิทัลในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งการแสดงหรือการประมวลผลลายเซ็นดิจิทัลในเอกสาร Word ได้โดยใช้ Aspose.Words สำหรับ .NET โดยการเข้าถึงคุณสมบัติและวิธีการของ`DigitalSignature` วัตถุ คุณสามารถดึงข้อมูลที่ต้องการ ดำเนินการตรวจสอบเพิ่มเติม หรือรวมกระบวนการตรวจสอบลายเซ็นเข้ากับขั้นตอนการทำงานของแอปพลิเคชันของคุณได้

#### ถาม: เป็นไปได้ไหมที่จะตรวจสอบลายเซ็นดิจิทัลหลายรายการในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

 ตอบ: ได้ คุณสามารถตรวจสอบลายเซ็นดิจิทัลหลายรายการในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้ โดยวนซ้ำผ่าน`DigitalSignatures` การรวบรวมเอกสาร คุณสามารถเข้าถึงและตรวจสอบลายเซ็นดิจิทัลแต่ละรายการได้

---
title: โหลด PDF ที่เข้ารหัส
linktitle: โหลด PDF ที่เข้ารหัส
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการโหลด PDF ที่เข้ารหัสโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

เมื่อประมวลผลคำด้วยเอกสาร PDF ในแอปพลิเคชัน .NET ของคุณ อาจจำเป็นต้องโหลดไฟล์ PDF ที่มีการป้องกันด้วยรหัสผ่าน Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งมีฟังก์ชันสำหรับการโหลดเอกสาร PDF ที่เข้ารหัส ในบทความนี้ เราจะแนะนำคุณทีละขั้นตอนเพื่อทำความเข้าใจและใช้ฟีเจอร์นี้

## ทำความเข้าใจเกี่ยวกับคุณสมบัติโหลด PDF ที่เข้ารหัส

คุณลักษณะ Load Encrypted PDF ของ Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถโหลดไฟล์ PDF ที่ได้รับการป้องกันด้วยรหัสผ่าน คุณสามารถระบุรหัสผ่านเมื่อโหลดเอกสารเพื่อให้คุณสามารถเข้าถึงเนื้อหาและจัดการได้ตามต้องการ

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร PDF ที่เข้ารหัส

ขั้นตอนแรกคือการโหลดเอกสาร PDF ที่เข้ารหัสลงในแอปพลิเคชันของคุณ ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไฟล์ PDF ที่เข้ารหัสใน`dataDir` ตัวแปร.

## ขั้นตอนที่ 2: การเข้ารหัสเอกสาร PDF

 หากคุณต้องการเข้ารหัสเอกสาร PDF ของคุณ คุณสามารถทำได้โดยใช้`PdfSaveOptions` คลาสและระบุรายละเอียดการเข้ารหัส:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

สิ่งนี้จะสร้างเอกสาร PDF เวอร์ชันที่เข้ารหัสในไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 3: บันทึกเอกสาร PDF ที่เข้ารหัส

หลังจากอัปโหลดและเข้ารหัสเอกสาร PDF แล้ว คุณสามารถบันทึกในรูปแบบอื่นหรือประมวลผลเพิ่มเติมได้ตามความต้องการเฉพาะของคุณ

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## ขั้นตอนที่ 5: กำลังโหลดเอกสาร PDF ที่เข้ารหัสด้วยรหัสผ่าน

การบำรุงรักษา

อย่างไรก็ตาม หากคุณต้องการโหลดเอกสาร PDF ที่เข้ารหัสด้วยรหัสผ่าน คุณต้องใช้ไฟล์`PdfLoadOptions` และระบุรหัสผ่านเมื่อโหลดเอกสาร:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 อย่าลืมระบุรหัสผ่านที่ถูกต้องใน`Password` ตัวแปร.

### ตัวอย่างซอร์สโค้ดสำหรับโหลด PDF ที่เข้ารหัสโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## บทสรุป

ในบทความนี้ เราได้ศึกษาวิธีใช้ฟีเจอร์ Load Encrypted PDF ของ Aspose.Words สำหรับ .NET คุณได้เรียนรู้วิธีอัปโหลดไฟล์ PDF ที่เข้ารหัส วิธีเข้ารหัสเอกสาร PDF วิธีอัปโหลด PDF ที่เข้ารหัสด้วยรหัสผ่าน และวิธีการสร้างเอาต์พุตในรูปแบบ Markdown คุณสมบัตินี้มีประโยชน์อย่างยิ่งเมื่อประมวลผลคำด้วยเอกสาร PDF ที่ปลอดภัย



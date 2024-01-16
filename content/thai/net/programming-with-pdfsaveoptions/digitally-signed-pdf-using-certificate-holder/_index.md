---
title: เพิ่มลายเซ็นดิจิทัลลงใน PDF โดยใช้ผู้ถือใบรับรอง
linktitle: เพิ่มลายเซ็นดิจิทัลลงใน PDF โดยใช้ผู้ถือใบรับรอง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มลายเซ็นดิจิทัลลงใน PDF โดยใช้ผู้ถือใบรับรองด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการเพิ่มลายเซ็นดิจิทัลลงใน PDF โดยใช้ผู้ถือใบรับรองกับ Aspose.Words สำหรับ .NET ลายเซ็นดิจิทัลเพิ่มชั้นความปลอดภัยและความสมบูรณ์ให้กับเอกสาร PDF ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: การสร้างเอกสารและเพิ่มเนื้อหา

เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาสเอกสาร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: เพิ่มเนื้อหาลงในเอกสาร

 จากนั้นใช้`DocumentBuilder`เพื่อเพิ่มเนื้อหาลงในเอกสาร ตัวอย่างเช่น หากต้องการเพิ่มย่อหน้าที่มีข้อความ "Test Signed PDF" ให้ใช้`Writeln` วิธี:

```csharp
builder.Writeln("Test Signed PDF.");
```

คุณสามารถเพิ่มรายการเนื้อหาอื่นๆ ได้ตามต้องการ

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการบันทึก PDF

สร้างอินสแตนซ์ของคลาส PdfSaveOptions และระบุรายละเอียดลายเซ็นดิจิทัล:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังใบรับรองและรหัสผ่านที่เกี่ยวข้องของคุณ คุณยังสามารถปรับแต่งเหตุผลและตำแหน่งของลายเซ็นได้

## ขั้นตอนที่ 4: บันทึกเอกสารเป็น PDF ที่เซ็นชื่อแบบดิจิทัล

 ใช้`Save` วิธีการบันทึกเอกสารเป็น PDF โดยระบุตัวเลือกการบันทึก:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องเพื่อบันทึก PDF ที่เซ็นชื่อแบบดิจิทัล

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้าง PDF ที่เซ็นชื่อแบบดิจิทัลพร้อมใบรับรองโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างง่ายดาย

### ตัวอย่างซอร์สโค้ดสำหรับ PDF ที่ลงนามแบบดิจิทัลโดยใช้ผู้ถือใบรับรองโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์ของ Pdf ที่เซ็นชื่อแบบดิจิทัลโดยใช้ผู้ถือใบรับรองจากเอกสารที่ใช้ Aspose.Words สำหรับ .NET:

```csharp

            // เส้นทางไปยังไดเร็กทอรีเอกสาร
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจขั้นตอนในการเพิ่มลายเซ็นดิจิทัลลงในเอกสาร PDF โดยใช้ใบรับรองที่มี Aspose.Words สำหรับ .NET ลายเซ็นดิจิทัลจะเพิ่มชั้นความปลอดภัยและความสมบูรณ์ให้กับเอกสาร จึงรับประกันความถูกต้องของเอกสาร และทำให้สามารถตรวจจับการแก้ไขใดๆ ในภายหลังได้ เมื่อทำตามขั้นตอนที่กำหนด คุณสามารถสร้าง PDF ที่เซ็นชื่อแบบดิจิทัลได้อย่างง่ายดายโดยใช้ใบรับรองที่มี Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ลายเซ็นดิจิทัลคืออะไร และเหตุใดจึงมีความสำคัญในเอกสาร PDF
ตอบ: ลายเซ็นดิจิทัลเป็นเทคนิคการรักษาความปลอดภัยที่ช่วยรับรองความถูกต้อง ความสมบูรณ์ และการไม่ปฏิเสธเอกสารอิเล็กทรอนิกส์ เช่น ไฟล์ PDF ใช้ใบรับรองดิจิทัลเพื่อเพิ่มชั้นความปลอดภัยให้กับเอกสาร ซึ่งช่วยตรวจสอบตัวตนของผู้เขียนและตรวจจับการเปลี่ยนแปลงใดๆ ที่เกิดขึ้นกับเนื้อหาในภายหลัง

#### ถาม: ฉันจะเพิ่มลายเซ็นดิจิทัลลงในเอกสาร PDF โดยใช้ใบรับรองกับ Aspose.Words สำหรับ .NET ได้อย่างไร
ตอบ: หากต้องการเพิ่มลายเซ็นดิจิทัลลงในเอกสาร PDF โดยใช้ใบรับรองกับ Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

 สร้างอินสแตนซ์ของ`Document` คลาสเพื่อแสดงเอกสาร

 ใช้`DocumentBuilder` คลาสเพื่อเพิ่มเนื้อหาที่ต้องการลงในเอกสาร

 สร้างอินสแตนซ์ของ`PdfSaveOptions` และระบุรายละเอียดลายเซ็นดิจิทัลโดยใช้`PdfDigitalSignatureDetails` ระดับ. คุณจะต้องระบุเส้นทางไปยังใบรับรอง (`CertificateHolder.Create`) รหัสผ่านที่เกี่ยวข้อง ตลอดจนเหตุผลและสถานที่ในการลงนาม

 ใช้`Save` วิธีการบันทึกเอกสารในรูปแบบ PDF โดยระบุตัวเลือกการบันทึก

#### ถาม: ฉันจะได้รับใบรับรองเพื่อเพิ่มลายเซ็นดิจิทัลลงในเอกสาร PDF ได้อย่างไร
ตอบ: หากต้องการขอรับใบรับรองเพื่อเพิ่มลายเซ็นดิจิทัลลงในเอกสาร PDF โดยปกติแล้ว คุณจะสามารถติดต่อผู้ออกใบรับรอง (CA) หรือผู้ให้บริการที่เชื่อถือได้ หน่วยงานเหล่านี้จะออกใบรับรองดิจิทัลหลังจากยืนยันตัวตนของคุณและตรวจสอบคำขอของคุณแล้ว เมื่อคุณได้รับใบรับรองแล้ว คุณจะสามารถใช้ใบรับรองดังกล่าวในแอปพลิเคชันของคุณเพื่อเพิ่มลายเซ็นดิจิทัลลงในเอกสาร PDF ได้

#### ถาม: สามารถปรับแต่งรายละเอียดของลายเซ็นดิจิทัล เช่น เหตุผลและสถานที่ ได้หรือไม่
 ตอบ: ได้ คุณสามารถปรับแต่งรายละเอียดลายเซ็นดิจิทัลได้โดยการระบุเหตุผลและตำแหน่งของลายเซ็น ในโค้ดตัวอย่างที่ให้มา คุณสามารถแก้ไขค่าของ`reason` และ`location` พารามิเตอร์เมื่อสร้าง`PdfDigitalSignatureDetails` วัตถุ. อย่าลืมให้ข้อมูลที่เหมาะสมสำหรับแต่ละพารามิเตอร์เพื่อสะท้อนเหตุผลและตำแหน่งของลายเซ็นในเอกสาร PDF ของคุณ
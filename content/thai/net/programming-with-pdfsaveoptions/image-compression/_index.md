---
title: การบีบอัดรูปภาพในเอกสาร PDF
linktitle: การบีบอัดรูปภาพในเอกสาร PDF
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการบีบอัดรูปภาพในเอกสาร PDF ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfsaveoptions/image-compression/
---

บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการใช้การบีบอัดรูปภาพในฟีเจอร์เอกสาร PDF ด้วย Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนโดยละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีบีบอัดรูปภาพในเอกสารและสร้าง PDF ด้วยการบีบอัดรูปภาพที่เหมาะสม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดูไลบรารีและคำแนะนำในการติดตั้งได้จากเว็บไซต์ Aspose

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ในการเริ่มต้น คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของคุณอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: อัปโหลดเอกสาร

ต่อไปเราต้องโหลดเอกสารที่เราต้องการดำเนินการ ในตัวอย่างนี้ เราถือว่าเอกสารชื่อ "Rendering.docx" และอยู่ในไดเร็กทอรีเอกสารที่ระบุ

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกบันทึกเป็น PDF ด้วยการบีบอัดรูปภาพ

 ในการบีบอัดรูปภาพเมื่อแปลงเป็น PDF เราจำเป็นต้องกำหนดค่า`PdfSaveOptions` วัตถุ วัตถุ เราสามารถตั้งค่าประเภทการบีบอัดภาพ คุณภาพ JPEG และตัวเลือกการปฏิบัติตาม PDF อื่นๆ ได้ หากจำเป็น

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## ขั้นตอนที่ 4: บันทึกเอกสารเป็น PDF ด้วยการบีบอัดรูปภาพ

สุดท้ายนี้ เราสามารถบันทึกเอกสารในรูปแบบ PDF โดยใช้ตัวเลือกการบันทึกที่กำหนดค่าไว้ก่อนหน้านี้

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## ขั้นตอนที่ 5: กำหนดค่าตัวเลือกสำหรับการบันทึกเป็น PDF/A-2u ด้วยการบีบอัดรูปภาพ

หากคุณต้องการสร้าง PDF ที่รองรับ PDF/A-2u ด้วยการบีบอัดรูปภาพ คุณสามารถกำหนดค่าตัวเลือกการบันทึกเพิ่มเติมได้

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // ใช้การบีบอัด JPEG ที่มีคุณภาพ 50% เพื่อลดขนาดไฟล์
};
```

## ขั้นตอนที่ 6: บันทึกเอกสารเป็น PDF/A-2u ด้วยการบีบอัดรูปภาพ

บันทึกเอกสารในรูปแบบ PDF/A-2u โดยใช้ตัวเลือกการบันทึกเพิ่มเติมที่กำหนดค่าไว้ก่อนหน้านี้

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



นั่นคือทั้งหมด! คุณบีบอัดรูปภาพในเอกสารได้สำเร็จและสร้าง PDF ด้วยการบีบอัดรูปภาพที่เหมาะสมโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับการบีบอัดรูปภาพด้วย Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // ใช้การบีบอัด JPEG ที่คุณภาพ 50% เพื่อลดขนาดไฟล์
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีบีบอัดรูปภาพในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ คุณสามารถลดขนาดรูปภาพในเอกสาร PDF ของคุณได้อย่างง่ายดาย และสร้าง PDF ด้วยการบีบอัดรูปภาพที่เหมาะสม ใช้คุณสมบัติการบีบอัดภาพของ Aspose.Words สำหรับ .NET เพื่อปรับขนาดเอกสาร PDF ของคุณให้เหมาะสมที่สุดในขณะที่ยังคงรักษาคุณภาพของภาพไว้

### คำถามที่พบบ่อย

#### ถาม: การบีบอัดรูปภาพในเอกสาร PDF คืออะไร
ตอบ: การบีบอัดรูปภาพในเอกสาร PDF คือการลดขนาดของรูปภาพที่รวมอยู่ในเอกสาร PDF เพื่อลดขนาดโดยรวมของไฟล์ PDF ซึ่งจะช่วยลดพื้นที่จัดเก็บข้อมูลที่จำเป็นและปรับปรุงประสิทธิภาพในการโหลดและดู PDF

#### ถาม: ฉันจะบีบอัดรูปภาพในเอกสาร PDF ด้วย Aspose.Words สำหรับ .NET ได้อย่างไร
ตอบ: หากต้องการบีบอัดรูปภาพในเอกสาร PDF ด้วย Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

 สร้างอินสแตนซ์ของ`Document` คลาสที่ระบุเส้นทางไปยังเอกสาร Word

 สร้างอินสแตนซ์ของ`PdfSaveOptions` คลาสและตั้งค่า`ImageCompression`ทรัพย์สินเพื่อ`PdfImageCompression.Jpeg` เพื่อใช้การบีบอัด JPEG

คุณยังสามารถตั้งค่าตัวเลือกการบีบอัดรูปภาพอื่นๆ ได้ เช่น คุณภาพ JPEG ตามความต้องการของคุณ

 ใช้`Save` วิธีการของ`Document`คลาสเพื่อบันทึกเอกสารในรูปแบบ PDF โดยระบุตัวเลือกการบันทึก

#### ถาม: อะไรคือความแตกต่างระหว่างการบีบอัดภาพมาตรฐานและการบีบอัดภาพ PDF/A-2u?
ตอบ: การบีบอัดรูปภาพมาตรฐานจะลดขนาดของรูปภาพในเอกสาร PDF ในขณะที่ยังคงรักษาฟิลด์แบบฟอร์มไว้ ซึ่งจะช่วยลดขนาดโดยรวมของไฟล์ PDF โดยไม่กระทบต่อการทำงานของฟิลด์แบบฟอร์ม

การบีบอัดรูปภาพด้วย PDF/A-2u เป็นตัวเลือกเพิ่มเติมที่ช่วยให้คุณสามารถสร้างไฟล์ PDF ที่เป็นไปตามมาตรฐาน PDF/A-2u ในขณะที่ใช้การบีบอัดรูปภาพ PDF/A-2u เป็นมาตรฐาน ISO สำหรับเอกสาร PDF ที่เก็บถาวรและรับประกันการเก็บรักษาเอกสารในระยะยาว

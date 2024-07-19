---
title: โหลดหน้าช่วงของ Pdf
linktitle: โหลดหน้าช่วงของ Pdf
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการโหลดช่วงหน้า PDF เฉพาะด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

ในบทช่วยสอนนี้ เราจะอธิบายวิธีการโหลดช่วงหน้าเฉพาะจากเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่าง:

## ขั้นตอนที่ 1: กำลังโหลดหน้า PDF หลายหน้า

ใช้รหัสต่อไปนี้เพื่อโหลดช่วงหน้าเฉพาะจากเอกสาร PDF:

```csharp
//พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 ในตัวอย่างนี้ เรากำลังโหลดหน้าแรกของเอกสาร PDF คุณสามารถเปลี่ยนค่าของ`PageIndex`และ`PageCount` ไปจนถึงช่วงหน้าที่ต้องการ

## ขั้นตอนที่ 2: บันทึกเอกสาร

 สุดท้าย คุณสามารถบันทึกเอกสารที่มีช่วงหน้าเฉพาะได้โดยใช้`Save` วิธี:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

อย่าลืมระบุเส้นทางที่ถูกต้องเพื่อบันทึกเอกสารที่แก้ไข

นั่นคือทั้งหมดที่ ! ขณะนี้ คุณได้โหลดช่วงหน้าเฉพาะจากเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET แล้ว

### ตัวอย่างซอร์สโค้ดสำหรับโหลดช่วงหน้าของ Pdf โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีของเอกสาร PDF ของคุณ




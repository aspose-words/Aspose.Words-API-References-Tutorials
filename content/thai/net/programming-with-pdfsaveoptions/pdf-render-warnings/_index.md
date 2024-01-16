---
title: คำเตือนการเรนเดอร์ Pdf
linktitle: คำเตือนการเรนเดอร์ Pdf
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการจัดการกับคำเตือนการเรนเดอร์ PDF ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการใช้ฟีเจอร์คำเตือนการแสดงผล PDF กับ Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนโดยละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีจัดการกับการแสดงคำเตือนเมื่อแปลงเป็น PDF

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดูไลบรารีและคำแนะนำในการติดตั้งได้จากเว็บไซต์ Aspose

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ในการเริ่มต้น คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของคุณอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: อัปโหลดเอกสาร

ต่อไปเราต้องโหลดเอกสารที่เราต้องการดำเนินการ ในตัวอย่างนี้ เราถือว่าเอกสารชื่อ "WMF with image.docx" และอยู่ในไดเร็กทอรีเอกสารที่ระบุ

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกบันทึกเป็น PDF พร้อมคำเตือนการเรนเดอร์

 ในการจัดการกับคำเตือนการเรนเดอร์เมื่อแปลงเป็น PDF เราจำเป็นต้องกำหนดค่า`MetafileRenderingOptions` วัตถุเพื่อระบุวิธีการแสดงผล metafiles เรายังใช้`HandleDocumentWarnings` ตัวเลือกในการจัดการคำเตือนที่เกิดขึ้นเมื่อบันทึกเอกสาร

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## ขั้นตอนที่ 4: บันทึกเอกสารเป็น PDF พร้อมคำเตือนการเรนเดอร์

สุดท้ายนี้ เราสามารถบันทึกเอกสารในรูปแบบ PDF โดยใช้ตัวเลือกการบันทึกที่กำหนดค่าไว้ก่อนหน้านี้

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## ขั้นตอนที่ 5: จัดการคำเตือนการแสดงผล

คำเตือนการแสดงผลที่สร้างขึ้นเมื่อบันทึกเอกสารสามารถเรียกข้อมูลได้โดยใช้ตัวจัดการคำเตือนแบบกำหนดเอง ในตัวอย่างนี้ เราเพียงแค่พิมพ์คำอธิบายของคำเตือนแต่ละรายการ

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

นั่นคือทั้งหมดที่ ! คุณจัดการคำเตือนการแสดงผลเมื่อแปลงเอกสารได้สำเร็จ

  เป็น PDF โดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับคำเตือนการเรนเดอร์ PDF ด้วย Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	//หาก Aspose.Words ไม่สามารถแสดงบันทึก metafile บางส่วนได้อย่างถูกต้อง
	// เป็นกราฟิกแบบเวกเตอร์ จากนั้น Aspose.Words จะแสดงผล metafile นี้เป็นบิตแมป
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// แม้ว่าไฟล์จะบันทึกได้สำเร็จ แต่คำเตือนการแสดงผลที่เกิดขึ้นระหว่างการบันทึกจะถูกรวบรวมไว้ที่นี่
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

### คำถามที่พบบ่อย

#### ถาม: ฟังก์ชั่นคำเตือนการเรนเดอร์ PDF ด้วย Aspose.Words สำหรับ .NET คืออะไร
คุณลักษณะคำเตือนการเรนเดอร์ PDF พร้อม Aspose.Words สำหรับ .NET ช่วยจัดการคำเตือนที่สร้างขึ้นเมื่อแปลงเอกสารเป็น PDF โดยให้วิธีการตรวจจับและจัดการกับคำเตือนในการแสดงผลเพื่อให้มั่นใจในคุณภาพและความสมบูรณ์ของเอกสารที่แปลงแล้ว

#### ถาม: ฉันจะใช้ฟีเจอร์นี้กับ Aspose.Words สำหรับ .NET ได้อย่างไร
เมื่อต้องการใช้คุณลักษณะนี้กับ Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

ตั้งค่าไดเร็กทอรีเอกสารโดยระบุพาธไดเร็กทอรีที่มีเอกสารของคุณอยู่

 โหลดเอกสารที่จะประมวลผลโดยใช้`Document` วิธีการและระบุเส้นทางไฟล์

 กำหนดค่าตัวเลือกบันทึกเป็น PDF โดยการสร้างอินสแตนซ์ของ`PdfSaveOptions` ระดับ. ใช้`MetafileRenderingOptions` เพื่อระบุวิธีการเรนเดอร์เมตาไฟล์และตั้งค่า`MetafileRenderingOptions.RenderingMode` ถึง`MetafileRenderingMode.VectorWithFallback`.

 ใช้`HandleDocumentWarnings` คลาสเพื่อจัดการการเรนเดอร์คำเตือน ชุด`doc.WarningCallback` ไปยังอินสแตนซ์ของคลาสนี้

 ใช้`Save` วิธีการบันทึกเอกสารในรูปแบบ PDF โดยระบุตัวเลือกการบันทึก

จากนั้นคุณสามารถจัดการคำเตือนการเรนเดอร์ได้โดยใช้`HandleDocumentWarnings` ระดับ. ตัวอย่างเช่น คุณสามารถแสดงคำอธิบายของคำเตือนแต่ละรายการโดยใช้การวนซ้ำ

#### ถาม: ฉันจะทราบได้อย่างไรว่ามีคำเตือนเกี่ยวกับการเรนเดอร์เมื่อแปลงเอกสารเป็น PDF
 คุณสามารถใช้`HandleDocumentWarnings` คลาสเพื่อดึงคำเตือนการเรนเดอร์ที่สร้างขึ้นเมื่อบันทึกเอกสาร ชั้นเรียนนี้ประกอบด้วยก`mWarnings` รายการที่เก็บข้อมูลเกี่ยวกับคำเตือน คุณสามารถเรียกดูรายการนี้และเข้าถึงคุณสมบัติของคำเตือนแต่ละรายการ เช่น คำอธิบาย เพื่อดำเนินการที่เหมาะสม

#### ถาม: คำเตือนการเรนเดอร์ประเภทใดที่สามารถสร้างได้เมื่อแปลงเป็น PDF
คำเตือนการแสดงผลเมื่อแปลงเป็น PDF อาจรวมถึงคำเตือนที่เกี่ยวข้องกับเค้าโครง แบบอักษรที่หายไป รูปภาพที่ไม่รองรับ ปัญหาความเข้ากันได้ ฯลฯ คำเตือนเฉพาะจะขึ้นอยู่กับเนื้อหาของเอกสารต้นฉบับและตัวเลือกการแปลงที่ใช้

#### ถาม: เป็นไปได้ไหมที่จะจัดการการเรนเดอร์คำเตือนด้วยวิธีที่กำหนดเอง
 ใช่ คุณสามารถปรับแต่งการจัดการคำเตือนการเรนเดอร์ได้โดยปรับแต่ง`HandleDocumentWarnings`ระดับ. คุณสามารถเพิ่มฟังก์ชันเพิ่มเติมเพื่อจัดการคำเตือนเฉพาะสำหรับแอปพลิเคชันของคุณ เช่น คำเตือนในการบันทึก การสร้างรายงาน การส่งการแจ้งเตือน และอื่นๆ
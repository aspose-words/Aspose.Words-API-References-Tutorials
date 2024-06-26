---
title: ลดขนาด PDF ด้วยปรับขนาดแบบอักษร Wmf เป็นขนาด Metafile
linktitle: ลดขนาด PDF ด้วยปรับขนาดแบบอักษร Wmf เป็นขนาด Metafile
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการลดขนาด PDF ด้วยแบบอักษร wmf ที่ปรับขนาดเป็นขนาด metafile เมื่อแปลงเป็น PDF ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีลดขนาด PDF ด้วยฟีเจอร์ปรับขนาดฟอนต์ wmf ให้เป็นขนาด metafile ด้วย Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนโดยละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีเปิดหรือปิดใช้งานการปรับขนาดแบบอักษร WMF เมื่อแปลงเป็น PDF

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดูไลบรารีและคำแนะนำในการติดตั้งได้จากเว็บไซต์ Aspose

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

 ในการเริ่มต้น คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีที่มีเอกสารของคุณอยู่ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: อัปโหลดเอกสาร

ต่อไปเราต้องโหลดเอกสารที่เราต้องการดำเนินการ ในตัวอย่างนี้ เราถือว่าเอกสารชื่อ "WMF with text.docx" และอยู่ในไดเร็กทอรีเอกสารที่ระบุ

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการเรนเดอร์ metafile

 หากต้องการเปิดใช้งานหรือปิดใช้งานการปรับขนาดแบบอักษร WMF เป็นขนาด metafile เราจำเป็นต้องกำหนดค่า`MetafileRenderingOptions` วัตถุ วัตถุ ในตัวอย่างนี้ เราปิดใช้งานการปรับขนาดแบบอักษรโดยการตั้งค่า`ScaleWmfFontsToMetafileSize`ทรัพย์สินเพื่อ`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกบันทึกเป็น PDF ด้วยตัวเลือกการเรนเดอร์ metafile

สุดท้ายนี้ เราสามารถกำหนดค่าตัวเลือกบันทึกเป็น PDF ได้โดยใช้ตัวเลือกการเรนเดอร์ metafile ที่กำหนดค่าไว้ก่อนหน้านี้

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## ขั้นตอนที่ 5: บันทึกเอกสารเป็น PDF ด้วยตัวเลือกการเรนเดอร์ Metafile

บันทึกเอกสารในรูปแบบ PDF โดยใช้ตัวเลือกการบันทึกที่กำหนดค่าไว้ก่อนหน้านี้

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

นั่นคือทั้งหมด! คุณได้เปิดใช้งานหรือปิดใช้งานการปรับขนาดฟอนต์ WMF เป็นขนาดเมตาไฟล์สำเร็จแล้วเมื่อทำการแปลง

เอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดสำหรับการปรับขนาดฟอนต์ WMF เป็นขนาดเมตาไฟล์ด้วย Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//หาก Aspose.Words ไม่สามารถแสดงบันทึก metafile บางส่วนเป็นกราฟิกแบบเวกเตอร์ได้อย่างถูกต้อง
	// จากนั้น Aspose.Words จะแสดงผล metafile นี้เป็นบิตแมป
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีเปิดหรือปิดการปรับขนาดฟอนต์ WMF เป็นขนาดเมตาไฟล์ในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ คุณสามารถควบคุมได้อย่างง่ายดายว่าควรปรับขนาดฟอนต์ WMF ให้ตรงกับขนาดเมตาไฟล์เมื่อแปลงเป็นเอกสาร PDF หรือไม่ วิธีนี้สามารถช่วยลดขนาดของไฟล์ PDF ที่สร้างขึ้นและปรับปรุงประสิทธิภาพการเรนเดอร์ได้ อย่าลืมระบุเส้นทางที่ถูกต้องไปยังเอกสารของคุณและกำหนดค่าตัวเลือกการแสดงผล metafile ตามความจำเป็น

### คำถามที่พบบ่อย

#### ถาม: การปรับขนาดแบบอักษร WMF เป็นขนาด metafile ในเอกสาร PDF คืออะไร
ตอบ: การปรับขนาดฟอนต์ WMF เป็นขนาดเมตาไฟล์ในเอกสาร PDF เป็นคุณสมบัติที่ควบคุมว่าควรปรับขนาดฟอนต์ WMF ให้ตรงกับขนาดเมตาไฟล์เมื่อแปลงเป็นเอกสาร PDF หรือไม่ เมื่อเปิดใช้งานคุณสมบัตินี้ แบบอักษร WMF จะถูกปรับขนาดให้ตรงกับขนาดของเมตาไฟล์ ซึ่งอาจลดขนาดของเอกสาร PDF ที่สร้างขึ้น

#### ถาม: ฉันจะใช้ Aspose.Words สำหรับ .NET เพื่อเปิดหรือปิดการปรับขนาดฟอนต์ WMF เป็นขนาดเมตาไฟล์ในเอกสาร PDF ได้อย่างไร
ตอบ: หากต้องการเปิดใช้งานหรือปิดใช้งานการปรับขนาดแบบอักษร WMF เป็นขนาด metafile ในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

 กำหนดเส้นทางไดเร็กทอรีที่มีเอกสารของคุณอยู่โดยการแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีเอกสารของคุณ

 โหลดเอกสารที่คุณต้องการประมวลผลโดยใช้`Document` และระบุเส้นทางไปยังเอกสาร Word ในไดเร็กทอรีเอกสารที่ระบุ

 กำหนดค่าตัวเลือกการเรนเดอร์ metafile โดยการสร้างอินสแตนซ์ของ`MetafileRenderingOptions` คลาสและการตั้งค่า`ScaleWmfFontsToMetafileSize`ทรัพย์สินเพื่อ`true` เพื่อเปิดใช้งานการปรับขนาดแบบอักษร WMF เป็นขนาด metafile หรือเป็น`false` เพื่อปิดการใช้งานคุณสมบัตินี้

 กำหนดค่าตัวเลือกบันทึกเป็น PDF โดยการสร้างอินสแตนซ์ของ`PdfSaveOptions` คลาสและใช้ตัวเลือกการเรนเดอร์ metafile ที่กำหนดค่าไว้ก่อนหน้านี้

 บันทึกเอกสารในรูปแบบ PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` คลาสที่ระบุเส้นทางและตัวเลือกการบันทึก

#### ถาม: การปรับขนาดฟอนต์ WMF เป็นขนาด metafile ในเอกสาร PDF มีประโยชน์อย่างไร
ตอบ: ข้อดีของการปรับขนาดฟอนต์ WMF เป็นขนาดเมตาไฟล์ในเอกสาร PDF คือ:

การลดขนาดไฟล์ PDF: การปรับขนาดฟอนต์ WMF เป็นขนาดเมตาไฟล์สามารถลดขนาดของเอกสาร PDF ที่สร้างขึ้นได้โดยการปรับขนาดฟอนต์ให้ตรงกับความต้องการของเมตาไฟล์

ปรับปรุงประสิทธิภาพ: ด้วยการปรับขนาดฟอนต์ WMF ให้เป็นขนาดของเมตาไฟล์ การเรนเดอร์เอกสาร PDF จะเร็วขึ้นและมีประสิทธิภาพมากขึ้น
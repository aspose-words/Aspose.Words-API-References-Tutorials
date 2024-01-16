---
title: ตั้งค่าตัวเลือกเค้าร่างในเอกสาร PDF
linktitle: ตั้งค่าตัวเลือกเค้าร่างในเอกสาร PDF
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าตัวเลือกโครงร่างในเอกสาร PDF ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-pdfsaveoptions/set-outline-options/
---

บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการใช้ตัวเลือกเค้าร่างการตั้งค่าคุณลักษณะขนาด metafile ด้วย Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนโดยละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีตั้งค่าตัวเลือกเค้าร่างในเอกสารและสร้าง PDF ที่มีตัวเลือกเค้าร่างที่เกี่ยวข้องได้

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

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกบันทึกเป็น PDF พร้อมตัวเลือกแผน

 ในการตั้งค่าตัวเลือกโครงร่างใน PDF ที่สร้างขึ้น เราจำเป็นต้องกำหนดค่า`PdfSaveOptions` วัตถุ. เราสามารถกำหนดจำนวนระดับโครงร่างส่วนหัวได้ (`HeadingsOutlineLevels`) และจำนวนระดับโครงร่างที่ขยาย (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## ขั้นตอนที่ 4: บันทึกเอกสารเป็น PDF พร้อมตัวเลือกโครงร่าง

สุดท้ายนี้ เราสามารถบันทึกเอกสารในรูปแบบ PDF โดยใช้ตัวเลือกการบันทึกที่กำหนดค่าไว้ก่อนหน้านี้

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

นั่นคือทั้งหมดที่ ! คุณได้ตั้งค่าตัวเลือกเค้าร่างในเอกสารเรียบร้อยแล้ว และสร้าง PDF ที่มีตัวเลือกเค้าร่างที่เกี่ยวข้องโดยใช้ Aspose.Words สำหรับ .NET

### ตัวอย่างซอร์สโค้ดเพื่อตั้งค่าตัวเลือกแผนเป็นขนาด metafile ด้วย Aspose.Words สำหรับ .NET


```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายวิธีตั้งค่าตัวเลือกเค้าร่างในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET เมื่อใช้ขั้นตอนที่อธิบายไว้ คุณสามารถระบุระดับหัวเรื่องและโครงร่างในเอกสารของคุณได้อย่างง่ายดาย และสร้างไฟล์ PDF ที่มีตัวเลือกโครงร่างที่เกี่ยวข้อง เพลิดเพลินไปกับคุณประโยชน์ของตัวเลือกเค้าร่างเพื่อปรับปรุงโครงสร้างและการนำทางในเอกสาร PDF ของคุณโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ตัวเลือกโครงร่างในเอกสาร PDF คืออะไร
ตอบ: ตัวเลือกเค้าร่างในเอกสาร PDF อ้างอิงถึงโครงสร้างลำดับชั้นของเนื้อหาเอกสาร ช่วยให้คุณสร้างสารบัญแบบโต้ตอบและอำนวยความสะดวกในการนำทางในเอกสาร ตัวเลือกเค้าร่างจะกำหนดชื่อเรื่องและระดับคำบรรยายที่จะรวมไว้ในโครงร่างและระดับรายละเอียดที่จะแสดงในโครงร่างที่สร้างขึ้น

#### ถาม: ฉันจะตั้งค่าตัวเลือกโครงร่างในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร
ตอบ: หากต้องการตั้งค่าตัวเลือกโครงร่างในเอกสาร PDF โดยใช้ Aspose.Words สำหรับ .NET ให้ทำตามขั้นตอนเหล่านี้:

 กำหนดเส้นทางไดเร็กทอรีที่มีเอกสารของคุณอยู่โดยการแทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีเอกสารของคุณ

 โหลดเอกสารที่คุณต้องการแปลงเป็น PDF โดยใช้`Document` และระบุเส้นทางไปยังเอกสารในไดเร็กทอรีเอกสารที่ระบุ

 กำหนดค่าตัวเลือกบันทึกเป็น PDF โดยการสร้างอินสแตนซ์ของ`PdfSaveOptions` คลาสและการใช้งาน`OutlineOptions` คุณสมบัติเพื่อตั้งค่าตัวเลือกเค้าร่าง คุณสามารถระบุจำนวนระดับส่วนหัวที่จะรวมไว้ในโครงร่างได้โดยใช้`HeadingsOutlineLevels` คุณสมบัติและจำนวนระดับโครงร่างที่ขยายโดยใช้`ExpandedOutlineLevels` คุณสมบัติ.

 บันทึกเอกสารในรูปแบบ PDF โดยใช้ไฟล์`Save` วิธีการของ`Document` คลาสที่ระบุเส้นทางและตัวเลือกการบันทึก

#### ถาม: ตัวเลือกแผนในเอกสาร PDF คืออะไร
ตอบ: ตัวเลือกเค้าร่างในเอกสาร PDF ช่วยให้คุณสร้างโครงสร้างเนื้อหาแบบลำดับชั้น ซึ่งทำให้ง่ายต่อการนำทางเอกสารและเข้าถึงส่วนต่างๆ ซึ่งช่วยให้ผู้ใช้สามารถข้ามไปยังส่วนเฉพาะของเอกสารได้อย่างรวดเร็วโดยคลิกรายการในสารบัญหรือโครงร่าง ตัวเลือกโครงร่างยังช่วยปรับปรุงประสบการณ์การอ่านด้วยการให้ภาพรวมของโครงสร้างเอกสารโดยรวม
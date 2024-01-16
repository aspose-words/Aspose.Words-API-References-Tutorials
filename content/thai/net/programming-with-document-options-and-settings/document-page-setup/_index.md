---
title: การตั้งค่าหน้าเอกสาร
linktitle: การตั้งค่าหน้าเอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าเค้าโครงเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-options-and-settings/document-page-setup/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อกำหนดค่าเค้าโครงเอกสารด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถตั้งค่าโหมดเค้าโครง จำนวนอักขระต่อบรรทัด และจำนวนบรรทัดต่อหน้า

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่เราต้องการกำหนดค่า ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: การตั้งค่าเค้าโครง

ตอนนี้เรามากำหนดค่าเค้าโครงเอกสารกันดีกว่า ใช้รหัสต่อไปนี้เพื่อตั้งค่าโหมดเค้าโครง จำนวนอักขระต่อบรรทัด และจำนวนบรรทัดต่อหน้า:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

รหัสนี้ตั้งค่าโหมดเค้าโครงเป็น "ตาราง" จากนั้นระบุจำนวนอักขระต่อบรรทัดและจำนวนบรรทัดต่อหน้า

### ตัวอย่างซอร์สโค้ดสำหรับการตั้งค่าหน้าเอกสารโดยใช้ Aspose.Words สำหรับ .NET


```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// ตั้งค่าโหมดเค้าโครงสำหรับส่วนที่อนุญาตให้กำหนดลักษณะการทำงานของตารางเอกสาร
	// โปรดทราบว่าแท็บ Document Grid จะปรากฏในกล่องโต้ตอบการตั้งค่าหน้ากระดาษของ MS Word
	// หากภาษาเอเชียใดถูกกำหนดให้เป็นภาษาแก้ไข
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีกำหนดค่าเค้าโครงของเอกสารโดยใช้ Aspose.Words สำหรับ .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนในบทช่วยสอนนี้ คุณสามารถปรับแต่งเลย์เอาต์ของเอกสารของคุณเองได้อย่างง่ายดาย
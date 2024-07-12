---
title: ล้างข้อมูลสไตล์และรายการที่ไม่ได้ใช้
linktitle: ล้างข้อมูลสไตล์และรายการที่ไม่ได้ใช้
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการล้างสไตล์และรายการที่ไม่ได้ใช้ในเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อล้างสไตล์และรายการที่ไม่ได้ใช้ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถลบสไตล์และรายการที่ไม่ได้ใช้ในเอกสารได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่มีสไตล์และรายการที่ไม่ได้ใช้ซึ่งเราต้องการล้างข้อมูล ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: นับสไตล์และรายการก่อนทำความสะอาด

ก่อนทำความสะอาด เราจะนับจำนวนรูปแบบและรายการที่มีอยู่ในเอกสาร ใช้รหัสต่อไปนี้เพื่อแสดงตัวนับ:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

คำแนะนำเหล่านี้แสดงจำนวนรูปแบบและรายการที่มีอยู่ในเอกสารก่อนทำความสะอาด

## ขั้นตอนที่ 4: ล้างสไตล์และรายการที่ไม่ได้ใช้

ตอนนี้เรามาทำความสะอาดสไตล์และรายการที่ไม่ได้ใช้จากเอกสารกันดีกว่า ใช้รหัสต่อไปนี้เพื่อดำเนินการล้างข้อมูล:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 รหัสนี้จะล้างสไตล์และรายการที่ไม่ได้ใช้ออกจากเอกสารโดยใช้ตัวเลือกที่ระบุ ในตัวอย่างนี้ เราเปิดใช้งานไฟล์`UnusedStyles` ตัวเลือกในการลบสไตล์ที่ไม่ได้ใช้และปิดการใช้งาน`UnusedLists` ตัวเลือกในการเก็บรายการแม้ว่าจะไม่ได้ใช้ก็ตาม

## ขั้นตอนที่ 5: นับสไตล์และรายการหลังจากทำความสะอาด

หลังจากทำการล้างข้อมูล เราจะนับสไตล์และรายการอีกครั้งเพื่อตรวจสอบว่าถูกยุบหรือไม่ ใช้รหัสต่อไปนี้เพื่อแสดงตัวนับใหม่:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

คำแนะนำเหล่านี้แสดงจำนวนสไตล์และรายการที่เหลืออยู่หลังการทำความสะอาด

### ตัวอย่างซอร์สโค้ดสำหรับการล้างข้อมูลสไตล์และรายการที่ไม่ได้ใช้โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// เมื่อรวมกับสไตล์ที่มีอยู่แล้วภายใน เอกสารจะมีแปดสไตล์
	// สไตล์แบบกำหนดเองจะถูกทำเครื่องหมายเป็น "ใช้แล้ว" ขณะที่มีข้อความใดๆ ภายในเอกสาร
	// จัดรูปแบบในลักษณะนั้น ซึ่งหมายความว่า 4 สไตล์ที่เราเพิ่มนั้นยังไม่ได้ใช้
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	// ล้างสไตล์และรายการที่ไม่ได้ใช้ออกจากเอกสาร ขึ้นอยู่กับ CleanupOptions ที่กำหนด
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้ คุณได้เรียนรู้วิธีล้างสไตล์และรายการที่ไม่ได้ใช้จากเอกสารโดยใช้ Aspose.Words สำหรับ .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณจะสามารถใช้คุณสมบัตินี้กับเอกสารของคุณเองได้อย่างง่ายดาย


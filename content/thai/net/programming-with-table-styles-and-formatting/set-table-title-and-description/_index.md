---
title: ตั้งชื่อตารางและคำอธิบาย
linktitle: ตั้งชื่อตารางและคำอธิบาย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งชื่อและคำอธิบายของตารางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-table-styles-and-formatting/set-table-title-and-description/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนในการตั้งชื่อและคำอธิบายของตารางโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีเพิ่มชื่อเรื่องและคำอธิบายลงในตารางในเอกสาร Word ของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือตำแหน่งที่คุณต้องการบันทึกเอกสาร Word ที่แก้ไขแล้ว แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารที่มีตาราง
 ถัดไป คุณจะต้องโหลดเอกสารที่มีตารางโดยใช้`Document` ระดับ. อย่าลืมระบุเส้นทางเอกสารที่ถูกต้อง

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ขั้นตอนที่ 3: เข้าถึงตารางและตั้งชื่อและคำอธิบาย
 ตอนนี้คุณสามารถเข้าถึงตารางในเอกสารโดยใช้`GetChild()` วิธีการและ`Table` ระดับ. จากนั้นตั้งชื่อตารางและคำอธิบายโดยใช้`Title` และ`Description` คุณสมบัติ.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table.Title = "Test Title";
table.Description = "Test Description";
```

## ขั้นตอนที่ 4: ตั้งค่าตัวเลือกการสำรองข้อมูล
 หากคุณต้องการระบุตัวเลือกการบันทึก คุณสามารถกำหนดค่าได้โดยใช้`OoxmlSaveOptions` ระดับ. ในตัวอย่างนี้ เราได้ใช้`Compliance` ตัวเลือกเพื่อระบุการปฏิบัติตามรูปแบบที่เข้มงวด ISO 29500:2008

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };
```

## ขั้นตอนที่ 5: ปรับความเข้ากันได้ของเอกสารให้เหมาะสม
 คุณยังสามารถปรับความเข้ากันได้ของเอกสารให้เหมาะสมโดยใช้`OptimizeFor()` วิธีการของ`CompatibilityOptions` ระดับ. ในตัวอย่างนี้ เราได้ปรับเอกสารให้เหมาะสมสำหรับ Word 2016

```csharp
doc.CompatibilityOptions.OptimizeFor(Aspose.Words.Settings.MsWordVersion.Word2016);
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข
 สุดท้าย คุณสามารถบันทึกเอกสารที่แก้ไขลงในไฟล์ได้โดยใช้นามสกุลไฟล์`Save()` วิธีการของ`Document` ระดับ. อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้อง



```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetTableTitleAndDescription.docx", options);
```

### ตัวอย่างซอร์สโค้ดสำหรับการตั้งชื่อตารางและคำอธิบายโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.Title = "Test title";
	table.Description = "Test description";
	OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };
	doc.CompatibilityOptions.OptimizeFor(Aspose.Words.Settings.MsWordVersion.Word2016);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetTableTitleAndDescription.docx", options);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งชื่อและคำอธิบายของตารางโดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถเพิ่มชื่อและคำอธิบายลงในตารางในเอกสาร Word ของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับจัดการและจัดรูปแบบตารางในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถปรับแต่งโครงสร้างและข้อมูลที่เกี่ยวข้องกับตารางของคุณตามความต้องการเฉพาะของคุณได้
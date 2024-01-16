---
title: สถานะปัจจุบันของกล่องกาเครื่องหมาย
linktitle: สถานะปัจจุบันของกล่องกาเครื่องหมาย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีดึงข้อมูลและตั้งค่าสถานะปัจจุบันของการควบคุมเนื้อหากล่องกาเครื่องหมายในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/current-state-of-check-box/
---

บทช่วยสอนนี้จะอธิบายวิธีการดึงข้อมูลและตั้งค่าสถานะปัจจุบันของการควบคุมเนื้อหากล่องกาเครื่องหมายในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถเลือกหรือยกเลิกการเลือกช่องทำเครื่องหมายตามสถานะปัจจุบันได้

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและดึงข้อมูลการควบคุมเนื้อหาของกล่องกาเครื่องหมาย
 โหลดเอกสาร Word โดยใช้ไฟล์`Document` Constructor โดยส่งเส้นทางไปยังเอกสารเป็นพารามิเตอร์ จากนั้น ดึงข้อมูลการควบคุมเนื้อหากล่องกาเครื่องหมายที่ต้องการจากเอกสาร ในตัวอย่างนี้ เราถือว่ากล่องกาเครื่องหมายเป็นแท็กเอกสารที่มีโครงสร้างแท็กแรกในเอกสาร

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ขั้นตอนที่ 3: ทำเครื่องหมายหรือยกเลิกการทำเครื่องหมายในช่องตามสถานะปัจจุบัน
 ตรวจสอบว่าแท็กเอกสารที่มีโครงสร้างที่ดึงข้อมูลมาเป็นประเภทหรือไม่`SdtType.Checkbox` . หากเป็นเช่นนั้น ให้ตั้งค่า`Checked` คุณสมบัติของการควบคุมเนื้อหาไปที่`true` เพื่อทำเครื่องหมายในช่อง มิฉะนั้น คุณสามารถปล่อยทิ้งไว้โดยไม่เลือกได้

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 บันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save`วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.CurrentStateOfCheckBox.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับสถานะปัจจุบันของกล่องกาเครื่องหมายโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// รับการควบคุมเนื้อหาแรกจากเอกสาร
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

แค่นั้นแหละ! คุณได้ดึงข้อมูลและตั้งค่าสถานะปัจจุบันของการควบคุมเนื้อหากล่องกาเครื่องหมายในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET
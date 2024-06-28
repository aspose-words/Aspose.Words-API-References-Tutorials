---
title: ล้างเนื้อหาการควบคุม
linktitle: ล้างเนื้อหาการควบคุม
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีล้างเนื้อหาของตัวควบคุมในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/clear-contents-control/
---

บทช่วยสอนนี้สาธิตวิธีการล้างเนื้อหาของ SDT ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET การล้างเนื้อหาของ SDT จะลบข้อความหรือโหนดย่อยภายในตัวควบคุมเนื้อหา

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและรับ StructuredDocumentTag
 โหลดเอกสาร Word โดยใช้ไฟล์`Document` Constructor โดยส่งเส้นทางไปยังเอกสารเป็นพารามิเตอร์ จากนั้นจึงดึงสิ่งที่ต้องการกลับมา`StructuredDocumentTag` จากเอกสาร ในตัวอย่างนี้ เราถือว่า SDT เป็นโหนดลูกแรกในเอกสาร

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ขั้นตอนที่ 3: ล้างเนื้อหาของ StructuredDocumentTag
 ล้างเนื้อหาของ SDT โดยใช้`Clear` วิธี. วิธีนี้จะลบข้อความหรือโหนดย่อยภายในตัวควบคุมเนื้อหา

```csharp
sdt.Clear();
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 บันทึกเอกสารที่แก้ไขโดยใช้`Save`วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.ClearContentsControl.doc"

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### ตัวอย่างซอร์สโค้ดสำหรับการควบคุมเนื้อหาที่ชัดเจนโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

แค่นั้นแหละ! คุณได้ล้างเนื้อหาของ StructuredDocumentTag ในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words for .NET
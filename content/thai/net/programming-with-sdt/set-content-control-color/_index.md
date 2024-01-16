---
title: ตั้งค่าสีควบคุมเนื้อหา
linktitle: ตั้งค่าสีควบคุมเนื้อหา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตั้งค่าสีของตัวควบคุมเนื้อหาในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เพื่อปรับแต่งลักษณะที่ปรากฏ
type: docs
weight: 10
url: /th/net/programming-with-sdt/set-content-control-color/
---

บทช่วยสอนนี้จะอธิบายวิธีการตั้งค่าสีของตัวควบคุมเนื้อหาในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถปรับแต่งลักษณะที่ปรากฏของตัวควบคุมเนื้อหาได้โดยการเปลี่ยนสี

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและเรียกข้อมูลการควบคุมเนื้อหา
 โหลดเอกสาร Word โดยใช้ไฟล์`Document` Constructor โดยส่งเส้นทางไปยังเอกสารเป็นพารามิเตอร์ ดึงตัวควบคุมเนื้อหาที่ต้องการจากเอกสาร ในตัวอย่างนี้ เราถือว่าตัวควบคุมเนื้อหาเป็นแท็กเอกสารที่มีโครงสร้างแท็กแรกในเอกสาร

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## ขั้นตอนที่ 3: ตั้งค่าสีควบคุมเนื้อหา
 ตั้งค่าสีของตัวควบคุมเนื้อหาโดยการกำหนด`Color` มูลค่าให้กับ`Color` คุณสมบัติของแท็กเอกสารที่มีโครงสร้าง ในตัวอย่างนี้ เราตั้งค่าสีเป็นสีแดง

```csharp
sdt.Color = Color.Red;
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 บันทึกเอกสารที่แก้ไขไปยังไดเร็กทอรีที่ระบุโดยใช้`Save` วิธี. ระบุชื่อไฟล์ที่ต้องการพร้อมนามสกุลไฟล์ที่เหมาะสม ในตัวอย่างนี้ เราบันทึกเอกสารเป็น "WorkingWithSdt.SetContentControlColor.docx"

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าสีควบคุมเนื้อหาโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

แค่นั้นแหละ! คุณได้ตั้งค่าสีของตัวควบคุมเนื้อหาในเอกสาร Word ของคุณโดยใช้ Aspose.Words for .NET เรียบร้อยแล้ว
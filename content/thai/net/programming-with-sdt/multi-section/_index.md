---
title: หลายส่วน
linktitle: หลายส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีดึงข้อมูลและประมวลผลแท็กเอกสารที่มีโครงสร้างหลายส่วนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-sdt/multi-section/
---

บทช่วยสอนนี้จะอธิบายวิธีการทำงานกับแท็กเอกสารที่มีโครงสร้างหลายส่วนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถดึงข้อมูลและประมวลผลแท็กส่วนที่มีอยู่ในเอกสารได้

## ข้อกำหนดเบื้องต้น
หากต้องการติดตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- ความรู้พื้นฐานเกี่ยวกับ C# และการประมวลผลคำด้วยเอกสาร Word

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
 เริ่มต้นด้วยการตั้งค่าเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารและรับแท็กแบบหลายส่วน
 โหลดเอกสาร Word โดยใช้ไฟล์`Document` Constructor โดยส่งเส้นทางไปยังเอกสารเป็นพารามิเตอร์ ดึงโหนดเริ่มต้นของช่วงแท็กเอกสารที่มีโครงสร้างทั้งหมดในเอกสารโดยใช้`GetChildNodes` วิธี.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## ขั้นตอนที่ 3: ประมวลผลแท็กแบบหลายส่วน
วนซ้ำการรวบรวมโหนดเริ่มต้นของช่วงแท็กเอกสารที่มีโครงสร้าง ในตัวอย่างนี้ เราเพียงพิมพ์ชื่อของแต่ละแท็กไปที่คอนโซล คุณสามารถดำเนินการประมวลผลเพิ่มเติมได้ตามความต้องการของคุณ

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Multi Section โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

แค่นั้นแหละ! คุณได้เรียกและประมวลผลแท็กเอกสารที่มีโครงสร้างหลายส่วนในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET
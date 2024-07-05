---
title: เพิ่มลายน้ำข้อความพร้อมตัวเลือกเฉพาะ
linktitle: เพิ่มลายน้ำข้อความพร้อมตัวเลือกเฉพาะ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มลายน้ำข้อความพร้อมตัวเลือกเฉพาะโดยใช้ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

ในบทช่วยสอนนี้ เราจะอธิบายวิธีการเพิ่มลายน้ำข้อความพร้อมตัวเลือกเฉพาะโดยใช้ Aspose.Words สำหรับ .NET ลายน้ำข้อความคือข้อความที่ซ้อนทับบนเอกสารเพื่อระบุว่าเป็นฉบับร่าง เป็นความลับ ฯลฯ

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

เราจะโหลดเอกสารที่มีอยู่โดยใช้เส้นทางเอกสาร

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## ขั้นตอนที่ 3: เพิ่มลายน้ำข้อความพร้อมตัวเลือกเฉพาะ

 เราจะสร้างอินสแตนซ์ของ`TextWatermarkOptions`และตั้งค่าตัวเลือกที่ต้องการสำหรับลายน้ำข้อความ

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้ายนี้ เราสามารถบันทึกเอกสารด้วยลายน้ำข้อความที่เพิ่มเข้ามาได้

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่มลายน้ำข้อความพร้อมตัวเลือกเฉพาะด้วย Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีเพิ่มลายน้ำข้อความด้วยตัวเลือกเฉพาะโดยใช้ Aspose.Words สำหรับ .NET


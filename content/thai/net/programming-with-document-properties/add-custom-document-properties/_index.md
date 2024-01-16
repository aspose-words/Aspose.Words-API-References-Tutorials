---
title: เพิ่มคุณสมบัติเอกสารแบบกำหนดเอง
linktitle: เพิ่มคุณสมบัติเอกสารแบบกำหนดเอง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการเพิ่มคุณสมบัติแบบกำหนดเองให้กับเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-properties/add-custom-document-properties/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อเพิ่มคุณสมบัติแบบกำหนดเองให้กับเอกสารด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเพิ่มข้อมูลที่กำหนดเองลงในเอกสารได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่เราต้องการเพิ่มคุณสมบัติที่กำหนดเอง ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: เพิ่มคุณสมบัติที่กำหนดเอง

ตอนนี้เรามาเพิ่มคุณสมบัติที่กำหนดเองให้กับเอกสารกันดีกว่า ใช้รหัสต่อไปนี้เพื่อเพิ่มคุณสมบัติ:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

รหัสนี้จะตรวจสอบก่อนว่าคุณสมบัติ "ได้รับอนุญาต" มีอยู่แล้วในคุณสมบัติที่กำหนดเองหรือไม่ หากมีอยู่ กระบวนการจะถูกขัดจังหวะ มิฉะนั้น คุณสมบัติแบบกำหนดเองจะถูกเพิ่มลงในเอกสาร

### ตัวอย่างซอร์สโค้ดสำหรับเพิ่มคุณสมบัติเอกสารแบบกำหนดเองโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีเพิ่มคุณสมบัติแบบกำหนดเองให้กับเอกสารโดยใช้ Aspose.Words สำหรับ .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณสามารถเพิ่มคุณสมบัติที่คุณกำหนดเองลงในเอกสารของคุณได้อย่างง่ายดาย
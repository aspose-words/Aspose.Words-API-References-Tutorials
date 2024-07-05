---
title: แจกแจงคุณสมบัติ
linktitle: แจกแจงคุณสมบัติ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการแจงนับคุณสมบัติของเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-properties/enumerate-properties/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อระบุคุณสมบัติของเอกสารด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณเข้าถึงคุณสมบัติในตัวและแบบกำหนดเองของเอกสารได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่มีคุณสมบัติที่เราต้องการแสดงรายการ ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: การแจงนับคุณสมบัติ

ตอนนี้เรามาแสดงรายการคุณสมบัติของเอกสาร ทั้งคุณสมบัติในตัวและคุณสมบัติแบบกำหนดเอง ใช้รหัสต่อไปนี้:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

รหัสนี้จะแสดงชื่อเอกสาร จากนั้นแสดงรายการคุณสมบัติในตัวและคุณสมบัติแบบกำหนดเองที่แสดงชื่อและค่า

### ตัวอย่างซอร์สโค้ดสำหรับคุณสมบัติแจงนับโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้ คุณได้เรียนรู้วิธีระบุคุณสมบัติเอกสารโดยใช้ Aspose.Words สำหรับ .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณสามารถเข้าถึงและดูคุณสมบัติของเอกสารของคุณเองได้อย่างง่ายดาย


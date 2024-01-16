---
title: รับตัวแปร
linktitle: รับตัวแปร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการดึงข้อมูลตัวแปรเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-properties/get-variables/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อดึงตัวแปรจากเอกสารด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณเข้าถึงตัวแปรที่กำหนดไว้ในเอกสารได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่เราต้องการดึงข้อมูลตัวแปร ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: การดึงตัวแปร

ตอนนี้เราจะดึงข้อมูลตัวแปรที่กำหนดไว้ในเอกสาร ใช้รหัสต่อไปนี้:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

รหัสนี้จะวนซ้ำคู่คีย์-ค่าแต่ละคู่ในตัวแปรเอกสาร และดึงชื่อและค่าของตัวแปรแต่ละตัว จากนั้นนำตัวแปรมาต่อกันเพื่อแสดงข้อมูลของตัวแปรแต่ละตัว

### ตัวอย่างซอร์สโค้ดสำหรับรับตัวแปรโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีดึงตัวแปรจากเอกสารโดยใช้ Aspose.Words สำหรับ .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณจะสามารถเข้าถึงและดูตัวแปรจากเอกสารของคุณเองได้อย่างง่ายดาย
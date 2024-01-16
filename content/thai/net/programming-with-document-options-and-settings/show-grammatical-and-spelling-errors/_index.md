---
title: แสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำ
linktitle: แสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการเปิดใช้งานการแสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำในเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อเปิดใช้งานการแสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณดูข้อผิดพลาดทางไวยากรณ์และการสะกดคำในเอกสารได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่เราต้องการแสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำ ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: เปิดใช้งานการแสดงข้อผิดพลาด

ตอนนี้เราจะเปิดใช้งานการแสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำในเอกสาร ใช้รหัสต่อไปนี้เพื่อเปิดใช้งานการแสดงข้อผิดพลาด:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

รหัสนี้ช่วยให้สามารถแสดงข้อผิดพลาดทางไวยากรณ์ (`ShowGrammaticalErrors`) และการสะกดผิด (`ShowSpellingErrors`) ในเอกสาร

### ตัวอย่างซอร์สโค้ดสำหรับแสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีเปิดใช้งานการแสดงข้อผิดพลาดทางไวยากรณ์และการสะกดคำในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณสามารถเปิดใช้งานคุณสมบัตินี้ในเอกสารของคุณเองได้อย่างง่ายดาย
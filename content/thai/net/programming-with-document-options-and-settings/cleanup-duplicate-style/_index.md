---
title: การล้างข้อมูลรูปแบบที่ซ้ำกัน
linktitle: การล้างข้อมูลรูปแบบที่ซ้ำกัน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนเพื่อล้างสไตล์ที่ซ้ำกันในเอกสารโดยใช้ Aspose.Words สำหรับ .NET รวมซอร์สโค้ดแบบเต็ม
type: docs
weight: 10
url: /th/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# ทีละขั้นตอนเพื่อล้างสไตล์ที่ซ้ำกันด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยลบสไตล์ที่ซ้ำกันออกจากเอกสาร

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่เราต้องการล้างข้อมูล ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: นับสไตล์ก่อนทำความสะอาด

ก่อนดำเนินการทำความสะอาด เราจะนับจำนวนรูปแบบที่มีอยู่ในเอกสาร ใช้รหัสต่อไปนี้เพื่อแสดงจำนวนสไตล์:

```csharp
Console.WriteLine(doc.Styles.Count);
```

คำสั่งนี้แสดงจำนวนสไตล์ที่มีอยู่ในเอกสาร

## ขั้นตอนที่ 4: ทำความสะอาดสไตล์ที่ซ้ำกัน

ตอนนี้เรามาทำความสะอาดสไตล์ที่ซ้ำกันจากเอกสารกันดีกว่า ใช้รหัสต่อไปนี้เพื่อดำเนินการล้างข้อมูล:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 รหัสนี้จะล้างรูปแบบที่ซ้ำกันออกจากเอกสารโดยใช้ตัวเลือกที่ระบุ ในตัวอย่างนี้ เราเปิดใช้งานไฟล์`DuplicateStyle` ตัวเลือกในการล้างสไตล์ที่ซ้ำกัน

## ขั้นตอนที่ 5: นับจำนวนสไตล์หลังจากทำความสะอาด

หลังจากทำความสะอาดแล้วเราจะนับจำนวนแบบอีกครั้งเพื่อดูว่าลดลงหรือไม่ ใช้รหัสต่อไปนี้เพื่อแสดงจำนวนสไตล์ใหม่:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

คำสั่งนี้แสดงจำนวนสไตล์ที่เหลืออยู่หลังการทำความสะอาด

### ตัวอย่างซอร์สโค้ดสำหรับ Cleanup Duplicate Style โดยใช้ Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// จำนวนสไตล์ก่อนการล้างข้อมูล
	Console.WriteLine(doc.Styles.Count);

	// ล้างรูปแบบที่ซ้ำกันออกจากเอกสาร
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	// จำนวนสไตล์หลังจากการล้างข้อมูลลดลง
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```
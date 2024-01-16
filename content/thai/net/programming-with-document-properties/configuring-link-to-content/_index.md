---
title: การกำหนดค่าลิงก์ไปยังเนื้อหา
linktitle: การกำหนดค่าลิงก์ไปยังเนื้อหา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าการลิงก์ไปยังเนื้อหาในเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-properties/configuring-link-to-content/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อตั้งค่าการลิงก์ไปยังเนื้อหาด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเชื่อมโยงไปยังเนื้อหาเฉพาะในเอกสารได้

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: การสร้างเอกสารและตัวสร้าง

ในขั้นตอนนี้ เราจะสร้างเอกสารใหม่และเริ่มต้นตัวสร้าง ใช้รหัสต่อไปนี้:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: สร้างบุ๊กมาร์ก

ตอนนี้เราจะสร้างบุ๊กมาร์กในเอกสาร ใช้รหัสต่อไปนี้เพื่อสร้างบุ๊กมาร์กที่มีข้อความอยู่ข้างใน:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

รหัสนี้สร้างบุ๊กมาร์กชื่อ "MyBookmark" และเพิ่มข้อความบางส่วนไว้ข้างใน

## ขั้นตอนที่ 4: การตั้งค่าลิงก์เนื้อหา

ตอนนี้เราจะกำหนดค่าลิงก์ไปยังเนื้อหาโดยใช้คุณสมบัติเอกสาร ใช้รหัสต่อไปนี้เพื่อเพิ่มและดึงลิงก์ไปยังเนื้อหา:

```csharp
// รับรายการคุณสมบัติแบบกำหนดเองทั้งหมดในเอกสาร
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// เพิ่มคุณสมบัติที่ผูกกับเนื้อหา
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

รหัสนี้จะเพิ่มคุณสมบัติที่เกี่ยวข้องกับเนื้อหาที่เรียกว่า "บุ๊กมาร์ก" พร้อมด้วยบุ๊กมาร์ก "MyBookmark" จากนั้นจะดึงข้อมูลคุณสมบัติที่เกี่ยวข้องกับเนื้อหา เช่น สถานะลิงก์ แหล่งที่มาของลิงก์ และมูลค่าของคุณสมบัติ

### ตัวอย่างซอร์สโค้ดสำหรับการกำหนดค่าลิงก์ไปยังเนื้อหาโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// ดึงรายการคุณสมบัติเอกสารแบบกำหนดเองทั้งหมดจากไฟล์
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// เพิ่มเชื่อมโยงกับคุณสมบัติเนื้อหา
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

ตอนนี้คุณได้เรียนรู้วิธีกำหนดค่าลิงก์ไปยังเนื้อหาในเอกสารโดยใช้ Aspose.Words สำหรับ .NET แล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ คุณสามารถสร้างและกำหนดค่าลิงก์ไปยังเนื้อหาเฉพาะในเอกสารของคุณเองได้อย่างง่ายดาย
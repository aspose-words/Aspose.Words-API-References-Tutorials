---
title: ผสานเอกสาร Word
linktitle: รวมเอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีผสานเอกสาร Word หลายชุดโดยใช้ Aspose.Words สำหรับ .NET API อันทรงพลังนี้ทำให้กระบวนการรวมเอกสารง่ายขึ้น ทำให้มีประสิทธิภาพและตรงไปตรงมา
type: docs
weight: 10
url: /th/net/split-document/merge-documents/
---

ในบทช่วยสอนนี้ เราจะอธิบายวิธีการผสานเอกสาร Word หลายฉบับโดยใช้ฟีเจอร์ผสานเอกสารของ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและรับเอกสารที่ผสานซึ่งมีเอกสารต้นฉบับทั้งหมด

## ขั้นตอนที่ 1: ค้นหาเอกสารที่จะรวม

ก่อนที่จะรวมเอกสาร เราจำเป็นต้องค้นหาเอกสารต้นทางที่จะรวม มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// ค้นหาเอกสารที่จะรวม
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## ขั้นตอนที่ 2: รวมเอกสาร

ตอนนี้เราจะรวมเอกสารทีละฉบับเพื่อสร้างเอกสารที่ผสานกันในขั้นสุดท้าย มีวิธีดังนี้:

```csharp
// เปิดส่วนแรกของเอกสารผลลัพธ์
Document sourceDoc = new Document(sourceDocumentPath);

// สร้างเอกสารผลลัพธ์ใหม่
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// รวมเอกสารทีละรายการ
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับผสานเอกสารโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์ผสานเอกสารของ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
// ค้นหาเอกสารที่ใช้ในการรวม
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// เปิดส่วนแรกของเอกสารผลลัพธ์
Document sourceDoc = new Document(sourceDocumentPath);

// สร้างเอกสารผลลัพธ์ใหม่
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// รวมส่วนเอกสารทีละส่วน
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีผสานเอกสาร Word หลายชุดโดยใช้คุณสมบัติผสานเอกสารของ Aspose.Words สำหรับ .NET เมื่อปฏิบัติตามซอร์สโค้ดที่ให้มา คุณสามารถรวมเอกสารที่แยกจากกันเป็นเอกสารที่ผสานเป็นเอกสารเดียวได้ โดยยังคงรูปแบบของเอกสารต้นฉบับแต่ละฉบับไว้

การรวมเอกสารจะมีประโยชน์เมื่อคุณต้องการรวบรวมข้อมูลจากหลายแหล่ง หรือสร้างเอกสารที่รวมเป็นหนึ่งเดียวจากแต่ละส่วน Aspose.Words สำหรับ .NET มี API อันทรงพลังที่ทำให้กระบวนการรวมเอกสารง่ายขึ้น ทำให้มีประสิทธิภาพและตรงไปตรงมา

สำรวจคุณสมบัติอื่นๆ ที่นำเสนอโดย Aspose.Words สำหรับ .NET ได้ตามสบาย เพื่อปรับปรุงความสามารถในการประมวลผลเอกสารของคุณและปรับปรุงขั้นตอนการทำงานของคุณ

### คำถามที่พบบ่อย

#### ฉันจะรวมเอกสารที่มีรูปแบบต่างกันได้อย่างไร

 เมื่อรวมเอกสาร Aspose.Words สำหรับ .NET มีตัวเลือกในการรักษาการจัดรูปแบบของเอกสารต้นฉบับแต่ละฉบับ โดยใช้`ImportFormatMode.KeepSourceFormatting` ตัวเลือก เอกสารที่ผสานจะคงรูปแบบของเอกสารต้นฉบับไว้ หากคุณต้องการใช้การจัดรูปแบบที่สอดคล้องกันทั่วทั้งเอกสารที่ผสาน คุณสามารถแก้ไขการจัดรูปแบบได้โดยใช้ Aspose.Words API หลังจากผสานเอกสารแล้ว

#### ฉันสามารถรวมเอกสารในรูปแบบต่างๆ ได้หรือไม่

ใช่ Aspose.Words สำหรับ .NET รองรับการรวมเอกสารในรูปแบบต่างๆ รวมถึง DOCX, DOC, RTF และอื่นๆ คุณสามารถโหลดเอกสารที่มีรูปแบบต่างๆ ลงใน Aspose.Words API และรวมเอกสารเหล่านั้นให้เป็นเอกสารเดียวได้ โดยไม่คำนึงถึงรูปแบบดั้งเดิมของเอกสารเหล่านั้น

#### ฉันสามารถรวมเอกสารที่มีโครงสร้างที่ซับซ้อน เช่น ตารางและรูปภาพได้หรือไม่

อย่างแน่นอน! Aspose.Words สำหรับ .NET สามารถรวมเอกสารที่มีโครงสร้างที่ซับซ้อน รวมถึงตาราง รูปภาพ ส่วนหัว ส่วนท้าย และอื่นๆ API จัดการกระบวนการผสานโดยยังคงรักษาความสมบูรณ์และเค้าโครงของเนื้อหาในแต่ละเอกสาร

#### เป็นไปได้หรือไม่ที่จะรวมเอกสารที่มีการวางแนวหน้าหรือขนาดต่างกัน

ใช่ Aspose.Words สำหรับ .NET จัดการเอกสารที่มีการวางแนวหน้าหรือขนาดต่างกันในระหว่างกระบวนการรวม เอกสารที่ผสานที่ได้จะรองรับการวางแนวหน้าและขนาดของเอกสารต้นฉบับที่แตกต่างกัน
---
title: สร้างบุ๊กมาร์กในเอกสาร Word
linktitle: สร้างบุ๊กมาร์กในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างบุ๊กมาร์กในเอกสาร Word และระบุระดับการแสดงตัวอย่างบุ๊กมาร์กใน PDF โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/create-bookmark/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชันสร้างบุ๊กมาร์กในไลบรารี Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสร้างบุ๊กมาร์กในเอกสารและระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในไฟล์ PDF เอาท์พุต

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: การสร้างเอกสารและเครื่องมือสร้าง

 ก่อนที่จะสร้างบุ๊กมาร์ก เราจำเป็นต้องสร้างเอกสารและเครื่องมือสร้างเอกสารโดยใช้`Document` และ`DocumentBuilder` วัตถุ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การสร้างบุ๊กมาร์กหลัก

 เราใช้`StartBookmark` วิธีการเริ่มบุ๊กมาร์กหลักและ`EndBookmark` วิธีการยุติมัน ในระหว่างนี้ เราสามารถเพิ่มข้อความและบุ๊กมาร์กอื่นๆ ได้:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// เพิ่มบุ๊กมาร์กหรือข้อความเพิ่มเติมที่นี่

builder. EndBookmark("My Bookmark");
```

## ขั้นตอนที่ 3: การสร้างบุ๊กมาร์กที่ซ้อนกัน

 นอกจากนี้เรายังสามารถสร้างบุ๊กมาร์กแบบซ้อนภายในบุ๊กมาร์กหลักได้ เราก็ใช้เหมือนกัน`StartBookmark` และ`EndBookmark` วิธีสร้างและสิ้นสุดบุ๊กมาร์กที่ซ้อนกัน:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## ขั้นตอนที่ 4: การระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในไฟล์ PDF เอาท์พุต

 เราใช้`PdfSaveOptions` วัตถุเพื่อระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในไฟล์ PDF เอาต์พุต เราใช้`BookmarksOutlineLevels` คุณสมบัติ

  เพื่อเพิ่มบุ๊กมาร์กหลักและบุ๊กมาร์กแบบซ้อนตามระดับที่เกี่ยวข้อง:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### ตัวอย่างซอร์สโค้ดสำหรับสร้างบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการสร้างบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟังก์ชันสร้างบุ๊กมาร์กของ Aspose.Words สำหรับ .NET เราได้ปฏิบัติตามคำแนะนำทีละขั้นตอนในการสร้างบุ๊กมาร์กในเอกสารและระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในไฟล์ PDF เอาท์พุต

### คำถามที่พบบ่อย

#### ถาม: ข้อกำหนดเบื้องต้นในการใช้ฟังก์ชัน "สร้างบุ๊กมาร์ก" ใน Aspose.Words สำหรับ .NET มีอะไรบ้าง

ตอบ: หากต้องการใช้ฟังก์ชัน "สร้างบุ๊กมาร์ก" ใน Aspose.Words สำหรับ .NET คุณต้องมีความรู้พื้นฐานเกี่ยวกับภาษา C# คุณต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words ด้วย

#### ถาม: จะสร้างเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างเอกสารใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Document` ชั้นเรียน นี่คือโค้ดตัวอย่าง:

```csharp
Document doc = new Document();
```

#### ถาม: จะสร้างบุ๊กมาร์กหลักในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างบุ๊กมาร์กหลักในเอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`StartBookmark` วิธีการเริ่มบุ๊กมาร์ก เพิ่มข้อความหรือบุ๊กมาร์กอื่นๆ ภายใน จากนั้นใช้` EndBookmark` เพื่อยุติมัน นี่คือโค้ดตัวอย่าง:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### ถาม: จะสร้างบุ๊กมาร์กแบบซ้อนภายในบุ๊กมาร์กหลักโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างบุ๊กมาร์กแบบซ้อนภายในบุ๊กมาร์กหลักโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้สิ่งเดียวกันได้`StartBookmark` และ`EndBookmark` วิธีการเริ่มต้นและสิ้นสุดบุ๊กมาร์กที่ซ้อนกัน นี่คือโค้ดตัวอย่าง:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### ถาม: จะระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในเอาต์พุต PDF โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในเอาต์พุต PDF โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้`PdfSaveOptions` ชั้นเรียนและ`BookmarksOutlineLevels` คุณสมบัติ. คุณสามารถเพิ่มบุ๊กมาร์กหลักและบุ๊กมาร์กแบบซ้อนตามระดับที่เกี่ยวข้องได้ นี่คือโค้ดตัวอย่าง:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### ถาม: จะบันทึกเอกสารได้อย่างไรหลังจากสร้างบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET

 ตอบ: หากต้องการบันทึกเอกสารหลังจากสร้างบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Save` วิธีการของ`Document` วัตถุที่ระบุเส้นทางไฟล์ปลายทาง นี่คือโค้ดตัวอย่าง:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### ถาม: จะระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในเอาต์พุต PDF โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการระบุระดับการแสดงตัวอย่างบุ๊กมาร์กในเอาต์พุต PDF โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้`PdfSaveOptions` ชั้นเรียนและ`BookmarksOutlineLevels` คุณสมบัติ. คุณสามารถเพิ่มบุ๊กมาร์กหลักและบุ๊กมาร์กแบบซ้อนตามระดับที่เกี่ยวข้องได้ นี่คือโค้ดตัวอย่าง:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### ถาม: จะสร้างบุ๊กมาร์กแบบซ้อนภายในบุ๊กมาร์กหลักโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างบุ๊กมาร์กที่ซ้อนกันภายในบุ๊กมาร์กหลักโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้สิ่งเดียวกันได้`StartBookmark` และ`EndBookmark` วิธีการเริ่มต้นและสิ้นสุดบุ๊กมาร์กที่ซ้อนกัน อย่าลืมระบุบุ๊กมาร์กหลักเป็นพารามิเตอร์เมื่อเรียกใช้`StartBookmark` วิธี. นี่คือโค้ดตัวอย่าง:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### ถาม: จะเพิ่มข้อความในบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเพิ่มข้อความภายในบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Write` วิธีการของ`DocumentBuilder`วัตถุที่ระบุข้อความที่จะเพิ่ม นี่คือโค้ดตัวอย่าง:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### ถาม: จะสร้างบุ๊กมาร์กหลักในเอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างบุ๊กมาร์กหลักในเอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`StartBookmark` วิธีการเริ่มบุ๊กมาร์กและ`EndBookmark` วิธีการยุติมัน นี่คือโค้ดตัวอย่าง:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```
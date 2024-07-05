---
title: คัดลอกข้อความที่คั่นหน้าในเอกสาร Word
linktitle: คัดลอกข้อความที่คั่นหน้าในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีคัดลอกข้อความบุ๊กมาร์กในเอกสาร Word ไปยังเอกสารอื่นโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/copy-bookmarked-text/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชันคัดลอกข้อความที่คั่นหน้าในไลบรารี Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถคัดลอกเนื้อหาของบุ๊กมาร์กเฉพาะจากเอกสารต้นทางไปยังเอกสารอื่นได้

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: กำลังโหลดเอกสารต้นฉบับ

 ก่อนที่จะคัดลอกข้อความบุ๊กมาร์ก เราต้องโหลดเอกสารต้นฉบับลงในไฟล์`Document` วัตถุที่ใช้เส้นทางไฟล์:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## ขั้นตอนที่ 2: รับบุ๊กมาร์กแหล่งที่มา

 เราใช้`Bookmarks` คุณสมบัติของช่วงเอกสารต้นทางเพื่อรับบุ๊กมาร์กเฉพาะที่เราต้องการคัดลอก:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## ขั้นตอนที่ 3: การสร้างเอกสารปลายทาง

เราสร้างเอกสารใหม่ที่จะทำหน้าที่เป็นเอกสารปลายทางเพื่อคัดลอกเนื้อหาบุ๊กมาร์ก:

```csharp
Document dstDoc = new Document();
```

## ขั้นตอนที่ 4: การระบุตำแหน่งการทำสำเนา

เราระบุตำแหน่งที่เราต้องการเพิ่มข้อความที่คัดลอก ในตัวอย่างของเรา เราเพิ่มข้อความที่ส่วนท้ายของส่วนสุดท้ายของเอกสารปลายทาง:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## ขั้นตอนที่ 5: นำเข้าและคัดลอกข้อความบุ๊กมาร์ก

 เราใช้ก`NodeImporter`วัตถุที่จะนำเข้าและคัดลอกข้อความบุ๊กมาร์กจากเอกสารต้นทางไปยังเอกสารปลายทาง:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการคัดลอกข้อความที่คั่นหน้าโดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการคัดลอกข้อความจากบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// นี่คือบุ๊กมาร์กที่มีเนื้อหาที่เราต้องการคัดลอก
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// เราจะเพิ่มเอกสารนี้
	Document dstDoc = new Document();

	// สมมติว่าเราจะนำไปต่อท้ายเนื้อหาของส่วนสุดท้าย
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// หากคุณนำเข้าหลายครั้งโดยไม่มีบริบทเดียว จะส่งผลให้มีการสร้างสไตล์มากมาย
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### ผนวกซอร์สโค้ดข้อความที่คั่นหน้า

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // นี่คือย่อหน้าที่มีจุดเริ่มต้นของบุ๊กมาร์ก
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // นี่คือย่อหน้าที่มีส่วนท้ายของบุ๊กมาร์ก
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // จำกัดตัวเราเองให้อยู่ในสถานการณ์ที่เรียบง่ายพอสมควร
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // เราต้องการคัดลอกย่อหน้าทั้งหมดตั้งแต่ย่อหน้าเริ่มต้นจนถึง (และรวมถึง) ย่อหน้าสุดท้าย
            // ดังนั้นโหนดที่เราหยุดจะอยู่หลังย่อหน้าสุดท้าย
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //สิ่งนี้จะสร้างสำเนาของโหนดปัจจุบันและนำเข้า (ทำให้ถูกต้อง) ในบริบท
                // ของเอกสารปลายทาง การนำเข้าหมายถึงการปรับสไตล์และตัวระบุรายการอย่างถูกต้อง
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟังก์ชันคัดลอกข้อความที่คั่นหน้าจาก Aspose.Words สำหรับ .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่อคัดลอกเนื้อหาของบุ๊กมาร์กจากเอกสารต้นทางไปยังเอกสารอื่น

### คำถามที่พบบ่อยสำหรับการคัดลอกข้อความที่คั่นหน้าในเอกสาร Word

#### ถาม: ข้อกำหนดในการใช้ฟีเจอร์ "คัดลอกข้อความพร้อมบุ๊กมาร์ก" ใน Aspose.Words สำหรับ .NET มีอะไรบ้าง

ตอบ: หากต้องการใช้ฟีเจอร์ "คัดลอกข้อความพร้อมบุ๊กมาร์ก" ใน Aspose.Words สำหรับ .NET คุณต้องมีความรู้พื้นฐานเกี่ยวกับภาษา C# คุณต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words ด้วย

#### ถาม: ฉันจะโหลดเอกสารต้นฉบับลงใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการโหลดเอกสารต้นฉบับใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Document` คลาสโดยระบุเส้นทางไฟล์ของเอกสาร นี่คือโค้ดตัวอย่าง:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### ถาม: จะรับเนื้อหาของบุ๊กมาร์กเฉพาะในเอกสารต้นฉบับโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการรับเนื้อหาของบุ๊กมาร์กเฉพาะในเอกสารต้นทางโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถเข้าถึง`Bookmarks` คุณสมบัติของช่วงเอกสารต้นทางและใช้ชื่อบุ๊กมาร์กเพื่อเรียกข้อมูลบุ๊กมาร์กเฉพาะ นี่คือโค้ดตัวอย่าง:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### ถาม: จะระบุตำแหน่งของสำเนาข้อความบุ๊กมาร์กในเอกสารปลายทางโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการระบุตำแหน่งที่คุณต้องการเพิ่มข้อความบุ๊กมาร์กที่คัดลอกไว้ในเอกสารปลายทางโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถนำทางไปยังเนื้อหาของส่วนสุดท้ายของเอกสารปลายทางได้ คุณสามารถใช้`LastSection` คุณสมบัติในการเข้าถึงส่วนสุดท้ายและ`Body` คุณสมบัติในการเข้าถึงเนื้อหาของส่วนนั้น นี่คือโค้ดตัวอย่าง:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### ถาม: จะนำเข้าและคัดลอกข้อความบุ๊กมาร์กจากเอกสารต้นทางไปยังเอกสารปลายทางโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการนำเข้าและคัดลอกข้อความบุ๊กมาร์กจากเอกสารต้นทางไปยังเอกสารปลายทางโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้`NodeImporter` คลาสที่ระบุเอกสารต้นทาง เอกสารปลายทาง และโหมดการจัดรูปแบบที่จะเก็บไว้ จากนั้นคุณสามารถใช้`AppendBookmarkedText` วิธีการเพิ่มข้อความบุ๊กมาร์กในเอกสารปลายทาง นี่คือโค้ดตัวอย่าง:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### ถาม: จะบันทึกเอกสารปลายทางได้อย่างไรหลังจากคัดลอกข้อความบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET

ตอบ: หากต้องการบันทึกเอกสารปลายทางหลังจากคัดลอกข้อความจากบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้`Save` วิธีการของ`Document` วัตถุที่ระบุเส้นทางไฟล์ปลายทาง นี่คือโค้ดตัวอย่าง:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```
---
title: ผนวกข้อความที่คั่นหน้าไว้ในเอกสาร Word
linktitle: ผนวกข้อความที่คั่นหน้าไว้ในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเพิ่มข้อความจากบุ๊กมาร์กในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/append-bookmarked-text/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชันผนวกข้อความที่คั่นหน้าใน Aspose.Words สำหรับไลบรารี .NET คุณลักษณะนี้ช่วยให้คุณสามารถเพิ่มข้อความที่อยู่ในบุ๊กมาร์กเฉพาะของเอกสาร Word ลงในเอกสารอื่นได้

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: รับย่อหน้าจากบุ๊กมาร์ก

 ก่อนที่เราจะเริ่มเพิ่มข้อความบุ๊กมาร์ก เราจำเป็นต้องได้รับย่อหน้าที่มีจุดเริ่มต้นและจุดสิ้นสุดของบุ๊กมาร์ก ซึ่งสามารถทำได้โดยการเข้าถึง`BookmarkStart` และ`BookmarkEnd` คุณสมบัติของบุ๊กมาร์ก:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## ขั้นตอนที่ 2: ตรวจสอบย่อหน้าหลัก

เราตรวจสอบว่าย่อหน้าเริ่มต้นและสิ้นสุดมีพาเรนต์ที่ถูกต้องหรือไม่ กล่าวคือ ย่อหน้าเหล่านั้นอยู่ในย่อหน้าจริงหรือไม่ ถ้าไม่เช่นนั้น เราจะสร้างข้อยกเว้น:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## ขั้นตอนที่ 3: ตรวจสอบผู้ปกครองของย่อหน้า

เราตรวจสอบว่าย่อหน้าเริ่มต้นและสิ้นสุดมีพาเรนต์เดียวกันหรือไม่ หากไม่เป็นเช่นนั้น แสดงว่าย่อหน้าไม่อยู่ในส่วนหรือเอกสารเดียวกัน และเรามีข้อยกเว้น:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## ขั้นตอนที่ 4: คัดลอกย่อหน้า

เราวนซ้ำโหนด (ย่อหน้า) จากย่อหน้าเริ่มต้นไปยังย่อหน้าสุดท้าย สำหรับแต่ละโหนด เราจะสร้างสำเนาและนำเข้าไปยังบริบทของเอกสารปลายทาง:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### ตัวอย่างซอร์สโค้ดสำหรับผนวกข้อความที่คั่นหน้าโดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการเพิ่มข้อความจากบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

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

```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Append Bookmarked Text ของ Aspose.Words สำหรับ .NET เราได้ปฏิบัติตามคำแนะนำทีละขั้นตอนในการรับย่อหน้าจากบุ๊กมาร์ก การตรวจสอบผู้ปกครอง และการคัดลอกย่อหน้าไปยังเอกสารอื่น

### คำถามที่พบบ่อยสำหรับการต่อท้ายข้อความที่คั่นหน้าในเอกสาร word

#### คำถามที่ 1: ข้อกำหนดเบื้องต้นในการใช้ฟีเจอร์ "เพิ่มข้อความด้วยบุ๊กมาร์ก" ใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: หากต้องการใช้ฟังก์ชัน "เพิ่มข้อความด้วยบุ๊กมาร์ก" ใน Aspose.Words สำหรับ .NET คุณต้องมีความรู้พื้นฐานเกี่ยวกับภาษา C# คุณต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words ด้วย

#### คำถามที่ 2: วิธีรับย่อหน้าที่มีจุดเริ่มต้นและจุดสิ้นสุดของบุ๊กมาร์กในเอกสาร Word

ตอบ: หากต้องการรับย่อหน้าที่มีจุดเริ่มต้นและจุดสิ้นสุดของบุ๊กมาร์กในเอกสาร Word คุณสามารถเข้าถึงได้`BookmarkStart` และ`BookmarkEnd` คุณสมบัติของบุ๊กมาร์ก นี่คือโค้ดตัวอย่าง:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: จะเกิดอะไรขึ้นถ้าย่อหน้าเริ่มต้นและสิ้นสุดไม่มีพาเรนต์ที่ถูกต้อง

ตอบ: หากย่อหน้าเริ่มต้นและสิ้นสุดไม่มีพาเรนต์ที่ถูกต้อง กล่าวคือ ไม่ใช่ย่อหน้าจริงๆ ข้อยกเว้นจะเกิดขึ้น ไม่สามารถจัดการสถานการณ์นี้ได้ในขณะนี้

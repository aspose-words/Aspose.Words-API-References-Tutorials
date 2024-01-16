---
title: แสดงซ่อนเนื้อหาที่คั่นหน้าในเอกสาร Word
linktitle: แสดงซ่อนเนื้อหาที่คั่นหน้าในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแสดงหรือซ่อนเนื้อหาที่คั่นหน้าในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชันแสดงซ่อนเนื้อหาที่คั่นหน้าใน Aspose.Words สำหรับไลบรารี .NET คุณลักษณะนี้ช่วยให้คุณสามารถแสดงหรือซ่อนเนื้อหาของบุ๊กมาร์กในเอกสาร Word ตามเงื่อนไขเฉพาะเมื่อรวมข้อมูล

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: รับบุ๊กมาร์ก

 เราใช้`Bookmarks` คุณสมบัติของช่วงเอกสารเพื่อรับบุ๊กมาร์กเฉพาะที่เราต้องการแสดงหรือซ่อนเนื้อหา:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## ขั้นตอนที่ 2: การแทรกเขตข้อมูลผสาน

 เราใช้เครื่องมือสร้างเอกสาร`DocumentBuilder` เพื่อแทรกช่องผสานที่จำเป็น ช่องผสานเหล่านี้จะกำหนดเงื่อนไขให้แสดงหรือซ่อนเนื้อหาบุ๊กมาร์กโดยขึ้นอยู่กับค่าของ`showHide` ตัวแปร:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## ขั้นตอนที่ 3: การย้ายเนื้อหาบุ๊กมาร์ก

เราวนซ้ำเนื้อหาของบุ๊กมาร์กแล้วย้ายเพื่อให้ปรากฏ

ปัญหาก่อนบุ๊กมาร์ก วิธีนี้จะควบคุมการแสดงหรือซ่อนเนื้อหาตามเงื่อนไขที่ระบุ:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## ขั้นตอนที่ 4: การย้ายเนื้อหาบุ๊กมาร์กที่เหลือ

เราย้ายเนื้อหาบุ๊กมาร์กที่เหลือไปหลังบุ๊กมาร์ก โดยใช้จุดสิ้นสุดของบุ๊กมาร์กเป็นจุดแทรก:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## ขั้นตอนที่ 5: ดำเนินการผสาน

 เราใช้`Execute` วิธีการจัดทำเอกสาร`s `จดหมายเวียน` object to execute the merge using the bookmark name and the value of the `ตัวแปร showHide`:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### ตัวอย่างซอร์สโค้ดสำหรับแสดงซ่อนเนื้อหาที่คั่นหน้าโดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างแบบเต็มของซอร์สโค้ดเพื่อแสดงหรือซ่อนเนื้อหาบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟีเจอร์แสดงซ่อนเนื้อหาที่คั่นหน้าของ Aspose.Words สำหรับ .NET เราได้ปฏิบัติตามคำแนะนำทีละขั้นตอนเพื่อแสดงหรือซ่อนเนื้อหาของบุ๊กมาร์กตามเงื่อนไขเฉพาะเมื่อรวมข้อมูล

### คำถามที่พบบ่อยสำหรับการแสดงซ่อนเนื้อหาที่คั่นหน้าในเอกสาร Word

#### ถาม: ฉันสามารถใช้เงื่อนไขเดียวกันสำหรับบุ๊กมาร์กหลายรายการในเอกสารเดียวกันได้หรือไม่

ตอบ: ได้ คุณสามารถใช้เงื่อนไขเดียวกันสำหรับบุ๊กมาร์กหลายรายการในเอกสารเดียวกันได้ เพียงทำซ้ำขั้นตอนที่ 2-5 สำหรับแต่ละบุ๊กมาร์ก โดยปรับชื่อบุ๊กมาร์กและเลือกค่าของ`showhide` ตัวแปรได้ตามต้องการ

#### ถาม: ฉันจะเพิ่มเงื่อนไขเพื่อแสดงหรือซ่อนเนื้อหาบุ๊กมาร์กได้อย่างไร

 ตอบ: หากต้องการเพิ่มเงื่อนไข คุณสามารถใช้ตัวดำเนินการเชิงตรรกะ เช่น`AND` และ`OR` ในโค้ดสำหรับแทรกเขตข้อมูลผสานในขั้นตอนที่ 2 แก้ไขเงื่อนไขในโค้ดต่อไปนี้เพื่อเพิ่มเงื่อนไขเพิ่มเติม:

```csharp
builder. Write("\" = \"true\" ");
```

#### ถาม: ฉันจะลบบุ๊กมาร์กในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

 ตอบ: หากต้องการลบบุ๊กมาร์กในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Remove` วิธีการจาก`Bookmarks` การรวบรวมช่วงเอกสาร นี่คือโค้ดตัวอย่างสำหรับการลบบุ๊กมาร์กเฉพาะ:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### ถาม: ไลบรารี Aspose.Words ฟรีหรือไม่

 ตอบ: ไลบรารี Aspose.Words เป็นไลบรารีเชิงพาณิชย์และจำเป็นต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ในโครงการของคุณ คุณสามารถตรวจสอบได้[Aspose.Words สำหรับการอ้างอิง .NET API](https://reference.aspose.com/words/net/) เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับตัวเลือกใบอนุญาตและราคา

#### ถาม: มีไลบรารีอื่นสำหรับการประมวลผลคำด้วยเอกสาร Word ใน .NET หรือไม่

ตอบ: ใช่ ยังมีไลบรารีอื่นๆ สำหรับการประมวลผลคำด้วยเอกสาร Word ใน .NET เช่น Open XML SDK และ GemBox.Document คุณสามารถสำรวจไลบรารีเหล่านี้เป็นทางเลือกแทน Aspose.Words ได้ตามความต้องการและความชอบเฉพาะของคุณ
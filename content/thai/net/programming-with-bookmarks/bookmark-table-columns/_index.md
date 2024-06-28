---
title: คั่นคอลัมน์ตารางในเอกสาร Word
linktitle: คั่นคอลัมน์ตารางในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีบุ๊กมาร์กคอลัมน์ตารางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/bookmark-table-columns/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Bookmark Table Columns ในไลบรารี Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถบุ๊กมาร์กคอลัมน์เฉพาะของตารางในเอกสาร Word และเข้าถึงเนื้อหาของคอลัมน์นั้นได้

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: การสร้างตาราง

 ก่อนที่จะสร้างบุ๊กมาร์กบนคอลัมน์ของตาราง เราต้องสร้างตารางก่อนโดยใช้ a`DocumentBuilder`วัตถุ วัตถุ ในตัวอย่างของเรา เราสร้างตารางที่มีสองแถวและสองคอลัมน์:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## ขั้นตอนที่ 2: สร้างบุ๊กมาร์กคอลัมน์

 เราใช้`StartBookmark` วิธีสร้างบุ๊กมาร์กบนคอลัมน์เฉพาะของตาราง ในตัวอย่างของเรา เราใช้ชื่อ "MyBookmark" สำหรับบุ๊กมาร์ก:

```csharp
builder. StartBookmark("MyBookmark");
```

## ขั้นตอนที่ 3: เข้าถึงเนื้อหาคอลัมน์

 เราอ่านบุ๊กมาร์กทั้งหมดในเอกสารและแสดงชื่อ หากบุ๊กมาร์กเป็นคอลัมน์ เราจะเข้าถึงเนื้อหาของคอลัมน์นั้นโดยใช้ดัชนีคอลัมน์และ`GetText` วิธี:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### ตัวอย่างซอร์สโค้ดสำหรับคอลัมน์ตารางบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการสร้างบุ๊กมาร์กบนคอลัมน์ตารางโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Bookmark Table Columns ของ Aspose.Words สำหรับ .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่อบุ๊กมาร์กคอลัมน์เฉพาะของตารางในเอกสาร Word และข้ามไปยังเนื้อหาของคอลัมน์นั้น

### คำถามที่พบบ่อยสำหรับคอลัมน์ตารางบุ๊กมาร์กในเอกสาร Word

#### ถาม: ข้อกำหนดเบื้องต้นในการใช้ฟีเจอร์ “บุ๊กมาร์กสำหรับคอลัมน์ตาราง” ใน Aspose.Words สำหรับ .NET มีอะไรบ้าง

ตอบ: หากต้องการใช้ฟีเจอร์ “บุ๊กมาร์กสำหรับคอลัมน์ตาราง” ใน Aspose.Words สำหรับ .NET คุณต้องมีความรู้พื้นฐานเกี่ยวกับภาษา C# คุณต้องมีสภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words ด้วย

#### ถาม: จะสร้างตารางที่มีคอลัมน์ในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างตารางที่มีคอลัมน์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้`DocumentBuilder` วัตถุเพื่อแทรกเซลล์และเนื้อหาลงในตาราง นี่คือโค้ดตัวอย่าง:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### ถาม: จะบุ๊กมาร์กคอลัมน์ตารางโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการสร้างบุ๊กมาร์กบนคอลัมน์ตารางโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`StartBookmark` วิธีการของ`DocumentBuilder` วัตถุเพื่อเริ่มบุ๊กมาร์กในคอลัมน์ตารางเฉพาะ นี่คือโค้ดตัวอย่าง:

```csharp
builder.StartBookmark("MyBookmark");
```

#### ถาม: จะเข้าถึงเนื้อหาคอลัมน์ตารางจากบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการเข้าถึงเนื้อหาของคอลัมน์ตารางจากบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถวนซ้ำบุ๊กมาร์กทั้งหมดในเอกสาร ตรวจสอบว่าบุ๊กมาร์กเป็นคอลัมน์หรือไม่ และใช้ดัชนีของคอลัมน์เพื่อเข้าถึงเนื้อหาของ คอลัมน์นั้น นี่คือโค้ดตัวอย่าง:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // ทำบางสิ่งกับเนื้อหาของคอลัมน์...
         }
     }
}
```

#### ถาม: มีการจำกัดจำนวนคอลัมน์ที่ฉันสามารถสร้างในตารางที่มีบุ๊กมาร์กคอลัมน์ได้หรือไม่

ตอบ: ไม่มีการจำกัดจำนวนคอลัมน์ที่คุณสามารถสร้างในตารางที่มีบุ๊กมาร์กคอลัมน์โดยใช้ Aspose.Words สำหรับ .NET ขีดจำกัดจะขึ้นอยู่กับทรัพยากรที่มีอยู่ในระบบของคุณและข้อกำหนดเฉพาะของรูปแบบไฟล์ Word ที่คุณใช้เป็นหลัก อย่างไรก็ตาม ขอแนะนำว่าอย่าสร้างคอลัมน์จำนวนมากเกินไป เนื่องจากอาจส่งผลต่อประสิทธิภาพและความสามารถในการอ่านของเอกสารขั้นสุดท้ายได้
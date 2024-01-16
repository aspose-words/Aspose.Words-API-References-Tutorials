---
title: แก้ให้หายยุ่งในเอกสาร Word
linktitle: แก้ให้หายยุ่งในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแก้ให้หายยุ่งในเอกสาร word ที่คั่นหน้าซ้อนกันในแถวตารางที่อยู่ติดกันโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/untangle/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Untangle ในไลบรารี Aspose.Words สำหรับ .NET ฟังก์ชันนี้จะคลี่บุ๊กมาร์กที่ซ้อนกันซึ่งอยู่ในแถวตารางที่อยู่ติดกัน

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: เรียกดูบุ๊กมาร์กเอกสาร

เราใช้ foreach loop เพื่อวนซ้ำบุ๊กมาร์กทั้งหมดที่มีอยู่ในเอกสาร:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // รหัสสำหรับจัดการบุ๊กมาร์กที่นี่
}
```

## ขั้นตอนที่ 2: รับแถวพาเรนต์จากบุ๊กมาร์ก

 เราใช้`GetAncestor` วิธีการดึงข้อมูลแถวพาเรนต์ของโหนดเริ่มต้นและจุดสิ้นสุดของบุ๊กมาร์ก:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## ขั้นตอนที่ 3: แก้ให้หายยุ่งที่คั่นหน้าซ้อนกัน

หากพบทั้งสองบรรทัดหลักและบุ๊กมาร์กเริ่มต้นและสิ้นสุดในบรรทัดที่อยู่ติดกัน เราจะย้ายโหนดสิ้นสุดของบุ๊กมาร์กไปที่จุดสิ้นสุดของย่อหน้าสุดท้ายของเซลล์สุดท้ายในแถวบนสุด:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### ตัวอย่างซอร์สโค้ดสำหรับแก้ให้หายยุ่งโดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มสำหรับการแกะบุ๊กมาร์กที่ซ้อนกันโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// รับแถวพาเรนต์ของทั้งบุ๊กมาร์กและโหนดสิ้นสุดบุ๊กมาร์ก
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// หากพบว่าทั้งสองแถวไม่เป็นไร และบุ๊กมาร์กเริ่มต้นและสิ้นสุดอยู่ในแถวที่อยู่ติดกัน
		// ย้ายโหนดสิ้นสุดบุ๊กมาร์กไปยังจุดสิ้นสุดของย่อหน้าสุดท้ายในเซลล์สุดท้ายของแถวบนสุด
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Untangle ของ Aspose.Words สำหรับ .NET เราได้ปฏิบัติตามคำแนะนำทีละขั้นตอนเพื่อแก้ปัญหาบุ๊กมาร์กที่ซ้อนกันในแถวตารางที่อยู่ติดกัน

### คำถามที่พบบ่อย

#### ถาม: ฟังก์ชัน Untangle ใช้งานได้เฉพาะกับบุ๊กมาร์กที่ซ้อนกันในแถวตารางที่อยู่ติดกันหรือไม่

ตอบ: ได้ คุณสมบัติแก้ให้หายยุ่งได้รับการออกแบบมาโดยเฉพาะเพื่อแก้ให้หายยุ่งบุ๊กมาร์กที่ซ้อนกันซึ่งอยู่ในแถวตารางที่อยู่ติดกัน หากบุ๊กมาร์กไม่อยู่ในบรรทัดที่อยู่ติดกัน ฟังก์ชันนี้จะใช้งานไม่ได้

#### ถาม: ฉันจะระบุบุ๊กมาร์กที่ซ้อนกันในเอกสาร Word ได้อย่างไร

ตอบ: คุณสามารถระบุบุ๊กมาร์กที่ซ้อนกันได้โดยการวนซ้ำบุ๊กมาร์กในเอกสาร และตรวจสอบเพื่อดูว่าบุ๊กมาร์กเริ่มต้นและบุ๊กมาร์กสิ้นสุดอยู่ในแถวของตารางที่อยู่ติดกันหรือไม่ คุณสามารถใช้ซอร์สโค้ดที่ให้ไว้ในบทความนี้เป็นจุดเริ่มต้นในการใช้งานฟังก์ชันนี้

#### ถาม: ฟังก์ชัน Unscramble จะแก้ไขเนื้อหาของเอกสารต้นฉบับหรือไม่

ตอบ: ได้ ฟังก์ชัน Untangle จะแก้ไขเอกสารต้นฉบับโดยการย้ายโหนดสิ้นสุดของบุ๊กมาร์กไปที่จุดสิ้นสุดของย่อหน้าสุดท้ายของเซลล์สุดท้ายในแถวบนสุด ตรวจสอบให้แน่ใจว่าได้บันทึกสำเนาสำรองของเอกสารก่อนที่จะใช้คุณสมบัตินี้

#### ถาม: ฉันจะแยกบุ๊กมาร์กที่ซ้อนกันในองค์ประกอบเอกสารประเภทอื่นๆ เช่น ส่วนหรือย่อหน้าออกได้อย่างไร

ตอบ: ฟังก์ชัน Untangle ที่นำเสนอในบทความนี้ได้รับการออกแบบมาโดยเฉพาะเพื่อแก้ให้หายยุ่งบุ๊กมาร์กที่ซ้อนกันในแถวตารางที่อยู่ติดกัน หากคุณต้องการแยกบุ๊กมาร์กที่ซ้อนกันในองค์ประกอบเอกสารอื่นๆ คุณจะต้องปรับโค้ดให้เหมาะสมและใช้วิธีการที่เหมาะสมเพื่อเข้าถึงองค์ประกอบที่ต้องการ

#### ถาม: มีวิธีอื่นใดในการแก้ให้หายยุ่งบุ๊กมาร์กที่ซ้อนกันในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET หรือไม่

 ตอบ: วิธีการที่นำเสนอในบทความนี้เป็นวิธีการทั่วไปในการคลี่บุ๊กมาร์กที่ซ้อนกันในแถวตารางที่อยู่ติดกัน อย่างไรก็ตาม อาจมีแนวทางหรือเทคนิคอื่นๆ ขึ้นอยู่กับความต้องการเฉพาะของโครงการของคุณ คุณสามารถตรวจสอบได้ที่[Aspose.Words สำหรับการอ้างอิง .NET API](https://reference.aspose.com/words/net/) เพื่อสำรวจคุณสมบัติที่มีอยู่เพิ่มเติม
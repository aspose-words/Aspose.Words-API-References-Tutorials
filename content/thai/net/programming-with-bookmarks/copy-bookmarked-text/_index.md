---
title: คัดลอกข้อความที่คั่นหน้าในเอกสาร Word
linktitle: คัดลอกข้อความที่คั่นหน้าในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คัดลอกข้อความที่คั่นหน้าระหว่างเอกสาร Word ได้อย่างง่ายดายโดยใช้ Aspose.Words สำหรับ .NET เรียนรู้วิธีการด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/copy-bookmarked-text/
---
## การแนะนำ

เคยพบว่าตัวเองจำเป็นต้องคัดลอกส่วนเฉพาะจากเอกสาร Word หนึ่งไปยังอีกเอกสารหนึ่งหรือไม่? คุณโชคดี! ในบทช่วยสอนนี้ เราจะอธิบายวิธีคัดลอกข้อความที่บุ๊กมาร์กจากเอกสาร Word หนึ่งไปยังอีกเอกสารหนึ่งโดยใช้ Aspose.Words สำหรับ .NET ไม่ว่าคุณจะสร้างรายงานแบบไดนามิกหรือสร้างเอกสารอัตโนมัติ คู่มือนี้จะทำให้กระบวนการง่ายขึ้นสำหรับคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะดำน้ำ ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

-  Aspose.Words สำหรับ .NET Library: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET อื่น ๆ
- ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# และกรอบงาน .NET

## นำเข้าเนมสเปซ

ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## ขั้นตอนที่ 1: โหลดเอกสารต้นฉบับ

ก่อนอื่น คุณต้องโหลดเอกสารต้นฉบับที่มีข้อความบุ๊กมาร์กที่คุณต้องการคัดลอก

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 ที่นี่,`dataDir` คือเส้นทางไปยังไดเร็กทอรีเอกสารของคุณและ`Bookmarks.docx` เป็นเอกสารต้นทาง

## ขั้นตอนที่ 2: ระบุบุ๊กมาร์ก

จากนั้น ระบุบุ๊กมาร์กที่คุณต้องการคัดลอกจากเอกสารต้นฉบับ

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 แทนที่`"MyBookmark1"` พร้อมชื่อจริงของบุ๊กมาร์กของคุณ

## ขั้นตอนที่ 3: สร้างเอกสารปลายทาง

ตอนนี้ให้สร้างเอกสารใหม่ที่จะคัดลอกข้อความที่บุ๊กมาร์กไว้

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## ขั้นตอนที่ 4: นำเข้าเนื้อหาที่คั่นหน้า

 เพื่อให้แน่ใจว่าสไตล์และการจัดรูปแบบจะยังคงอยู่ ให้ใช้`NodeImporter` เพื่อนำเข้าเนื้อหาที่คั่นหน้าจากเอกสารต้นทางไปยังเอกสารปลายทาง

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## ขั้นตอนที่ 5: กำหนดวิธีการ AppendBookmarkedText

นี่คือจุดที่ความมหัศจรรย์เกิดขึ้น กำหนดวิธีการจัดการกับการคัดลอกข้อความที่คั่นหน้า:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## ขั้นตอนที่ 6: บันทึกเอกสารปลายทาง

สุดท้าย ให้บันทึกเอกสารปลายทางเพื่อตรวจสอบเนื้อหาที่คัดลอก

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## บทสรุป

แค่นั้นแหละ! คุณได้คัดลอกข้อความบุ๊กมาร์กจากเอกสาร Word หนึ่งไปยังอีกเอกสารหนึ่งได้สำเร็จโดยใช้ Aspose.Words สำหรับ .NET วิธีการนี้มีประสิทธิภาพในการทำงานจัดการเอกสารโดยอัตโนมัติ ทำให้ขั้นตอนการทำงานของคุณมีประสิทธิภาพและคล่องตัวยิ่งขึ้น

## คำถามที่พบบ่อย

### ฉันสามารถคัดลอกบุ๊กมาร์กหลายรายการพร้อมกันได้หรือไม่
ได้ คุณสามารถวนซ้ำผ่านบุ๊กมาร์กหลายรายการ และใช้วิธีการเดียวกันในการคัดลอกแต่ละบุ๊กมาร์ก

### จะเกิดอะไรขึ้นหากไม่พบบุ๊กมาร์ก?
 ที่`Range.Bookmarks` ทรัพย์สินจะกลับมา`null`ดังนั้นให้แน่ใจว่าคุณจัดการกรณีนี้เพื่อหลีกเลี่ยงข้อยกเว้น

### ฉันสามารถคงรูปแบบของบุ๊กมาร์กเดิมไว้ได้หรือไม่
 อย่างแน่นอน! โดยใช้`ImportFormatMode.KeepSourceFormatting` ตรวจสอบให้แน่ใจว่าการจัดรูปแบบดั้งเดิมยังคงอยู่

### มีการจำกัดขนาดของข้อความที่บุ๊กมาร์กหรือไม่?
ไม่มีขีดจำกัดเฉพาะ แต่ประสิทธิภาพอาจแตกต่างกันไปตามเอกสารที่มีขนาดใหญ่มาก

### ฉันสามารถคัดลอกข้อความระหว่างรูปแบบเอกสาร Word ที่แตกต่างกันได้หรือไม่
ใช่ Aspose.Words รองรับรูปแบบ Word ที่หลากหลาย และวิธีการนี้สามารถใช้ได้กับรูปแบบเหล่านี้
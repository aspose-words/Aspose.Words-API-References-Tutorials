---
title: แสดงซ่อนบุ๊กมาร์กในเอกสาร Word
linktitle: แสดงซ่อนบุ๊กมาร์กในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแสดงหรือซ่อนบุ๊กมาร์กเฉพาะในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/show-hide-bookmarks/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชันแสดงซ่อนบุ๊กมาร์กในไลบรารี Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถแสดงหรือซ่อนบุ๊กมาร์กเฉพาะในเอกสาร Word

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

 เราใช้`Document` คลาสเพื่อโหลดเอกสารที่มีอยู่จากไฟล์:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## ขั้นตอนที่ 2: แสดงหรือซ่อนบุ๊กมาร์กเฉพาะ

 เราใช้`ShowHideBookmarkedContent` ฟังก์ชั่นแสดงหรือซ่อนบุ๊กมาร์กเฉพาะในเอกสาร ฟังก์ชันนี้จะใช้เป็นพารามิเตอร์ของเอกสาร ชื่อของบุ๊กมาร์ก และบูลีนเพื่อระบุว่าจะแสดงหรือซ่อนบุ๊กมาร์ก:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## ขั้นตอนที่ 3: บันทึกเอกสารที่แก้ไข

 เราใช้`Save` วิธีการบันทึกเอกสารที่แก้ไขลงในไฟล์:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับแสดงซ่อนบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการแสดงหรือซ่อนบุ๊กมาร์กเฉพาะโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ซอร์สโค้ด ShowHideBookmarkedContent

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟีเจอร์แสดงซ่อนบุ๊กมาร์กของ Aspose.Words สำหรับ .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่อแสดงหรือซ่อนบุ๊กมาร์กเฉพาะในเอกสาร

### คำถามที่พบบ่อยสำหรับการแสดงซ่อนบุ๊กมาร์กในเอกสาร word

#### ถาม: ฉันสามารถแสดงหรือซ่อนบุ๊กมาร์กหลายรายการในเอกสารเดียวกันได้หรือไม่

ตอบ: ได้ คุณสามารถแสดงหรือซ่อนบุ๊กมาร์กหลายรายการในเอกสารเดียวกันได้โดยทำซ้ำขั้นตอนที่ 2 และ 3 สำหรับแต่ละบุ๊กมาร์กที่คุณต้องการดำเนินการ

#### ถาม: โค้ดที่ให้มาทำงานร่วมกับรูปแบบเอกสาร Word อื่นๆ เช่น .doc หรือ .docm ได้หรือไม่

ตอบ: ใช่ โค้ดที่ให้มาใช้งานได้กับเอกสาร Word รูปแบบต่างๆ ที่ Aspose.Words รองรับ เช่น .doc และ .docm เพียงให้แน่ใจว่าใช้ชื่อไฟล์และเส้นทางที่ถูกต้องเมื่อโหลดและบันทึกเอกสาร

#### ถาม: ฉันจะแสดงบุ๊กมาร์กที่ซ่อนอยู่อีกครั้งได้อย่างไร

 ตอบ: หากต้องการแสดงบุ๊กมาร์กที่ซ่อนอยู่อีกครั้ง คุณต้องใช้อันเดิม`ShowHideBookmarkedContent` ฟังก์ชันส่งผ่านค่า`true` สำหรับพารามิเตอร์บูลีนที่ระบุว่าจะแสดงหรือซ่อนบุ๊กมาร์ก

#### ถาม: ฉันสามารถใช้เงื่อนไขเพื่อแสดงหรือซ่อนบุ๊กมาร์กตามค่าฟิลด์ผสานในเอกสารได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้เงื่อนไขและผสานค่าฟิลด์เพื่อกำหนดว่าควรแสดงหรือซ่อนบุ๊กมาร์กหรือไม่ คุณสามารถปรับแต่งโค้ดของ`ShowHideBookmarkedContent` ทำหน้าที่คำนึงถึงเงื่อนไขและค่าที่เหมาะสม

#### ถาม: ฉันจะลบบุ๊กมาร์กในเอกสาร Word โดยใช้ Aspose.Words for .NET ได้อย่างไร

 ตอบ: หากต้องการลบบุ๊กมาร์กในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`RemoveBookmarks` วิธีการของ`Document` ระดับ. นี่คือโค้ดตัวอย่าง:

```csharp
doc.RemoveBookmarks("BookmarkName");
```
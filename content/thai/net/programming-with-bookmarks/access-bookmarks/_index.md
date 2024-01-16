---
title: เข้าถึงบุ๊กมาร์กในเอกสาร Word
linktitle: เข้าถึงบุ๊กมาร์กในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการเข้าถึงบุ๊กมาร์กในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/programming-with-bookmarks/access-bookmarks/
---

ในบทความนี้ เราจะสำรวจซอร์สโค้ด C# ด้านบนเพื่อทำความเข้าใจวิธีใช้ฟังก์ชัน Access Bookmarks ใน Aspose.Words สำหรับไลบรารี .NET คุณลักษณะนี้ให้การเข้าถึงบุ๊กมาร์กเฉพาะในเอกสาร Word

## ข้อกำหนดเบื้องต้น

- ความรู้พื้นฐานของภาษา C#
- สภาพแวดล้อมการพัฒนา .NET ที่ติดตั้งไลบรารี Aspose.Words

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

 ก่อนที่เราจะเริ่มเข้าถึงบุ๊กมาร์ก เราต้องโหลดเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ซึ่งสามารถทำได้โดยการยกตัวอย่าง a`Document` วัตถุที่ระบุเส้นทางไฟล์เอกสาร:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## ขั้นตอนที่ 2: การเข้าถึงบุ๊กมาร์ก

เมื่อโหลดเอกสารแล้วเราจะสามารถเข้าถึงบุ๊กมาร์กในเอกสารได้ มีสองวิธีในการเข้าถึงบุ๊กมาร์ก: ตามดัชนีและตามชื่อ

- เข้าถึงโดยดัชนี: ในตัวอย่างของเรา เราใช้ดัชนี 0 เพื่อเข้าถึงบุ๊กมาร์กแรกของเอกสาร:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- เข้าถึงด้วยชื่อ: ในตัวอย่างของเรา เราใช้ชื่อ "MyBookmark3" เพื่อเข้าถึงบุ๊กมาร์กเฉพาะในเอกสาร:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### ตัวอย่างซอร์สโค้ดสำหรับ Access Bookmarks โดยใช้ Aspose.Words สำหรับ .NET

นี่คือตัวอย่างซอร์สโค้ดแบบเต็มเพื่อสาธิตการเข้าถึงบุ๊กมาร์กโดยใช้ Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// ตามดัชนี:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// โดยชื่อ:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## บทสรุป

ในบทความนี้ เราได้สำรวจซอร์สโค้ด C# เพื่อทำความเข้าใจวิธีใช้ฟีเจอร์ Access Bookmarks ของ Aspose.Words สำหรับ .NET เราทำตามคำแนะนำทีละขั้นตอนเพื่ออัปโหลดเอกสารและเข้าถึงบุ๊กมาร์กโดยใช้ดัชนีและชื่อ

### คำถามที่พบบ่อยสำหรับการเข้าถึงบุ๊กมาร์กในเอกสาร word

#### ถาม: ฉันจะอัปโหลดเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการโหลดเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถยกตัวอย่าง a`Document`วัตถุโดยระบุเส้นทางไฟล์ของเอกสาร นี่คือโค้ดตัวอย่าง:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

#### ถาม: ฉันจะเข้าถึงบุ๊กมาร์กในเอกสาร Word ได้อย่างไร

 ตอบ: คุณสามารถเข้าถึงบุ๊กมาร์กในเอกสาร Word ได้โดยใช้`Bookmarks` ทรัพย์สินของ`Range` วัตถุ. คุณสามารถเข้าถึงบุ๊กมาร์กตามดัชนีหรือตามชื่อ นี่คือโค้ดตัวอย่าง:

- เข้าถึงโดยดัชนี:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- เข้าถึงด้วยชื่อ:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

#### ถาม: ไลบรารีใดที่จำเป็นในการใช้คุณสมบัติการเข้าถึงบุ๊กมาร์กใน Aspose.Words สำหรับ .NET

ตอบ: หากต้องการใช้คุณสมบัติการเข้าถึงบุ๊กมาร์กใน Aspose.Words สำหรับ .NET คุณต้องมีไลบรารี Aspose.Words ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีนี้ในสภาพแวดล้อมการพัฒนา .NET ของคุณ

#### ถาม: มีวิธีอื่นในการเข้าถึงบุ๊กมาร์กในเอกสาร Word หรือไม่

 ตอบ: ได้ นอกเหนือจากการเข้าถึงบุ๊กมาร์กตามดัชนีหรือตามชื่อแล้ว คุณยังสามารถวนซ้ำบุ๊กมาร์กทั้งหมดในเอกสารโดยใช้การวนซ้ำ คุณสามารถรับจำนวนบุ๊กมาร์กทั้งหมดในเอกสารได้โดยใช้`Count` ทรัพย์สินของ`Bookmarks` ของสะสม. จากนั้นคุณสามารถเข้าถึงบุ๊กมาร์กแต่ละรายการได้โดยใช้ดัชนี นี่คือโค้ดตัวอย่าง:

```csharp
int bookmarkCount = doc.Range.Bookmarks.Count;

for (int i = 0; i < bookmarkCount; i++)
{
     Bookmark bookmark = doc.Range.Bookmarks[i];
     // ทำอะไรสักอย่างกับบุ๊กมาร์ก...
}
```
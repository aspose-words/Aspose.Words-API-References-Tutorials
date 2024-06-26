---
title: แยกเอกสาร Word ตามส่วนหัว Html
linktitle: โดยหัวเรื่อง Html
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ของเอกสารคำแยกโดยฟีเจอร์ Heading HTML ของ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/split-document/by-headings-html/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแบ่งเอกสาร Word ออกเป็นส่วนเล็กๆ โดยใช้ฟีเจอร์ By HTML Heading ของ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและสร้างเอกสาร HTML แยกกันตามหัวข้อ

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ในการเริ่มต้น ให้ระบุไดเร็กทอรีสำหรับเอกสารของคุณและโหลดเอกสารลงในออบเจ็กต์ Document มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## ขั้นตอนที่ 2: การแบ่งเอกสารตามหัวข้อในรูปแบบ HTML

ตอนนี้เราจะตั้งค่าตัวเลือกการบันทึกเพื่อแบ่งเอกสารออกเป็นส่วนเล็กๆ ตามหัวข้อในรูปแบบ HTML มีวิธีดังนี้:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// แบ่งเอกสารออกเป็นส่วนเล็กๆ ในกรณีนี้ โดยแยกตามชื่อเรื่อง
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### ตัวอย่างซอร์สโค้ดสำหรับ By Headings HTML โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์ By HTML Heading ของ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// แบ่งเอกสารออกเป็นส่วนเล็กๆ ในกรณีนี้ แบ่งตามหัวข้อ
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

ด้วยโค้ดนี้ คุณจะสามารถแบ่งเอกสาร Word ออกเป็นส่วนเล็กๆ ได้โดยใช้ Aspose.Words สำหรับ .NET ตามหัวข้อ จากนั้นคุณสามารถสร้างเอกสาร HTML แยกกันสำหรับแต่ละส่วนได้

## บทสรุป

 ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแบ่งเอกสาร Word ออกเป็นส่วนเล็กๆ โดยใช้ฟีเจอร์ By HTML Heading ของ Aspose.Words for .NET โดยระบุ`DocumentSplitCriteria` เช่น`HeadingParagraph` ใน`HtmlSaveOptions`เราสามารถสร้างเอกสาร HTML แยกกันตามหัวข้อที่มีอยู่ในเอกสารต้นฉบับได้

การแบ่งเอกสารตามหัวข้อจะมีประโยชน์สำหรับการจัดระเบียบและจัดการเนื้อหา โดยเฉพาะในเอกสารขนาดใหญ่ที่มีหลายส่วน Aspose.Words สำหรับ .NET มอบโซลูชันที่เชื่อถือได้และมีประสิทธิภาพสำหรับการจัดการการแยกเอกสารและสร้างเอาต์พุตในรูปแบบต่างๆ

รู้สึกอิสระที่จะสำรวจคุณสมบัติและตัวเลือกเพิ่มเติมที่ Aspose.Words สำหรับ .NET มอบให้เพื่อเพิ่มความสามารถในการประมวลผลเอกสารของคุณและปรับปรุงขั้นตอนการทำงานของคุณ

### คำถามที่พบบ่อย

#### ฉันจะแบ่งเอกสาร Word ออกเป็นส่วนเล็ก ๆ ตามหัวข้อโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 หากต้องการแยกเอกสาร Word ตามส่วนหัว คุณสามารถใช้คุณลักษณะ By HTML Heading ของ Aspose.Words สำหรับ .NET ทำตามซอร์สโค้ดที่ให้มาและตั้งค่า`DocumentSplitCriteria` ถึง`HeadingParagraph` ใน`HtmlSaveOptions` วัตถุ วัตถุ การดำเนินการนี้จะแบ่งเอกสารออกเป็นส่วนเล็กๆ ในแต่ละหัวข้อ

#### ฉันสามารถแบ่งเอกสาร Word เป็นรูปแบบใดได้บ้าง

 ซอร์สโค้ดที่ให้มาสาธิตการแบ่งเอกสาร Word ออกเป็นส่วนเล็กๆ ในรูปแบบ HTML อย่างไรก็ตาม Aspose.Words สำหรับ .NET รองรับรูปแบบเอาต์พุตที่หลากหลาย รวมถึง DOCX, PDF, EPUB และอื่นๆ คุณสามารถแก้ไขโค้ดและระบุรูปแบบผลลัพธ์ที่ต้องการได้ใน`HtmlSaveOptions` วัตถุตามนั้น

#### ฉันสามารถเลือกเกณฑ์อื่นสำหรับการแยกเอกสารได้หรือไม่

ได้ คุณสามารถเลือกเกณฑ์อื่นสำหรับการแบ่งเอกสารได้ตามความต้องการของคุณ Aspose.Words สำหรับ .NET มีตัวเลือกเกณฑ์มากมาย เช่น`HeadingParagraph`, `Page`, `Section` , และอื่น ๆ. ปรับเปลี่ยน`DocumentSplitCriteria` ทรัพย์สินใน`HtmlSaveOptions` วัตถุเพื่อเลือกเกณฑ์ที่เหมาะสมสำหรับการแยก

#### ฉันจะปรับแต่งเอาต์พุต HTML สำหรับส่วนที่แยกได้อย่างไร

 Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถปรับแต่งเอาต์พุต HTML สำหรับส่วนที่แยกออกได้โดยการระบุตัวเลือกเพิ่มเติมใน`HtmlSaveOptions` วัตถุ วัตถุ คุณสามารถควบคุมแง่มุมต่างๆ ได้ เช่น สไตล์ CSS รูปภาพ แบบอักษร และอื่นๆ โปรดดูเอกสารประกอบของ Aspose.Words สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับการปรับแต่งเอาต์พุต HTML

#### ฉันสามารถแบ่งเอกสารตามเกณฑ์หลายข้อได้หรือไม่

 ได้ คุณสามารถแบ่งเอกสารตามเกณฑ์หลายรายการได้โดยการรวมตัวเลือกเกณฑ์ต่างๆ เข้าด้วยกัน ตัวอย่างเช่น คุณสามารถแบ่งเอกสารตามส่วนหัวและหน้าโดยการตั้งค่า`DocumentSplitCriteria`ทรัพย์สินเพื่อ`HeadingParagraph | Page`- การดำเนินการนี้จะแยกเอกสารในแต่ละหัวข้อและแต่ละหน้า โดยสร้างส่วนเล็กๆ ตามเกณฑ์ทั้งสอง
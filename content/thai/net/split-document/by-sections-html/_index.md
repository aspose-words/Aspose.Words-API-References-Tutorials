---
title: แยกเอกสาร Word ตามส่วน HTML
linktitle: โดยส่วน Html
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแบ่งเอกสาร Word ออกเป็นส่วนๆ Html โดยใช้ Aspose.Words สำหรับ .NET พร้อมตัวอย่างโค้ดที่สมบูรณ์
type: docs
weight: 10
url: /th/net/split-document/by-sections-html/
---

ในตัวอย่างนี้ เราจะแสดงวิธีแยกเอกสาร Word ออกเป็นส่วนต่างๆ ในรูปแบบ HTML โดยใช้คุณลักษณะ By HTML Sections ของ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและสร้างเอกสาร HTML แยกกันสำหรับแต่ละส่วน

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ในการเริ่มต้น ให้ระบุไดเร็กทอรีสำหรับเอกสารของคุณและโหลดเอกสารลงในออบเจ็กต์ Document มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## ขั้นตอนที่ 2: การแบ่งเอกสารออกเป็นส่วนต่างๆ ในรูปแบบ HTML

ตอนนี้เราจะตั้งค่าตัวเลือกการบันทึกเพื่อแบ่งเอกสารออกเป็นส่วนต่างๆ ในรูปแบบ HTML ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### ตัวอย่างซอร์สโค้ดสำหรับ By Sections HTML โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์ By HTML Sections ของ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

ด้วยรหัสนี้ คุณจะสามารถแบ่งเอกสาร Word ออกเป็นส่วนๆ ในรูปแบบ HTML โดยใช้ Aspose.Words สำหรับ .NET

ตอนนี้คุณสามารถสร้างเอกสาร HTML แยกกันสำหรับแต่ละส่วนของเอกสารเริ่มต้นได้

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแบ่งเอกสาร Word ออกเป็นส่วนต่างๆ ในรูปแบบ HTML โดยใช้ฟีเจอร์ By HTML Sections ของ Aspose.Words สำหรับ .NET เมื่อปฏิบัติตามซอร์สโค้ดที่ให้มา คุณสามารถสร้างเอกสาร HTML แต่ละฉบับสำหรับแต่ละส่วนของเอกสารต้นฉบับได้

การแบ่งเอกสารออกเป็นส่วนต่างๆ อาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การสร้างเว็บเพจ การแยกเนื้อหาเฉพาะ หรือการจัดระเบียบข้อมูล Aspose.Words สำหรับ .NET มี API ที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถจัดการและปรับแต่งเอกสาร Word ตามความต้องการของคุณได้

รู้สึกอิสระที่จะสำรวจคุณสมบัติเพิ่มเติมที่นำเสนอโดย Aspose.Words สำหรับ .NET เพื่อปรับปรุงความสามารถในการประมวลผลเอกสารของคุณและปรับปรุงขั้นตอนการทำงานของคุณ

### คำถามที่พบบ่อย

#### ฉันจะปรับแต่งรูปแบบเอาต์พุต HTML ได้อย่างไร

Aspose.Words สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งรูปแบบเอาต์พุต HTML คุณสามารถแก้ไขสไตล์ การตั้งค่าแบบอักษร ความละเอียดของภาพ และลักษณะอื่นๆ ของเอกสาร HTML ได้โดยการปรับตัวเลือกการบันทึก โปรดดูเอกสารประกอบของ Aspose.Words สำหรับ .NET สำหรับข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกที่มีให้ใช้งานและวิธีการใช้งาน

#### ฉันสามารถแบ่งเอกสารตามเกณฑ์ที่แตกต่างกันได้หรือไม่

ใช่ นอกจากการใช้ตัวแบ่งส่วนเป็นเกณฑ์การแบ่งแล้ว Aspose.Words สำหรับ .NET ยังเสนอตัวเลือกอื่นๆ เช่น ตัวแบ่งย่อหน้า สไตล์หัวเรื่อง หรือเนื้อหาเฉพาะเป็นเกณฑ์ในการแบ่งเอกสาร คุณสามารถเลือกเกณฑ์ที่เหมาะสมที่สุดได้ตามความต้องการของคุณและปรับโค้ดให้เหมาะสม

#### เป็นไปได้ไหมที่จะแบ่งเอกสารเป็นรูปแบบอื่นที่ไม่ใช่ HTML

ใช่ Aspose.Words สำหรับ .NET รองรับการแบ่งเอกสารเป็นรูปแบบต่างๆ รวมถึง PDF ข้อความธรรมดา รูปภาพ และอื่นๆ คุณสามารถแก้ไขตัวเลือกการบันทึกเพื่อสร้างรูปแบบเอาต์พุตที่ต้องการได้ โปรดดูเอกสารประกอบของ Aspose.Words สำหรับ .NET สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับรูปแบบที่ใช้ได้ และวิธีการระบุรูปแบบเหล่านั้นในตัวเลือกการบันทึก

#### ฉันสามารถแยกเอกสารหลายชุดพร้อมกันได้หรือไม่?

ได้ คุณสามารถใช้กระบวนการแยกกับเอกสารหลายชุดพร้อมกันได้โดยวนซ้ำชุดเอกสารและดำเนินการรหัสแยกสำหรับแต่ละเอกสารแยกกัน ซึ่งช่วยให้คุณประมวลผลเอกสารหลายชุดได้อย่างมีประสิทธิภาพ และสร้างส่วนแยกกันสำหรับแต่ละเอกสาร

#### ฉันจะรวมส่วนต่างๆ กลับเป็นเอกสารเดียวได้อย่างไร

Aspose.Words สำหรับ .NET ยังมีวิธีการในการรวมเอกสารหรือส่วนต่างๆ กลับเป็นเอกสารเดียวอีกด้วย ด้วยการใช้คุณสมบัติการรวมเหล่านี้ คุณสามารถรวมส่วนที่สร้างแยกกันและสร้างเอกสารที่เป็นหนึ่งเดียวได้ โปรดดูเอกสารประกอบของ Aspose.Words สำหรับ .NET สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการผสานเอกสารหรือส่วนต่างๆ



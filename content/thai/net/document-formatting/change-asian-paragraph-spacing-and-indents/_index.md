---
title: เปลี่ยนระยะห่างย่อหน้าเอเชียและการเยื้องในเอกสาร Word
linktitle: เปลี่ยนระยะห่างย่อหน้าเอเชียและการเยื้องในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเปลี่ยนระยะห่างย่อหน้าเอเชียและการเยื้องในเอกสารคำด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการเปลี่ยนระยะห่างและการเยื้องของย่อหน้าภาษาเอเชียโดยใช้ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและใช้การเปลี่ยนแปลง

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ในการเริ่มต้น ให้ระบุไดเร็กทอรีสำหรับเอกสารของคุณและโหลดเอกสารที่มีตัวพิมพ์แบบเอเชียลงในออบเจ็กต์ Document มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## ขั้นตอนที่ 2: การเปลี่ยนระยะห่างและการเยื้องย่อหน้า

ตอนนี้เราจะแก้ไขระยะห่างและการเยื้องของย่อหน้าแรกของเอกสารเอเชีย มีวิธีดังนี้:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // อัปเดต ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // อัปเดต ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //อัปเดต ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // อัปเดตรูปแบบย่อหน้า SpaceBefore
format.LineUnitAfter = 10; // อัปเดตรูปแบบย่อหน้า SpaceAfter
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### ตัวอย่างซอร์สโค้ดสำหรับเปลี่ยนระยะห่างย่อหน้าเอเชียและการเยื้องโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์แก้ไขระยะห่างย่อหน้าเอเชียและการเยื้องด้วย Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent จะได้รับการปรับปรุง
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent จะได้รับการปรับปรุง
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent จะได้รับการปรับปรุง
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore จะได้รับการปรับปรุง
	format.LineUnitAfter = 10;                 // ParagraphFormat SpaceAfter จะได้รับการอัปเดต

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

ด้วยโค้ดนี้ คุณจะสามารถเปลี่ยนระยะห่างและการเยื้องของย่อหน้าเอเชียได้โดยใช้ Aspose.Words สำหรับ .NET

## บทสรุป

 ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเปลี่ยนระยะห่างและการเยื้องของย่อหน้าเอเชียโดยใช้ Aspose.Words สำหรับ .NET โดยการปรับเปลี่ยนคุณสมบัติที่เกี่ยวข้องของ`ParagraphFormat`เราสามารถควบคุมเค้าโครงและลักษณะของย่อหน้าเอเชียในเอกสาร Word ได้ คุณสมบัตินี้มีประโยชน์สำหรับการปรับแต่งการจัดรูปแบบข้อความด้วยตัวอักษรเอเชีย และการนำเสนอภาพตามที่ต้องการในเอกสารที่มีเนื้อหาแบบผสมภาษา

### คำถามที่พบบ่อย

#### ถาม: ฟีเจอร์ “เปลี่ยนระยะห่างและการเยื้องย่อหน้าเอเชีย” ใน Aspose.Words สำหรับ .NET ทำหน้าที่อะไร

ตอบ: คุณลักษณะ “เปลี่ยนระยะห่างและการเยื้องย่อหน้าเอเชีย” ใน Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถปรับเปลี่ยนคุณสมบัติระยะห่างและการเยื้องของย่อหน้าเอเชียในเอกสาร Word ได้ คุณสามารถปรับการเยื้องซ้ายและขวา การเยื้องบรรทัดแรก ช่องว่างก่อน และช่องว่างหลังค่า เพื่อควบคุมเค้าโครงและรูปลักษณ์ของย่อหน้า

#### ถาม: ฉันจะเปลี่ยนระยะห่างและการเยื้องของย่อหน้าเอเชียโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเปลี่ยนระยะห่างและการเยื้องของย่อหน้าเอเชีย คุณต้องเข้าถึง`ParagraphFormat`ของย่อหน้าเป้าหมายและแก้ไขคุณสมบัติที่เกี่ยวข้อง ในโค้ดตัวอย่างที่ให้มา เราเข้าถึงย่อหน้าแรกของเอกสารและตั้งค่า`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , และ`LineUnitAfter` คุณสมบัติในการปรับระยะห่างและการเยื้อง

#### ถาม: ฉันสามารถนำการเปลี่ยนแปลงเหล่านี้ไปใช้กับย่อหน้าอื่นในเอกสารได้หรือไม่

 ตอบ: ได้ คุณสามารถนำการเปลี่ยนแปลงเหล่านี้ไปใช้กับย่อหน้าอื่นๆ ในเอกสารได้โดยเข้าไปที่ส่วนต่างๆ ตามลำดับ`ParagraphFormat` วัตถุ โค้ดตัวอย่างกำหนดเป้าหมายไปที่ย่อหน้าแรกของเอกสาร แต่คุณสามารถแก้ไขย่อหน้าอื่นๆ ได้โดยการปรับดัชนีใน`Paragraphs` รวบรวมหรือใช้เกณฑ์อื่นเพื่อเลือกย่อหน้าที่ต้องการ
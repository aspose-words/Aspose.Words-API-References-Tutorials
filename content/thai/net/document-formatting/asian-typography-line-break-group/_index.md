---
title: กลุ่มแบ่งบรรทัดตัวอักษรเอเชียในเอกสารเวิร์ด
linktitle: กลุ่มแบ่งบรรทัดตัวอักษรเอเชียในเอกสารเวิร์ด
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้กลุ่มตัวแบ่งบรรทัด Asian Typography ในเอกสาร word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/document-formatting/asian-typography-line-break-group/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีใช้กลุ่มตัวแบ่งบรรทัดแบบอักษรเอเชียในฟีเจอร์เอกสารคำด้วย Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและใช้การเปลี่ยนแปลงการจัดรูปแบบ

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ในการเริ่มต้น ให้ระบุไดเร็กทอรีสำหรับเอกสารของคุณและโหลดเอกสารที่มีตัวพิมพ์แบบเอเชียลงในออบเจ็กต์ Document มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## ขั้นตอนที่ 2: การตั้งค่าการพิมพ์แบบเอเชีย

ตอนนี้เราจะกำหนดการตั้งค่าการพิมพ์แบบเอเชียสำหรับย่อหน้าแรกของเอกสาร มีวิธีดังนี้:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับ Asian Typography Line Break Group โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์ Asian Typography Line Break Group พร้อม Aspose.Words สำหรับ .NET:

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
ด้วยโค้ดนี้ คุณจะสามารถใช้กลุ่มตัวแบ่งบรรทัด Asian Typography โดยใช้ Aspose.Words สำหรับ .NET

## บทสรุป

 ในบทช่วยสอนนี้ เราได้สำรวจฟีเจอร์ "กลุ่มตัวแบ่งบรรทัดแบบอักษรเอเชีย" ใน Aspose.Words สำหรับ .NET โดยการกำหนดค่า`FarEastLineBreakControl`, `WordWrap` , และ`HangingPunctuation` คุณสมบัติของ`ParagraphFormat`เราสามารถควบคุมพฤติกรรมการแบ่งบรรทัดสำหรับการพิมพ์แบบเอเชียในเอกสาร Word ได้ คุณลักษณะนี้มีประโยชน์สำหรับการจัดการอักขระเอเชีย และช่วยให้มั่นใจว่ามีการแบ่งบรรทัดและการตัดคำในเอกสารที่มีเนื้อหาภาษาผสมอย่างเหมาะสม

### คำถามที่พบบ่อย

#### ถาม: ฟีเจอร์ "กลุ่มตัวแบ่งบรรทัดแบบอักษรเอเชีย" ใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะ "กลุ่มตัวแบ่งบรรทัดการพิมพ์แบบเอเชีย" ใน Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถควบคุมลักษณะการทำงานการแบ่งบรรทัดสำหรับการพิมพ์แบบเอเชียในเอกสาร Word โดยเฉพาะอย่างยิ่งจะส่งผลต่อวิธีการแบ่งบรรทัดและการตัดคำเมื่อจัดการกับอักขระเอเชียในย่อหน้า

#### ถาม: ฉันจะเปิดใช้งาน "กลุ่มตัวแบ่งบรรทัดแบบอักษรเอเชีย" ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเปิดใช้งาน "กลุ่มตัวแบ่งบรรทัดแบบอักษรเอเชีย" คุณต้องกำหนดค่า`FarEastLineBreakControl`, `WordWrap` , และ`HangingPunctuation` คุณสมบัติของ`ParagraphFormat` สำหรับย่อหน้าที่เกี่ยวข้องในเอกสารของคุณ การตั้งค่า`FarEastLineBreakControl` ถึง`false` ตรวจสอบให้แน่ใจว่าอักขระเอเชียได้รับการปฏิบัติเหมือนกับอักขระละตินเกี่ยวกับการขึ้นบรรทัดใหม่`WordWrap` ตั้งค่าให้`true` เปิดใช้งานการตัดคำสำหรับการพิมพ์แบบเอเชีย และ`HangingPunctuation` ตั้งค่าให้`false` ป้องกันไม่ให้เครื่องหมายวรรคตอนค้างอยู่ในข้อความภาษาเอเชีย

#### ถาม: ฉันสามารถใช้ "กลุ่มตัวแบ่งบรรทัดแบบอักษรเอเชีย" กับย่อหน้าเฉพาะในเอกสารได้หรือไม่

ตอบ: ได้ คุณสามารถใช้การตั้งค่า "กลุ่มตัวแบ่งบรรทัดแบบอักษรเอเชีย" กับย่อหน้าเฉพาะในเอกสาร Word ได้ ในโค้ดตัวอย่าง การตั้งค่าจะนำไปใช้กับย่อหน้าแรกของเอกสาร คุณสามารถปรับโค้ดเพื่อกำหนดเป้าหมายย่อหน้าอื่น ๆ ได้ตามต้องการโดยเข้าถึงผ่าน`Paragraphs` การรวบรวมส่วนที่เกี่ยวข้องในเอกสาร
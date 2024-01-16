---
title: ช่องว่างระหว่างข้อความเอเชียและละตินในเอกสาร Word
linktitle: ช่องว่างระหว่างข้อความเอเชียและละตินในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีปรับช่องว่างระหว่างข้อความเอเชียและละตินในเอกสาร Word โดยอัตโนมัติด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/document-formatting/space-between-asian-and-latin-text/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีใช้ฟีเจอร์ Space ระหว่างข้อความเอเชียและละตินในฟีเจอร์เอกสาร Word ด้วย Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและใช้การเปลี่ยนแปลง

## ขั้นตอนที่ 1: การสร้างและกำหนดค่าเอกสาร

ในการเริ่มต้น ให้สร้างเอกสารใหม่และออบเจ็กต์ DocumentBuilder ที่เกี่ยวข้อง มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การตั้งค่าช่องว่างระหว่างข้อความเอเชียและละติน

ตอนนี้เราจะกำหนดค่าช่องว่างระหว่างข้อความเอเชียและละตินโดยใช้คุณสมบัติของวัตถุ ParagraphFormat มีวิธีดังนี้:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## ขั้นตอนที่ 3: บันทึกเอกสาร

 หลังจากแทรกฟิลด์แบบฟอร์มป้อนข้อความแล้ว ให้บันทึกเอกสารไปยังตำแหน่งที่ต้องการโดยใช้`Save` วิธี. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางไฟล์ที่เหมาะสม:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับช่องว่างระหว่างข้อความเอเชียและละตินโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์ Space Between Asian และ Latin Text พร้อม Aspose.Words สำหรับ .NET:


```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

ด้วยโค้ดนี้ คุณจะสามารถปรับช่องว่างระหว่างข้อความเอเชียและละตินในเอกสารของคุณโดยอัตโนมัติโดยใช้ Aspose.Words สำหรับ .NET

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการใช้ฟีเจอร์ Space เพื่อปรับระยะห่างระหว่างข้อความเอเชียและละตินในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET เมื่อทำตามขั้นตอนที่ระบุไว้ คุณจะมั่นใจได้ว่ามีระยะห่างและการจัดตำแหน่งที่เหมาะสม ซึ่งจะมีประโยชน์อย่างยิ่งเมื่อต้องรับมือกับเนื้อหาเอเชียและละตินผสมกัน

### คำถามที่พบบ่อย

#### ถาม: ฟีเจอร์ Space ระหว่างข้อความเอเชียและละตินในเอกสาร Word คืออะไร

ตอบ: คุณลักษณะช่องว่างระหว่างข้อความเอเชียและละตินในเอกสาร Word หมายถึงความสามารถในการปรับระยะห่างระหว่างข้อความที่เขียนด้วยสคริปต์ที่แตกต่างกัน เช่น เอเชีย (เช่น จีน ญี่ปุ่น) และละติน (เช่น อังกฤษ) โดยอัตโนมัติ

#### ถาม: เหตุใดการปรับช่องว่างระหว่างข้อความภาษาเอเชียและภาษาละตินจึงมีความสำคัญ

ตอบ: การปรับช่องว่างระหว่างข้อความเอเชียและละตินถือเป็นสิ่งสำคัญเพื่อให้แน่ใจว่าสคริปต์ต่างๆ ผสมผสานกันภายในเอกสารได้อย่างกลมกลืน การเว้นวรรคที่เหมาะสมจะช่วยเพิ่มความสะดวกในการอ่านและรูปลักษณ์โดยรวม ป้องกันไม่ให้ข้อความปรากฏแคบหรือกระจายเกินไป

#### ถาม: ฉันสามารถปรับแต่งการปรับพื้นที่ระหว่างสคริปต์ต่างๆ ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งการปรับพื้นที่ระหว่างสคริปต์ต่างๆ ได้โดยใช้`AddSpaceBetweenFarEastAndAlpha` และ`AddSpaceBetweenFarEastAndDigit` คุณสมบัติ. เมื่อเปิดใช้งานหรือปิดใช้งานคุณสมบัติเหล่านี้ คุณสามารถควบคุมช่องว่างระหว่างข้อความเอเชียและละติน รวมถึงระหว่างข้อความและตัวเลขเอเชียได้

#### ถาม: Aspose.Words สำหรับ .NET รองรับคุณสมบัติการจัดรูปแบบเอกสารอื่นๆ หรือไม่

ตอบ: ได้ Aspose.Words สำหรับ .NET ให้การสนับสนุนฟีเจอร์การจัดรูปแบบเอกสารที่หลากหลาย ประกอบด้วยฟังก์ชันสำหรับลักษณะแบบอักษร ย่อหน้า ตาราง รูปภาพ และอื่นๆ คุณสามารถจัดการและจัดรูปแบบเอกสาร Word ของคุณโดยทางโปรแกรมได้อย่างมีประสิทธิภาพ

#### ถาม: ฉันจะหาแหล่งข้อมูลเพิ่มเติมและเอกสารประกอบสำหรับ Aspose.Words สำหรับ .NET ได้ที่ไหน

 ตอบ: สำหรับแหล่งข้อมูลและเอกสารที่ครอบคลุมเกี่ยวกับการใช้ Aspose.Words สำหรับ .NET โปรดไปที่[การอ้างอิง API ของ Aspose.Words](https://reference.aspose.com/words/net/). ที่นั่น คุณจะพบคำแนะนำโดยละเอียด บทช่วยสอน ตัวอย่างโค้ด และการอ้างอิง API เพื่อช่วยให้คุณใช้คุณสมบัติอันทรงพลังของ Aspose.Words สำหรับ .NET ได้อย่างมีประสิทธิภาพ
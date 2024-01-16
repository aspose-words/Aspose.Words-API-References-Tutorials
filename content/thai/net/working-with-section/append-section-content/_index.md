---
title: ผนวกเนื้อหาคำส่วน
linktitle: ผนวกเนื้อหาคำส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีเพิ่มเนื้อหาคำไปยังส่วนเฉพาะของเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-section/append-section-content/
---
ในบทช่วยสอนนี้ เราจะแสดงให้คุณเห็นถึงวิธีการเพิ่มเนื้อหาคำในส่วนเฉพาะของเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การเพิ่มเนื้อหาลงในส่วนที่มีอยู่จะมีประโยชน์ในการจัดระเบียบและจัดโครงสร้างเอกสารของคุณอย่างแม่นยำ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารและตัวสร้าง
 ขั้นแรก เราจะสร้างอินสแตนซ์ของ`Document` ชั้นเรียนและที่เกี่ยวข้อง`DocumentBuilder` ตัวสร้างเพื่อสร้างเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: เพิ่มเนื้อหาในส่วนต่างๆ
 ต่อไปเราจะใช้`DocumentBuilder` Constructor เพื่อเพิ่มเนื้อหาไปยังส่วนต่างๆ ของเอกสาร ในตัวอย่างนี้ เรากำลังเพิ่มเนื้อหาลงในสี่ส่วนที่แตกต่างกัน

```csharp
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

## ขั้นตอนที่ 3: เพิ่มและแทรกเนื้อหาระหว่างส่วนต่างๆ
ในการเพิ่มและแทรกเนื้อหาระหว่างส่วนต่างๆ เราจะเลือกส่วนเฉพาะที่เราต้องการเพิ่มเนื้อหา ในตัวอย่างนี้ เราจะเพิ่มเนื้อหาของส่วนแรกไปที่จุดเริ่มต้นของส่วนที่สาม จากนั้นเพิ่มเนื้อหาของส่วนที่สองไปที่ส่วนท้ายของส่วนที่สาม

```csharp
Section section = doc.Sections[2];

Section sectionToPrepend = doc.Sections[0];
section.PrependContent(sectionToPrepend);

Section sectionToAppend = doc.Sections[1];
section.AppendContent(sectionToAppend);
```

### ตัวอย่างซอร์สโค้ดสำหรับผนวกเนื้อหา Word ของส่วนโดยใช้ Aspose.Words สำหรับ .NET 

```csharp

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");

// นี่คือส่วนที่เราจะต่อท้ายและต่อท้าย
Section section = doc.Sections[2];

// นี่เป็นการคัดลอกเนื้อหาของส่วนที่ 1 และแทรกไว้ที่จุดเริ่มต้นของส่วนที่ระบุ
Section sectionToPrepend = doc.Sections[0];
section.PrependContent(sectionToPrepend);

// นี่เป็นการคัดลอกเนื้อหาของส่วนที่ 2 และแทรกไว้ที่ส่วนท้ายของส่วนที่ระบุ
Section sectionToAppend = doc.Sections[1];
section.AppendContent(sectionToAppend);

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีเพิ่มเนื้อหาไปยังส่วนเฉพาะของเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เมื่อทำตามขั้นตอนที่อธิบายไว้ คุณสามารถจัดระเบียบและจัดโครงสร้างเอกสารของคุณได้อย่างง่ายดายโดยการเพิ่มและแทรกเนื้อหาระหว่างส่วนต่างๆ คุณสามารถปรับแต่งเนื้อหาและคุณสมบัติของส่วนตามความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อยสำหรับเนื้อหาคำต่อท้ายส่วน

#### ถาม: ข้อกำหนดเบื้องต้นในการเพิ่มเนื้อหา Word ลงในส่วนเฉพาะของเอกสาร Word โดยใช้ Aspose.Words for .NET มีอะไรบ้าง

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ

#### ถาม: จะสร้างเอกสารและตัวสร้างใหม่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อต้องการสร้างเอกสารและตัวสร้างใหม่ใน Aspose.Words สำหรับ .NET คุณสามารถใช้โค้ดต่อไปนี้ ที่นี่เราสร้างอินสแตนซ์ของ`Document` ชั้นเรียนและที่เกี่ยวข้อง`DocumentBuilder` ตัวสร้างเพื่อสร้างเอกสาร:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### ถาม: ฉันจะเพิ่มเนื้อหาลงในส่วนของเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเพิ่มเนื้อหาไปยังส่วนต่างๆ ของเอกสารใน Aspose.Words สำหรับ .NET คุณสามารถใช้`DocumentBuilder` ตัวสร้าง ในตัวอย่างนี้ เรากำลังเพิ่มเนื้อหาลงในส่วนต่างๆ สี่ส่วน:

```csharp
builder. Writen("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello22");
doc.AppendChild(new Section(doc));
builder. Writen("Hello3");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello45");
```

#### ถาม: จะเพิ่มและแทรกเนื้อหาระหว่างส่วนต่างๆ ใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการเพิ่มและแทรกเนื้อหาระหว่างส่วนต่างๆ ใน Aspose.Words สำหรับ .NET คุณต้องเลือกส่วนเฉพาะที่คุณต้องการเพิ่มเนื้อหา ในตัวอย่างนี้ เราเพิ่มเนื้อหาของส่วนแรกไปที่จุดเริ่มต้นของส่วนที่สาม จากนั้นเราเพิ่มเนื้อหาของส่วนที่สองที่ส่วนท้ายของส่วนที่สาม:

```csharp
Section section = doc.Sections[2];

Section sectionToPrepend = doc.Sections[0];
section.PrependContent(sectionToPrepend);

Section sectionToAppend = doc.Sections[1];
section.AppendContent(sectionToAppend);
```
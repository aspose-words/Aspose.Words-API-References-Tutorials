---
title: ลบส่วน
linktitle: ลบส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีลบส่วนเฉพาะออกจากเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-section/delete-section/
---

ในบทช่วยสอนนี้ เราจะแสดงวิธีลบส่วนเฉพาะของเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การลบส่วนจะมีประโยชน์สำหรับการจัดเรียงใหม่หรือการลบส่วนใดส่วนหนึ่งของเอกสารของคุณ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

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

## ขั้นตอนที่ 2: เพิ่มเนื้อหาและส่วนต่างๆ
 ต่อไปเราจะใช้`DocumentBuilder` Constructor เพื่อเพิ่มเนื้อหาและส่วนต่างๆ ให้กับเอกสาร ในตัวอย่างนี้ เรากำลังเพิ่มข้อความสองบรรทัดและสองส่วน

```csharp
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello2");
doc.AppendChild(new Section(doc));
```

## ขั้นตอนที่ 3: ลบส่วนเฉพาะ
 หากต้องการลบส่วนใดส่วนหนึ่งของเอกสาร เราจะใช้`RemoveAt` วิธีการจัดทำเอกสาร`Sections` การรวบรวมโดยระบุดัชนีของส่วนที่จะลบ

```csharp
doc.Sections.RemoveAt(0);
```

### ตัวอย่างซอร์สโค้ดสำหรับ Delete Section โดยใช้ Aspose.Words สำหรับ .NET 

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.Writeln("Hello1");
	doc.AppendChild(new Section(doc));
	builder.Writeln("Hello2");
	doc.AppendChild(new Section(doc));
	doc.Sections.RemoveAt(0);

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีลบส่วนใดส่วนหนึ่งออกจากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET การลบส่วนทำให้คุณสามารถจัดเรียงใหม่หรือลบส่วนใดส่วนหนึ่งของเอกสารของคุณได้ อย่าลังเลที่จะปรับแต่งและใช้คุณสมบัตินี้ตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: ข้อกำหนดเบื้องต้นสำหรับการลบส่วนเฉพาะในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET มีอะไรบ้าง

ตอบ: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ

#### ถาม: จะสร้างเอกสารและตัวสร้างใหม่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: เมื่อต้องการสร้างเอกสารและตัวสร้างใหม่ใน Aspose.Words สำหรับ .NET คุณสามารถใช้โค้ดต่อไปนี้ ที่นี่เราสร้างอินสแตนซ์ของ`Document` ชั้นเรียนและที่เกี่ยวข้อง`DocumentBuilder` ตัวสร้างเพื่อสร้างเอกสาร:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### ถาม: จะเพิ่มเนื้อหาและส่วนต่างๆ ลงในเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการเพิ่มเนื้อหาและส่วนต่างๆ ลงในเอกสารใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`DocumentBuilder` ตัวสร้าง ในตัวอย่างนี้ เราเพิ่มข้อความสองบรรทัดและสองส่วน:

```csharp
builder. Writen("Hello1");
doc.AppendChild(new Section(doc));
builder. Writen("Hello2");
doc.AppendChild(new Section(doc));
```

#### ถาม: จะลบส่วนเฉพาะใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการลบส่วนใดส่วนหนึ่งออกจากเอกสารใน Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`RemoveAt` วิธีการจัดทำเอกสาร`Sections` คอลเลกชัน ระบุดัชนีของส่วนที่จะลบ:

```csharp
doc.Sections.RemoveAt(0);
```
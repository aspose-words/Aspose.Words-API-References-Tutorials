---
title: ลบทุกส่วน
linktitle: ลบทุกส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีลบส่วนทั้งหมดออกจากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-section/delete-all-sections/
---
ในบทช่วยสอนนี้ เราจะบอกวิธีลบส่วนทั้งหมดออกจากเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การลบส่วนจะมีประโยชน์ในการจัดระเบียบใหม่หรือทำให้เอกสารของคุณง่ายขึ้น เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

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

## ขั้นตอนที่ 3: ลบส่วนทั้งหมด
 หากต้องการลบส่วนทั้งหมดออกจากเอกสาร เราจะใช้`Clear` วิธีการของ`Sections` การรวบรวมเอกสาร

```csharp
doc.Sections.Clear();
```

### ตัวอย่างซอร์สโค้ดสำหรับการลบส่วนทั้งหมดโดยใช้ Aspose.Words สำหรับ .NET 
```csharp

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello2");
doc.AppendChild(new Section(doc));
doc.Sections.Clear();

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีลบส่วนทั้งหมดออกจากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET การลบส่วนจะทำให้คุณสามารถจัดเรียงใหม่หรือลดความซับซ้อนของโครงสร้างของเอกสารได้ อย่าลังเลที่จะปรับแต่งและใช้คุณสมบัตินี้เพื่อตอบสนองความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: ข้อกำหนดเบื้องต้นในการลบส่วนทั้งหมดออกจากเอกสาร Word โดยใช้ Aspose.Words for .NET คืออะไร

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

#### ถาม: จะลบส่วนทั้งหมดใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการลบส่วนทั้งหมดออกจากเอกสารใน Aspose.Words สำหรับ .NET คุณสามารถใช้`Clear` วิธีการของ`Sections` การรวบรวมเอกสาร:

```csharp
doc.Sections.Clear();
```
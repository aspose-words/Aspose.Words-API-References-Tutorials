---
title: ย้ายไปยังเอกสารเริ่มต้นสิ้นสุดในเอกสาร Word
linktitle: ย้ายไปยังเอกสารเริ่มต้นสิ้นสุดในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อย้ายไปยังเอกสารเริ่มต้นและสิ้นสุดในเอกสาร Word พร้อมคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/move-to-document-start-end/
---
ในตัวอย่างนี้ เราจะสำรวจคุณลักษณะ Move To Document Start/End ของ Aspose.Words สำหรับ .NET Aspose.Words เป็นไลบรารีจัดการเอกสารที่ทรงพลังซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงเอกสาร Word โดยทางโปรแกรม คุณลักษณะ Move To Document Start/End ช่วยให้เราสามารถนำทางไปยังจุดเริ่มต้นหรือจุดสิ้นสุดของเอกสารโดยใช้คลาส DocumentBuilder

## อธิบายซอร์สโค้ดทีละขั้นตอน

มาดูซอร์สโค้ดทีละขั้นตอนเพื่อทำความเข้าใจวิธีใช้ฟีเจอร์เริ่มต้น/สิ้นสุดการย้ายไปยังเอกสารโดยใช้ Aspose.Words สำหรับ .NET


## ขั้นตอนที่ 1: การเริ่มต้นเอกสารและตัวสร้างเอกสาร

ถัดไป เริ่มต้นวัตถุ Document และ DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การย้ายไปยังการเริ่มต้นเอกสาร

หากต้องการย้ายตำแหน่งเคอร์เซอร์ไปที่จุดเริ่มต้นของเอกสาร ให้ใช้เมธอด MoveToDocumentStart ของคลาส DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## ขั้นตอนที่ 3: การย้ายไปยังส่วนท้ายของเอกสาร

หากต้องการย้ายตำแหน่งเคอร์เซอร์ไปที่จุดสิ้นสุดของเอกสาร ให้ใช้เมธอด MoveToDocumentEnd ของคลาส DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## ขั้นตอนที่ 4: ส่งออกตำแหน่งเคอร์เซอร์

คุณสามารถส่งออกตำแหน่งเคอร์เซอร์ได้โดยใช้ Console.WriteLine หรือวิธีอื่นที่ต้องการ ตัวอย่างเช่น:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### ตัวอย่างซอร์สโค้ดสำหรับการย้ายไปยังเอกสารเริ่มต้น/สิ้นสุดโดยใช้ Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ย้ายตำแหน่งเคอร์เซอร์ไปที่จุดเริ่มต้นของเอกสารของคุณ
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// ย้ายตำแหน่งเคอร์เซอร์ไปที่ส่วนท้ายของเอกสาร
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## บทสรุป

ในตัวอย่างนี้ เราได้สำรวจคุณลักษณะ Move To Document Start/End ของ Aspose.Words สำหรับ .NET เราเรียนรู้วิธีนำทางไปยังจุดเริ่มต้นและจุดสิ้นสุดของเอกสารโดยใช้คลาส DocumentBuilder คุณลักษณะนี้มีประโยชน์เมื่อประมวลผลคำโดยทางโปรแกรมด้วยเอกสาร Word และจำเป็นต้องจัดการหรือแทรกเนื้อหาในตำแหน่งเฉพาะภายในเอกสาร

### คำถามที่พบบ่อย

#### ถาม: จุดประสงค์ของฟีเจอร์ Move To Document Start/End ใน Aspose.Words for .NET คืออะไร

ตอบ: คุณลักษณะ Move To Document Start/End ใน Aspose.Words สำหรับ .NET ช่วยให้นักพัฒนาสามารถนำทางไปยังจุดเริ่มต้นหรือจุดสิ้นสุดของเอกสาร Word โดยใช้คลาส DocumentBuilder มีประโยชน์สำหรับการจัดการหรือการแทรกเนื้อหาในตำแหน่งเฉพาะภายในเอกสารโดยทางโปรแกรม

#### ถาม: ฉันสามารถใช้ฟีเจอร์นี้กับเอกสาร Word ที่มีอยู่ได้หรือไม่

ตอบ: ได้ คุณสามารถใช้ฟีเจอร์เริ่มต้น/สิ้นสุดการย้ายไปยังเอกสารกับเอกสาร Word ใหม่และที่มีอยู่ได้ เพียงแค่เริ่มต้น DocumentBuilder ด้วยวัตถุ Document ที่เหมาะสม จากนั้นใช้เมธอด MoveToDocumentStart และ MoveToDocumentEnd ดังที่แสดงในซอร์สโค้ดตัวอย่าง

#### ถาม: เมธอด DocumentBuilder.MoveToDocumentStart/MoveToDocumentEnd ส่งผลต่อเนื้อหาของเอกสารอย่างไร

ตอบ: เมธอด DocumentBuilder.MoveToDocumentStart ย้ายเคอร์เซอร์ไปที่จุดเริ่มต้นของเอกสารโดยไม่ต้องเปลี่ยนเนื้อหาที่มีอยู่ ในทำนองเดียวกัน เมธอด DocumentBuilder.MoveToDocumentEnd จะย้ายเคอร์เซอร์ไปที่ส่วนท้ายของเอกสารโดยไม่ต้องเปลี่ยนแปลงเนื้อหา

#### ถาม: ฉันสามารถดำเนินการอื่นๆ หลังจากเลื่อนเคอร์เซอร์ไปที่จุดสิ้นสุดของเอกสารได้หรือไม่

ตอบ: ได้ หลังจากเลื่อนเคอร์เซอร์ไปที่ส่วนท้ายของเอกสารแล้ว คุณสามารถใช้ DocumentBuilder ต่อไปเพื่อเพิ่มหรือแก้ไขเนื้อหาที่ตำแหน่งนั้นได้ ตำแหน่งของเคอร์เซอร์ยังคงอยู่ที่ส่วนท้ายของเอกสารจนกว่าจะถูกย้ายอย่างชัดเจน

#### ถาม: ฉันจะส่งออกตำแหน่งเคอร์เซอร์โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: คุณสามารถส่งออกตำแหน่งเคอร์เซอร์โดยใช้วิธีการต่างๆ เช่น Console.WriteLine, การบันทึก หรือกลไกเอาท์พุตอื่นๆ ที่ต้องการ ในซอร์สโค้ดตัวอย่างที่ให้มา Console.WriteLine ใช้เพื่อแสดงข้อความสำหรับจุดเริ่มต้นและจุดสิ้นสุดของเอกสาร
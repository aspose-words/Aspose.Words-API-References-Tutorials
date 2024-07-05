---
title: รายการสั่ง
linktitle: รายการสั่ง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างรายการเรียงลำดับด้วย Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/ordered-list/
---

ในตัวอย่างนี้ เราจะอธิบายวิธีใช้ฟังก์ชันรายการเรียงลำดับกับ Aspose.Words สำหรับ .NET Ordered List ช่วยให้คุณสามารถจัดระเบียบรายการตามลำดับด้วยตัวเลข

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อสร้างเอกสารใหม่

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การใช้รูปแบบรายการสั่งซื้อ

 เราจะใช้รูปแบบรายการสั่งซื้อโดยใช้ตัวสร้างเอกสาร`ApplyBulletDefault`วิธี. เรายังปรับแต่งรูปแบบการเรียงลำดับเลขได้โดยไปที่ระดับรายการและตั้งค่ารูปแบบที่เราต้องการ

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## ขั้นตอนที่ 3: การเพิ่มรายการลงในรายการ

 เราสามารถเพิ่มรายการลงในรายการโดยใช้เครื่องมือสร้างเอกสาร`Writeln` วิธี.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## ขั้นตอนที่ 4: เยื้องรายการ

 เราสามารถเยื้องรายการโดยใช้ตัวสร้างเอกสาร`ListIndent` วิธี.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

สุดท้ายเราสามารถบันทึกเอกสารในรูปแบบที่ต้องการได้

### ตัวอย่างซอร์สโค้ดสำหรับรายการสั่งซื้อด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้คุณสมบัติรายการเรียงลำดับกับ Aspose.Words สำหรับ .NET แล้ว


### คำถามที่พบบ่อย

#### ถาม: จะสร้างรายการสั่งซื้อใน Markdown ได้อย่างไร

ตอบ: หากต้องการสร้างรายการที่เรียงลำดับใน Markdown ให้เริ่มต้นแต่ละรายการด้วยตัวเลขตามด้วยจุด (`1.`, `2.`, `3.`) ตามด้วยช่องว่าง

#### ถาม: เราสามารถซ้อนรายการสั่งซื้อใน Markdown ได้หรือไม่

ตอบ: ได้ คุณสามารถซ้อนรายการที่เรียงลำดับใน Markdown ได้โดยการเพิ่มช่องว่างออฟเซ็ตสี่ช่องไว้ด้านหน้าแต่ละรายการที่ซ้อนกัน

#### ถาม: จะกำหนดหมายเลขของรายการที่เรียงลำดับได้อย่างไร

ตอบ: ใน Markdown มาตรฐาน การกำหนดหมายเลขรายการตามลำดับจะถูกสร้างขึ้นโดยอัตโนมัติ อย่างไรก็ตาม เครื่องมือแก้ไข Markdown บางตัวอนุญาตให้คุณปรับแต่งได้โดยใช้ส่วนขยายเฉพาะ

#### ถาม: รายการที่เรียงลำดับใน Markdown รองรับการเยื้องหรือไม่

ตอบ: ใช่ รายการเรียงลำดับใน Markdown รองรับการเยื้อง คุณสามารถเพิ่มกะซ้ายได้โดยใช้ช่องว่างหรือแท็บ

#### ถาม: สามารถเพิ่มลิงก์หรือข้อความอินไลน์ลงในรายการได้หรือไม่

ตอบ: ได้ คุณสามารถเพิ่มลิงก์หรือข้อความอินไลน์เพื่อแสดงรายการโดยใช้ไวยากรณ์ Markdown ที่เหมาะสมได้
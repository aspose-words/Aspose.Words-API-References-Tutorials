---
title: กฎแนวนอน
linktitle: กฎแนวนอน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกกฎแนวนอนด้วย Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/horizontal-rule/
---

ในตัวอย่างนี้ เราจะแสดงวิธีใช้ฟีเจอร์กฎแนวนอนกับ Aspose.Words สำหรับ .NET กฎแนวนอนใช้เพื่อแยกส่วนของเอกสารด้วยสายตา

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: การแทรกกฎแนวนอน

 เราสามารถแทรกกฎแนวนอนได้โดยใช้`InsertHorizontalRule` วิธีการสร้างเอกสาร

```csharp
builder. InsertHorizontalRule();
```

## ตัวอย่างซอร์สโค้ดสำหรับกฎแนวนอนด้วย Aspose.Words สำหรับ .NET

```csharp
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

// แทรกกฎแนวนอน
builder.InsertHorizontalRule();
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้ฟีเจอร์กฎแนวนอนกับ Aspose.Words สำหรับ .NET แล้ว


### คำถามที่พบบ่อย

#### ถาม: ฉันจะสร้างไม้บรรทัดแนวนอนใน Markdown ได้อย่างไร

ตอบ: หากต้องการสร้างไม้บรรทัดแนวนอนใน Markdown คุณสามารถใช้สัญลักษณ์ใดสัญลักษณ์หนึ่งต่อไปนี้บนบรรทัดว่างได้: เครื่องหมายดอกจันสามดวง (\--สามขีดกลาง (\---) หรือขีดล่างสามอัน (\---

#### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของไม้บรรทัดแนวนอนใน Markdown ได้หรือไม่

ตอบ: ใน Markdown มาตรฐาน ไม่มีวิธีปรับแต่งลักษณะของไม้บรรทัดแนวนอนได้ อย่างไรก็ตาม ตัวแก้ไขและส่วนขยาย Markdown ขั้นสูงบางตัวมีคุณสมบัติการปรับแต่งเพิ่มเติม

#### ถาม: เครื่องมือแก้ไข Markdown ทั้งหมดรองรับไม้บรรทัดแนวนอนหรือไม่

ตอบ: ใช่ โปรแกรมแก้ไข Markdown ที่ได้รับความนิยมส่วนใหญ่รองรับไม้บรรทัดแนวนอน อย่างไรก็ตาม ควรตรวจสอบเอกสารประกอบของผู้จำหน่ายเฉพาะรายเพื่อให้แน่ใจว่าได้รับการสนับสนุนเสมอ

#### ถาม: ฉันสามารถสร้างองค์ประกอบอื่นใดใน Markdown ได้บ้าง

ตอบ: นอกจากไม้บรรทัดแนวนอนแล้ว คุณสามารถสร้างชื่อเรื่อง ย่อหน้า รายการ ลิงก์ รูปภาพ ตาราง และอื่นๆ ใน Markdown ได้
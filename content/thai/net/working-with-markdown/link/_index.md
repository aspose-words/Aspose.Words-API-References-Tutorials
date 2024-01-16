---
title: ลิงค์
linktitle: ลิงค์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกลิงก์ด้วย Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/link/
---

ในตัวอย่างนี้ เราจะแนะนำวิธีใช้ฟีเจอร์ลิงก์กับ Aspose.Words สำหรับ .NET ให้คุณทราบ ลิงก์ใช้เพื่อสร้างข้อมูลอ้างอิงที่สามารถคลิกไปยังเว็บไซต์หรือเอกสารอื่นๆ

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: การแทรกลิงก์

 เราสามารถแทรกลิงค์โดยใช้`Insertlink` วิธีการสร้างเอกสาร เราจำเป็นต้องระบุข้อความลิงก์ที่นี่ "Aspose" รวมถึง URL ปลายทาง

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", เท็จ);
```

### ตัวอย่างซอร์สโค้ดสำหรับลิงก์กับ Aspose.Words สำหรับ .NET


```csharp
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

// ใส่ลิงค์.
builder.Insertlink("Aspose", "https://www.aspose.com", เท็จ);
```
ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้คุณสมบัติลิงก์กับ Aspose.Words สำหรับ .NET แล้ว


### คำถามที่พบบ่อย

#### ถาม: ฉันจะลิงก์ไปยัง URL ใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการลิงก์ไปยังที่อยู่ URL ใน Aspose.Words คุณสามารถใช้`<a>` แท็กด้วย`href` แอตทริบิวต์ที่มีที่อยู่ URL ตัวอย่างเช่นคุณสามารถใช้`<a href="https://www.aspose.com">Click Here</a>` เพื่อไฮเปอร์ลิงก์ไปยัง URL "https://www.example.com " พร้อมข้อความที่แสดง "คลิกที่นี่"

#### ถาม: เป็นไปได้ไหมที่จะลิงก์ไปยังบุ๊กมาร์กภายในใน Aspose.Words

 ตอบ: ได้ คุณสามารถลิงก์ไปยังบุ๊กมาร์กภายในใน Aspose.Words ได้ คุณสามารถใช้`<a>` แท็กด้วย`href` แอตทริบิวต์ที่มีชื่อของบุ๊กมาร์กนำหน้าด้วยแฮช (#) ตัวอย่างเช่น,`<a href="#bookmark1">Go to bookmark 1</a>` จะเชื่อมโยงไปยังบุ๊กมาร์กชื่อ "bookmark1" ในเอกสาร

#### ถาม: ฉันจะปรับแต่งข้อความที่แสดงของลิงก์ใน Aspose.Words ได้อย่างไร

ตอบ: หากต้องการปรับแต่งข้อความที่แสดงของลิงก์ใน Aspose.Words คุณสามารถแก้ไขเนื้อหาระหว่าง`<a>` แท็ก ตัวอย่างเช่น,`<a href="https://www.aspose.com">Click here</a>` จะแสดงข้อความ "คลิกที่นี่" เป็นไฮเปอร์ลิงก์

#### ถาม: ฉันสามารถระบุเป้าหมายสำหรับลิงก์ใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถระบุเป้าหมายสำหรับลิงก์ใน Aspose.Words ได้โดยใช้`target` คุณลักษณะของ`<a>` แท็ก ตัวอย่างเช่น,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` จะเปิดลิงค์ในหน้าต่างหรือแท็บใหม่
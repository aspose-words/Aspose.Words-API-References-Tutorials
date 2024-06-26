---
title: สร้างลิงค์ใน Word
linktitle: สร้างลิงค์ใน Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีสร้างลิงก์ในคำระหว่างกล่องข้อความในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-textboxes/create-a-link/
---
คำแนะนำทีละขั้นตอนนี้อธิบายวิธีสร้างลิงก์ใน Word ระหว่างกล่องข้อความสองกล่องในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET คุณจะได้เรียนรู้วิธีกำหนดค่าเอกสาร สร้างรูปร่างของกล่องข้อความ เข้าถึงกล่องข้อความ ตรวจสอบความถูกต้องของเป้าหมายลิงก์ และสุดท้ายก็สร้างตัวลิงก์เอง

## ขั้นตอนที่ 1: การตั้งค่าเอกสารและสร้างรูปร่างกล่องข้อความ

 ในการเริ่มต้น เราต้องตั้งค่าเอกสารและสร้างกล่องข้อความสองรูปร่าง รหัสต่อไปนี้เตรียมใช้งานอินสแตนซ์ใหม่ของ`Document` และสร้างกล่องข้อความสองรูปร่าง:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## ขั้นตอนที่ 2: สร้างลิงก์ระหว่างกล่องข้อความ

ตอนนี้เราจะสร้างการเชื่อมโยงระหว่างกล่องข้อความทั้งสองโดยใช้`IsValidLinkTarget()` วิธีการและ`Next` คุณสมบัติของกล่องข้อความแรก

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 ที่`IsValidLinkTarget()` วิธีการตรวจสอบว่ากล่องข้อความที่สองสามารถเป็นเป้าหมายที่ถูกต้องสำหรับลิงก์ของกล่องข้อความแรกหรือไม่ หากการตรวจสอบสำเร็จ ระบบ`Next` คุณสมบัติของกล่องข้อความแรกถูกตั้งค่าเป็นกล่องข้อความที่สอง เพื่อสร้างการเชื่อมโยงระหว่างทั้งสอง

### ตัวอย่างซอร์สโค้ดเพื่อเชื่อมโยงกับ Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```
## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีสร้างลิงก์ระหว่างกล่องข้อความสองกล่องในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การใช้คำแนะนำทีละขั้นตอนนี้ทำให้คุณสามารถตั้งค่าเอกสาร สร้างรูปร่างของกล่องข้อความ เข้าถึงกล่องข้อความ ตรวจสอบความถูกต้องของเป้าหมายลิงก์ และสร้างลิงก์ในที่สุด

### คำถามที่พบบ่อยสำหรับการสร้างลิงค์ใน Word

#### ถาม: ไลบรารีใดที่ใช้ในการเชื่อมโยงกล่องข้อความใน Word โดยใช้ Aspose.Words for .NET

ตอบ: หากต้องการลิงก์กล่องข้อความใน Word โดยใช้ Aspose.Words สำหรับ .NET ไลบรารีที่ใช้คือ Aspose.Words สำหรับ .NET

#### ถาม: จะตรวจสอบได้อย่างไรว่าเป้าหมายลิงก์นั้นถูกต้องก่อนสร้างลิงก์

 ตอบ: ก่อนที่จะสร้างลิงก์ระหว่างกล่องข้อความ คุณสามารถใช้ไฟล์`IsValidLinkTarget()` วิธีการตรวจสอบว่าเป้าหมายลิงก์ถูกต้องหรือไม่ วิธีการนี้จะตรวจสอบว่ากล่องข้อความที่สองสามารถเป็นเป้าหมายที่ถูกต้องสำหรับลิงก์จากกล่องข้อความแรกหรือไม่

#### ถาม: จะสร้างลิงค์ระหว่างกล่องข้อความสองกล่องได้อย่างไร

 ตอบ: หากต้องการสร้างลิงก์ระหว่างสองกล่องข้อความ คุณต้องตั้งค่า`Next` คุณสมบัติของกล่องข้อความแรกไปยังกล่องข้อความที่สอง ตรวจสอบให้แน่ใจว่าคุณได้ตรวจสอบความถูกต้องของเป้าหมายลิงก์ล่วงหน้าโดยใช้`IsValidLinkTarget()` วิธี.

#### ถาม: เป็นไปได้ไหมที่จะสร้างลิงก์ระหว่างองค์ประกอบอื่นที่ไม่ใช่กล่องข้อความ

ตอบ: ได้ การใช้ไลบรารี Aspose.Words สำหรับ .NET ทำให้สามารถสร้างลิงก์ระหว่างองค์ประกอบต่างๆ ได้ เช่น ย่อหน้า ตาราง รูปภาพ ฯลฯ กระบวนการจะแตกต่างกันไปขึ้นอยู่กับรายการเฉพาะที่คุณต้องการเชื่อมโยง

#### ถาม: ฟังก์ชันอื่นใดที่สามารถเพิ่มลงในกล่องข้อความใน Word โดยใช้ Aspose.Words for .NET ได้

ตอบ: ด้วย Aspose.Words สำหรับ .NET คุณสามารถเพิ่มคุณสมบัติอื่นๆ มากมายให้กับกล่องข้อความ เช่น การจัดรูปแบบข้อความ การเพิ่มรูปภาพ การเปลี่ยนสไตล์ ฯลฯ คุณสามารถสำรวจเอกสารประกอบ Aspose.Words สำหรับ .NET เพื่อค้นหาคุณสมบัติทั้งหมดที่มี
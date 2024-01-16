---
title: แบ่งลิงก์ไปข้างหน้าในเอกสาร Word
linktitle: แบ่งลิงก์ไปข้างหน้าในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแยกลิงก์ไปข้างหน้าในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-textboxes/break-a-link/
---

Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งนำเสนอคุณลักษณะต่างๆ สำหรับการประมวลผลคำด้วยเอกสาร Microsoft Word โดยทางโปรแกรม หนึ่งในคุณสมบัติที่มีประโยชน์คือความสามารถในการแยกลิงก์ไปข้างหน้าในเอกสารคำ ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ดในภาษา C# ที่สาธิตวิธีแยกลิงก์ไปข้างหน้าในเอกสาร word โดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: ดูตัวอย่างซอร์สโค้ด C#

ซอร์สโค้ด C# ที่ให้มามุ่งเน้นไปที่ฟีเจอร์ "Break A Link" ของ Aspose.Words สำหรับ .NET โดยจะแสดงวิธีแบ่งลิงก์ในรูปร่างกล่องข้อความภายในเอกสาร โค้ดนี้นำเสนอสถานการณ์ต่างๆ ในการทำลายลิงก์ และให้คำแนะนำที่ชัดเจนเกี่ยวกับวิธีการบรรลุผลลัพธ์ที่ต้องการ

## ขั้นตอนที่ 2: การตั้งค่าเอกสารและสร้างรูปร่างกล่องข้อความ

 ในการเริ่มต้น เราต้องตั้งค่าเอกสารและสร้างรูปร่างกล่องข้อความ รหัสต่อไปนี้เตรียมใช้งานอินสแตนซ์ใหม่ของ`Document` คลาสและสร้างรูปร่างกล่องข้อความ:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## ขั้นตอนที่ 3: แบ่งลิงก์ไปข้างหน้าในกล่องข้อความ

 หากต้องการแยกลิงก์ไปข้างหน้าในกล่องข้อความ เราสามารถใช้ไฟล์`BreakForwardLink()` วิธี. วิธีนี้จะตัดการเชื่อมโยงไปยังรูปร่างถัดไปในลำดับ รหัสต่อไปนี้แสดงวิธีการทำลายลิงค์ไปข้างหน้า:

```csharp
textBox.BreakForwardLink();
```

## ขั้นตอนที่ 4: ทำลายลิงก์ไปข้างหน้าโดยการตั้งค่าว่าง

 หรืออีกทางหนึ่ง เราสามารถทำลายลิงก์ไปข้างหน้าโดยการตั้งค่ากล่องข้อความ`Next`ทรัพย์สินเพื่อ`null`. วิธีนี้จะลบการเชื่อมต่อกับรูปร่างถัดไปอย่างมีประสิทธิภาพ รหัสต่อไปนี้แสดงให้เห็นถึงแนวทางนี้:

```csharp
textBox. Next = null;
```

## ขั้นตอนที่ 5: ทำลายลิงก์ที่นำไปสู่กล่องข้อความ

 ในบางกรณี เราจำเป็นต้องตัดลิงก์ที่นำไปสู่รูปร่างกล่องข้อความ เราสามารถทำได้โดยการเรียก`BreakForwardLink()` วิธีการบน`Previous` แบบฟอร์มซึ่งแบ่งลิงก์ไปยังกล่องข้อความ นี่คือตัวอย่างวิธีทำลายลิงก์ดังกล่าว:

```csharp
textBox.Previous?.BreakForwardLink();
```

### ตัวอย่างซอร์สโค้ดสำหรับการทำลายลิงก์ด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// แบ่งลิงค์ไปข้างหน้า
textBox.BreakForwardLink();

// ทำลายลิงค์ไปข้างหน้าโดยการตั้งค่าว่าง
textBox. Next = null;

// ตัดลิงก์ที่นำไปสู่กล่องข้อความนี้
textBox.Previous?.BreakForwardLink();
```

## บทสรุป

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีทำลายลิงก์เปลี่ยนเส้นทางในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนในคู่มือนี้ คุณสามารถตั้งค่าเอกสาร สร้างรูปร่างกล่องข้อความ และทำลายลิงก์การเปลี่ยนเส้นทางโดยใช้วิธีการต่างๆ

### คำถามที่พบบ่อยสำหรับลิงก์ไปข้างหน้าในเอกสาร word

#### ถาม: ไลบรารีใดที่ใช้ในการทำลายลิงก์เปลี่ยนเส้นทางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

ตอบ: หากต้องการหยุดลิงก์การเปลี่ยนเส้นทางในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ไลบรารีที่ใช้คือ Aspose.Words สำหรับ .NET

#### ถาม: จะหยุดลิงก์เปลี่ยนเส้นทางในกล่องข้อความได้อย่างไร

 ตอบ: หากต้องการแยกลิงก์ไปข้างหน้าในกล่องข้อความ คุณสามารถใช้ไฟล์`BreakForwardLink()` วิธี. วิธีนี้จะตัดการเชื่อมโยงไปยังรูปร่างถัดไปในลำดับ

#### ถาม: วิธีทำลายลิงก์เปลี่ยนเส้นทางโดยการตั้งค่าว่าง

ตอบ: หรือคุณสามารถทำลายลิงก์เปลี่ยนเส้นทางได้โดยตั้งค่า`Next` คุณสมบัติของกล่องข้อความถึง`null`. วิธีนี้จะลบการเชื่อมต่อกับรูปร่างถัดไปอย่างมีประสิทธิภาพ

#### ถาม: จะทำลายลิงค์ที่นำไปสู่กล่องข้อความได้อย่างไร

 ตอบ: ในบางกรณี คุณจะต้องทำลายลิงก์ที่นำไปสู่กล่องข้อความ คุณสามารถบรรลุสิ่งนี้ได้โดยโทรไปที่`BreakForwardLink()` วิธีการบน`Previous` แบบฟอร์มซึ่งแบ่งลิงก์ไปยังกล่องข้อความ

#### ถาม: เราสามารถทำลายลิงก์เปลี่ยนเส้นทางบนองค์ประกอบอื่นที่ไม่ใช่กล่องข้อความได้หรือไม่

ตอบ: ได้ ด้วย Aspose.Words สำหรับ .NET คุณสามารถหยุดลิงก์เปลี่ยนเส้นทางในองค์ประกอบต่างๆ เช่น ย่อหน้า ตาราง รูปภาพ ฯลฯ กระบวนการอาจแตกต่างกันไปขึ้นอยู่กับรายการเฉพาะที่คุณต้องการตัดลิงก์
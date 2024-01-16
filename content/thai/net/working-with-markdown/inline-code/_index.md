---
title: รหัสอินไลน์
linktitle: รหัสอินไลน์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกโค้ดในบรรทัดด้วย Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/working-with-markdown/inline-code/
---

ในตัวอย่างนี้ เราจะอธิบายวิธีใช้ฟีเจอร์โค้ดอินไลน์กับ Aspose.Words สำหรับ .NET ให้คุณทราบ Inline Code ใช้เพื่อแสดงส่วนของโค้ดภายในย่อหน้าด้วยสายตา

## ขั้นตอนที่ 1: การใช้ตัวสร้างเอกสาร

ขั้นแรก เราจะใช้เครื่องมือสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสารของเรา

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ขั้นตอนที่ 2: เพิ่มสไตล์สำหรับโค้ดอินไลน์

 เราจะเพิ่มสไตล์ที่กำหนดเองสำหรับโค้ดอินไลน์โดยใช้`Styles.Add` วิธีการของ`Document` วัตถุ. ในตัวอย่างนี้ เรากำลังสร้างสไตล์ที่เรียกว่า "InlineCode" สำหรับโค้ดอินไลน์ที่มี backtick เริ่มต้น

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## ขั้นตอนที่ 3: เพิ่มโค้ดอินไลน์

ตอนนี้เราสามารถเพิ่มโค้ดอินไลน์โดยใช้สไตล์ที่กำหนดเอง "InlineCode" ในตัวอย่างนี้ เราเพิ่มข้อความสองชิ้นโดยมีจำนวน backtick ต่างกัน

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### ตัวอย่างซอร์สโค้ดสำหรับ Inline Code พร้อม Aspose.Words สำหรับ .NET

```csharp
// ใช้ตัวสร้างเอกสารเพื่อเพิ่มเนื้อหาลงในเอกสาร
DocumentBuilder builder = new DocumentBuilder();

// พลาดจำนวน backticks โดยจะใช้ backtick หนึ่งอันเป็นค่าเริ่มต้น
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// จะมีแบ็คติ๊ก 3 อัน
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

ขอแสดงความยินดี! ตอนนี้คุณได้เรียนรู้วิธีใช้ฟังก์ชันโค้ดอินไลน์กับ Aspose.Words สำหรับ .NET แล้ว


### คำถามที่พบบ่อย

#### ถาม: ฉันจะใช้โค้ดอินไลน์ใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการใช้โค้ดอินไลน์ใน Aspose.Words คุณสามารถใช้แท็กที่เหมาะสมเพื่อล้อมรอบข้อความที่จะจัดรูปแบบเป็นโค้ดอินไลน์ได้ ตัวอย่างเช่น คุณสามารถใช้`<code>` หรือ`<kbd>` แท็กเพื่อล้อมรอบข้อความที่จะจัดรูปแบบเป็นโค้ดอินไลน์

#### ถาม: เป็นไปได้หรือไม่ที่จะระบุแบบอักษรหรือสีของโค้ดอินไลน์ใน Aspose.Words

 ตอบ: ได้ คุณสามารถระบุแบบอักษรหรือสีของโค้ดอินไลน์ใน Aspose.Words ได้ คุณสามารถใช้`Font.Name` และ`Font.Color` คุณสมบัติของ`Run` วัตถุเพื่อตั้งค่าแบบอักษรและสีของโค้ดอินไลน์ ตัวอย่างเช่นคุณสามารถใช้`run.Font.Name = "Courier New"` เพื่อระบุแบบอักษรสำหรับโค้ดอินไลน์และ`run.Font.Color = Color.Blue`เพื่อระบุสี

#### ถาม: ฉันสามารถใช้โค้ดอินไลน์ในย่อหน้าที่มีองค์ประกอบข้อความอื่นๆ ได้หรือไม่

 ตอบ: ได้ คุณสามารถใช้โค้ดอินไลน์ในย่อหน้าที่มีองค์ประกอบข้อความอื่นๆ ได้ คุณสามารถสร้างได้หลายรายการ`Run` วัตถุเพื่อแสดงส่วนต่างๆ ของย่อหน้า จากนั้นใช้แท็กโค้ดอินไลน์เพื่อจัดรูปแบบเฉพาะบางส่วนเป็นโค้ดอินไลน์ จากนั้นคุณสามารถเพิ่มลงในย่อหน้าได้โดยใช้`Paragraph.AppendChild(run)` วิธี.
---
title: แทนที่ไฮเปอร์ลิงก์
linktitle: แทนที่ไฮเปอร์ลิงก์
second_title: Aspose.Words API การประมวลผลเอกสาร
description: แทนที่ไฮเปอร์ลิงก์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับการแทนที่ไฮเปอร์ลิงก์
type: docs
weight: 10
url: /th/net/working-with-fields/replace-hyperlinks/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ต่อไปนี้เพื่อแทนที่ไฮเปอร์ลิงก์โดยใช้ฟังก์ชัน Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words ไว้ในโปรเจ็กต์ของคุณก่อนที่จะใช้โค้ดนี้

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารของคุณที่มี`Hyperlinks.docx` ไฟล์.

## ขั้นตอนที่ 2: โหลดเอกสารที่มีไฮเปอร์ลิงก์

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 ที่นี่เรากำลังสร้างอินสแตนซ์ของ`Document` คลาสจากไฟล์ที่ระบุ

## ขั้นตอนที่ 3: เรียกดูฟิลด์เพื่อค้นหาไฮเปอร์ลิงก์

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // ไฮเปอร์ลิงก์บางรายการอาจเป็นในเครื่อง (ลิงก์ไปยังบุ๊กมาร์กภายในเอกสาร) เราก็ไม่สนใจ
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 การวนซ้ำนี้จะผ่านทุกช่องในเอกสารเพื่อค้นหาช่องประเภทต่างๆ`FieldType.FieldHyperlink` . เมื่อพบฟิลด์ประเภทนี้แล้ว เราจะตรวจสอบว่าเป็นลิงก์ในเครื่องหรือไม่โดยการตรวจสอบ`SubAddress` คุณสมบัติ. ถ้าไม่เช่นนั้น เราจะแทนที่ที่อยู่ลิงก์ด้วย`"http://www.aspose.com"` และผลลัพธ์ด้วย`"Aspose - The .NET & Java Component Editor"`.

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

สุดท้าย เราจะบันทึกเอกสารที่แก้ไขด้วยไฮเปอร์ลิงก์ที่ถูกแทนที่ไปยังไฟล์ที่ระบุ

### ตัวอย่างซอร์สโค้ดเพื่อแทนที่ไฮเปอร์ลิงก์ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // ไฮเปอร์ลิงก์บางรายการอาจเป็นในเครื่อง (ลิงก์ไปยังบุ๊กมาร์กภายในเอกสาร) เราก็ไม่สนใจ
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

นี่คือซอร์สโค้ดตัวอย่างเพื่อแทนที่ไฮเปอร์ลิงก์ในเอกสารโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะแทนที่ไฮเปอร์ลิงก์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: หากต้องการแทนที่ไฮเปอร์ลิงก์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถใช้ไฟล์`Document.Range.Replace`วิธีการระบุข้อความที่จะค้นหาและข้อความแทนที่ ตรวจสอบให้แน่ใจว่าใช้ตัวเลือกที่เหมาะสมเพื่อตั้งค่าการค้นหาและแทนที่พารามิเตอร์

#### ถาม: เป็นไปได้ไหมที่จะแทนที่ไฮเปอร์ลิงก์บางตัวในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET

ตอบ: ได้ คุณสามารถแทนที่ไฮเปอร์ลิงก์บางตัวในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ได้ คุณสามารถกรองไฮเปอร์ลิงก์ที่จะแทนที่ได้โดยใช้เกณฑ์เฉพาะ เช่น URL ลิงก์ ข้อความลิงก์ หรือคุณสมบัติอื่นๆ ที่เกี่ยวข้อง จากนั้นคุณสามารถใช้การแทนที่กับไฮเปอร์ลิงก์ที่ตรงกันเท่านั้น

#### ถาม: ฉันจะเพิกเฉยต่อไฮเปอร์ลิงก์ในส่วนหัว ส่วนท้าย หรือเชิงอรรถเมื่อแทนที่ด้วย Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการละเว้นไฮเปอร์ลิงก์ในส่วนหัว ส่วนท้าย หรือเชิงอรรถเมื่อแทนที่ด้วย Aspose.Words สำหรับ .NET คุณสามารถใช้ตัวเลือกการค้นหาขั้นสูงและระบุขีดจำกัดการค้นหาที่เหมาะสมได้ ตัวอย่างเช่น คุณสามารถจำกัดการค้นหาให้อยู่ในส่วนหลักของเอกสารและยกเว้นส่วนหัว ส่วนท้าย หรือเชิงอรรถได้

#### ถาม: เป็นไปได้ไหมที่จะแทนที่ไฮเปอร์ลิงก์ด้วยลิงก์ภายในไปยังส่วนอื่นๆ ของเอกสาร

 ตอบ: ได้ คุณสามารถแทนที่ไฮเปอร์ลิงก์ด้วยลิงก์ภายในไปยังส่วนอื่นๆ ของเอกสารด้วย Aspose.Words สำหรับ .NET คุณสามารถใช้แองเคอร์หรือรหัสข้อความเพื่อสร้างลิงก์ภายใน จากนั้นแทนที่ด้วย`Document.Range.Replace` วิธีการพร้อมตัวเลือกที่เหมาะสม

#### ถาม: การแทนที่ไฮเปอร์ลิงก์ด้วย Aspose.Words สำหรับ .NET จะรักษาคุณสมบัติของลิงก์ เช่น สีหรือสไตล์หรือไม่

ตอบ: ได้ เมื่อแทนที่ไฮเปอร์ลิงก์ด้วย Aspose.Words สำหรับ .NET คุณสมบัติลิงก์ เช่น สีหรือสไตล์จะยังคงอยู่ คุณสามารถระบุคุณสมบัติการจัดรูปแบบเดียวกันในข้อความแทนที่เพื่อให้ได้ผลลัพธ์ที่สอดคล้องกัน
---
title: ละเว้นกล่องข้อความ
linktitle: ละเว้นกล่องข้อความ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: รวมเอกสาร Word เข้ากับ Aspose.Words สำหรับ .NET เพื่อให้มั่นใจว่าการจัดรูปแบบกล่องข้อความจะยังคงอยู่ ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อการประมวลผลเอกสารที่ราบรื่น
type: docs
weight: 10
url: /th/net/join-and-append-documents/ignore-text-boxes/
---
## การแนะนำ

ยินดีต้อนรับสู่บทช่วยสอนโดยละเอียดเกี่ยวกับการใช้ Aspose.Words สำหรับ .NET เพื่อรวมเอกสาร Word โดยไม่สนใจกล่องข้อความ หากคุณต้องการปรับปรุงการประมวลผลเอกสารของคุณ และให้แน่ใจว่าการจัดรูปแบบของกล่องข้อความยังคงอยู่ แสดงว่าคุณมาถูกที่แล้ว มาดูคำแนะนำทีละขั้นตอนนี้กันดีกว่า

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:

1.  Aspose.Words สำหรับ .NET: ดาวน์โหลด[ที่นี่](https://releases.aspose.com/words/net/).
2. .NET Development Environment: Visual Studio หรือ IDE ที่ต้องการอื่นๆ
3. ความรู้พื้นฐานของ C#: ความเข้าใจแนวคิดการเขียนโปรแกรมพื้นฐานใน C#

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Importing;
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ขั้นแรก ตรวจสอบให้แน่ใจว่าโครงการของคุณได้รับการตั้งค่าอย่างถูกต้อง เปิด IDE ของคุณ สร้างโปรเจ็กต์ใหม่ และติดตั้งไลบรารี Aspose.Words สำหรับ .NET ผ่าน NuGet Package Manager

### วิธีการติดตั้ง Aspose.Words

1. เปิด NuGet Package Manager ใน IDE ของคุณ
2. ค้นหา "Aspose.Words"
3. คลิกที่ "ติดตั้ง"

## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสาร

ถัดไป ระบุไดเร็กทอรีที่มีเอกสารต้นทางและปลายทางของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: โหลดเอกสาร

ตอนนี้ โหลดทั้งเอกสารต้นทางและปลายทางลงในโปรเจ็กต์ของคุณ

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกการนำเข้า

 เพื่อให้แน่ใจว่าการจัดรูปแบบของกล่องข้อความยังคงอยู่ ให้ตั้งค่า`IgnoreTextBoxes` ตัวเลือกในการ`false`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## ขั้นตอนที่ 5: เริ่มต้นผู้นำเข้าโหนด

 เริ่มต้น`NodeImporter` เพื่อนำเข้าโหนดจากเอกสารต้นทางไปยังเอกสารปลายทาง

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## ขั้นตอนที่ 6: นำเข้าย่อหน้าจากเอกสารต้นฉบับ

ดึงย่อหน้าทั้งหมดจากส่วนแรกของเอกสารต้นฉบับ

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
```

## ขั้นตอนที่ 7: ผนวกย่อหน้าที่นำเข้าเข้ากับเอกสารปลายทาง

วนซ้ำแต่ละย่อหน้าแล้วผนวกเข้ากับเอกสารปลายทาง

```csharp
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## ขั้นตอนที่ 8: บันทึกเอกสารที่ผสาน

สุดท้าย ให้บันทึกเอกสารที่ผสานด้วยชื่อใหม่เพื่อหลีกเลี่ยงการเขียนทับไฟล์ต้นฉบับ

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

## บทสรุป

คุณได้รวมเอกสาร Word สองเอกสารเข้าด้วยกันโดยใช้ Aspose.Words สำหรับ .NET สำเร็จ พร้อมทั้งตรวจสอบให้แน่ใจว่ากล่องข้อความจะไม่ถูกละเลยในระหว่างการนำเข้า กระบวนการนี้มีคุณค่าอย่างยิ่งในการรักษาความสมบูรณ์ของการจัดรูปแบบของเอกสารของคุณ ไม่ว่าคุณจะจัดการกับรายงาน สัญญา หรือเอกสารประเภทอื่นๆ Aspose.Words สำหรับ .NET จะทำให้กระบวนการราบรื่น

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
 Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง จัดการ และแปลงเอกสาร Word ภายในแอปพลิเคชัน .NET[เรียนรู้เพิ่มเติม](https://reference.aspose.com/words/net/).

### ฉันสามารถลองใช้ Aspose.Words สำหรับ .NET ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Words สำหรับ .NET ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

### ฉันจะหาเอกสารรายละเอียดเพิ่มเติมได้จากที่ไหน?
 คุณสามารถค้นหาเอกสารที่ครอบคลุมได้[ที่นี่](https://reference.aspose.com/words/net/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words สำหรับ .NET ได้อย่างไร
 สำหรับการสนับสนุน โปรดไปที่ฟอรัม Aspose[ที่นี่](https://forum.aspose.com/c/words/8).

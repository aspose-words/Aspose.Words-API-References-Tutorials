---
title: ส่งออกไปยัง Markdown ด้วยการจัดตำแหน่งเนื้อหาตาราง
linktitle: ส่งออกไปยัง Markdown ด้วยการจัดตำแหน่งเนื้อหาตาราง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีส่งออกเอกสาร Word ไปยัง Markdown ด้วยตารางที่จัดเรียงโดยใช้ Aspose.Words สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อให้ได้ตาราง Markdown ที่สมบูรณ์แบบ
type: docs
weight: 10
url: /th/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## การแนะนำ

สวัสดี! เคยสงสัยบ้างไหมว่าจะส่งออกเอกสาร Word ของคุณเป็นรูปแบบ Markdown ด้วยตารางที่จัดแนวอย่างสมบูรณ์แบบได้อย่างไร ไม่ว่าคุณจะเป็นนักพัฒนาที่ทำงานเกี่ยวกับเอกสารหรือเพียงผู้ที่รัก Markdown คู่มือนี้เหมาะสำหรับคุณ เราจะเจาะลึกถึงสาระสำคัญของการใช้ Aspose.Words สำหรับ .NET เพื่อบรรลุเป้าหมายนี้ พร้อมที่จะเปลี่ยนตาราง Word ของคุณให้เป็นตาราง Markdown ที่จัดชิดอย่างเรียบร้อยแล้วหรือยัง? มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด มีบางสิ่งที่คุณต้องเตรียม:

1.  Aspose.Words สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณมีไลบรารี Aspose.Words สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[กำหนดหน้าเผยแพร่](https://releases.aspose.com/words/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ Visual Studio เป็นตัวเลือกยอดนิยมสำหรับการพัฒนา .NET
3. ความรู้พื้นฐานของ C#: การทำความเข้าใจ C# เป็นสิ่งสำคัญ เนื่องจากเราจะเขียนโค้ดในภาษานี้
4. ตัวอย่างเอกสาร Word: มีเอกสาร Word ที่คุณสามารถใช้สำหรับการทดสอบ

## นำเข้าเนมสเปซ

ก่อนที่เราจะเริ่มเขียนโค้ด เรามานำเข้าเนมสเปซที่จำเป็นก่อน สิ่งเหล่านี้จะทำให้เราสามารถเข้าถึงคลาส Aspose.Words และวิธีการที่เราจะใช้

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: เริ่มต้นเอกสารและ DocumentBuilder

ก่อนอื่น เราต้องสร้างเอกสาร Word ใหม่และเริ่มต้นไฟล์`DocumentBuilder` วัตถุเพื่อเริ่มสร้างเอกสารของเรา

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";

// สร้างเอกสารใหม่
Document doc = new Document();

// เริ่มต้น DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: แทรกเซลล์และจัดแนวเนื้อหา

ต่อไป เราจะแทรกเซลล์บางเซลล์ลงในเอกสารของเราและตั้งค่าการจัดตำแหน่ง นี่เป็นสิ่งสำคัญในการรับรองว่าการส่งออก Markdown จะรักษาการจัดตำแหน่งที่ถูกต้อง

```csharp
// แทรกเซลล์และตั้งค่าการจัดตำแหน่งไปทางขวา
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// แทรกเซลล์อื่นและตั้งค่าการจัดตำแหน่งให้อยู่ตรงกลาง
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## ขั้นตอนที่ 3: ตั้งค่าการจัดตำแหน่งเนื้อหาตารางสำหรับการส่งออก Markdown

 ตอนนี้ก็ถึงเวลากำหนดค่า`MarkdownSaveOptions` เพื่อควบคุมการจัดตำแหน่งของเนื้อหาตารางในไฟล์ Markdown ที่ส่งออก เราจะบันทึกเอกสารด้วยการตั้งค่าการจัดตำแหน่งที่แตกต่างกันเพื่อดูว่ามันทำงานอย่างไร

```csharp
// สร้างวัตถุ MarkdownSaveOptions
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// บันทึกเอกสารโดยจัดชิดซ้าย
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// เปลี่ยนการจัดตำแหน่งไปทางขวาแล้วบันทึก
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// เปลี่ยนการจัดตำแหน่งให้อยู่กึ่งกลางและบันทึก
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## ขั้นตอนที่ 4: ใช้การจัดตำแหน่งเนื้อหาตารางอัตโนมัติ

 ที่`Auto`ตัวเลือกการจัดตำแหน่งจะใช้การจัดตำแหน่งจากย่อหน้าแรกในคอลัมน์ตารางที่เกี่ยวข้อง ซึ่งจะมีประโยชน์เมื่อคุณมีการจัดแนวแบบผสมในตารางเดียว

```csharp
// ตั้งค่าการจัดตำแหน่งเป็นอัตโนมัติ
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// บันทึกเอกสารด้วยการจัดตำแหน่งอัตโนมัติ
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## บทสรุป

และคุณก็ได้แล้ว! การส่งออกเอกสาร Word ไปยัง Markdown ด้วยตารางที่จัดแนวโดยใช้ Aspose.Words สำหรับ .NET เป็นเรื่องง่ายเมื่อคุณรู้วิธีดำเนินการแล้ว ไลบรารีอันทรงพลังนี้ทำให้การควบคุมการจัดรูปแบบและการจัดแนวตารางของคุณเป็นเรื่องง่าย ทำให้มั่นใจได้ว่าเอกสาร Markdown ของคุณจะมีลักษณะตามที่คุณต้องการ ขอให้มีความสุขในการเขียนโค้ด!

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถสร้าง แก้ไข แปลง และส่งออกเอกสาร Word โดยทางโปรแกรม

### ฉันสามารถตั้งค่าการจัดแนวที่แตกต่างกันสำหรับคอลัมน์ต่างๆ ในตารางเดียวกันได้หรือไม่
 ใช่ โดยใช้`Auto` ตัวเลือกการจัดตำแหน่ง คุณสามารถมีการจัดตำแหน่งที่แตกต่างกันตามย่อหน้าแรกในแต่ละคอลัมน์

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Words สำหรับ .NET หรือไม่
 ใช่ Aspose.Words สำหรับ .NET จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเต็มรูปแบบ คุณจะได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผล

### เป็นไปได้หรือไม่ที่จะส่งออกองค์ประกอบเอกสารอื่น ๆ ไปยัง Markdown โดยใช้ Aspose.Words
ใช่ Aspose.Words รองรับการส่งออกองค์ประกอบต่างๆ เช่น ส่วนหัว รายการ และรูปภาพเป็นรูปแบบ Markdown

### ฉันจะรับการสนับสนุนได้ที่ไหนหากฉันประสบปัญหา
 คุณสามารถรับการสนับสนุนจาก[ฟอรั่มสนับสนุน Aspose.Words](https://forum.aspose.com/c/words/8).

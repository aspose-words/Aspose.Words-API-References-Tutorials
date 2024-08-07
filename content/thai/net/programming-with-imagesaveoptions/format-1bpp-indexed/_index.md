---
title: รูปแบบ 1Bpp จัดทำดัชนี
linktitle: รูปแบบ 1Bpp จัดทำดัชนี
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแปลงเอกสาร Word เป็นรูปภาพที่จัดทำดัชนี 1Bpp โดยใช้ Aspose.Words สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการแปลงที่ง่ายดาย
type: docs
weight: 10
url: /th/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## การแนะนำ

เคยสงสัยบ้างไหมว่าจะบันทึกเอกสาร Word เป็นภาพขาวดำโดยใช้โค้ดเพียงไม่กี่บรรทัดได้อย่างไร คุณโชคดี! วันนี้ เรากำลังเจาะลึกเคล็ดลับเล็ก ๆ น้อย ๆ ในการใช้ Aspose.Words สำหรับ .NET ที่ช่วยให้คุณแปลงเอกสารของคุณเป็นรูปภาพที่จัดทำดัชนี 1Bpp รูปแบบนี้เหมาะสำหรับการเก็บถาวร การพิมพ์แบบดิจิทัลบางประเภท หรือเมื่อคุณต้องการประหยัดพื้นที่ เราจะแจกแจงแต่ละขั้นตอนเพื่อให้ง่ายเหมือนพาย พร้อมที่จะเริ่มต้นหรือยัง? มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะทำให้มือสกปรก มีบางสิ่งที่คุณต้องเตรียม:

-  Aspose.Words สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีแล้ว คุณสามารถ[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา .NET: Visual Studio เป็นตัวเลือกที่ดี แต่คุณสามารถใช้สภาพแวดล้อมใดก็ได้ที่คุณพอใจ
- ความรู้พื้นฐานของ C#: ไม่ต้องกังวล เราจะทำให้มันเรียบง่าย แต่ความคุ้นเคยเล็กน้อยกับ C# จะช่วยได้
- เอกสาร Word: เตรียมเอกสาร Word ตัวอย่างพร้อมที่จะแปลง

## นำเข้าเนมสเปซ

ก่อนอื่น เราต้องนำเข้าเนมสเปซที่จำเป็นก่อน นี่เป็นสิ่งสำคัญเนื่องจากช่วยให้เราสามารถเข้าถึงคลาสและวิธีการที่เราต้องการจาก Aspose.Words

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

คุณจะต้องระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือที่เก็บเอกสาร Word ของคุณ และตำแหน่งที่จะบันทึกรูปภาพที่แปลงแล้ว

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสาร Word

 ตอนนี้ มาโหลดเอกสาร Word ลงใน Aspose.Words กัน`Document` วัตถุ. วัตถุนี้แสดงถึงไฟล์ Word ของคุณและช่วยให้คุณสามารถจัดการได้

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการบันทึกรูปภาพ

 ต่อไปเราจะต้องตั้งค่า`ImageSaveOptions`นี่คือจุดที่ความมหัศจรรย์เกิดขึ้น เราจะกำหนดค่าให้บันทึกรูปภาพในรูปแบบ PNG ด้วยโหมดสีที่จัดทำดัชนี 1Bpp

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: นี่เป็นการระบุว่าเราต้องการบันทึกเอกสารเป็นรูปภาพ PNG
- PageSet(1): สิ่งนี้บ่งชี้ว่าเรากำลังแปลงเฉพาะหน้าแรกเท่านั้น
- ImageColorMode.BlackAndWhite: นี่เป็นการตั้งค่าภาพให้เป็นขาวดำ
- ImagePixelFormat.Format1bppIndexed: ตั้งค่ารูปแบบรูปภาพเป็น 1Bpp ที่จัดทำดัชนี

## ขั้นตอนที่ 4: บันทึกเอกสารเป็นรูปภาพ

 สุดท้าย เราบันทึกเอกสารเป็นรูปภาพโดยใช้`Save` วิธีการของ`Document` วัตถุ.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## บทสรุป

และคุณก็ได้แล้ว! ด้วยโค้ดเพียงไม่กี่บรรทัด คุณก็สามารถแปลงเอกสาร Word ของคุณให้เป็นรูปภาพที่จัดทำดัชนี 1Bpp โดยใช้ Aspose.Words สำหรับ .NET วิธีการนี้มีประโยชน์อย่างเหลือเชื่อสำหรับการสร้างรูปภาพที่มีคอนทราสต์สูงและประหยัดพื้นที่จากเอกสารของคุณ ตอนนี้คุณสามารถรวมสิ่งนี้เข้ากับโปรเจ็กต์และเวิร์กโฟลว์ของคุณได้อย่างง่ายดาย ขอให้มีความสุขในการเขียนโค้ด!

## คำถามที่พบบ่อย

### รูปภาพที่จัดทำดัชนี 1Bpp คืออะไร
รูปภาพที่จัดทำดัชนี 1Bpp (1 บิตต่อพิกเซล) คือรูปแบบภาพขาวดำโดยแต่ละพิกเซลจะแสดงด้วยบิตเดียว ไม่ว่าจะเป็น 0 หรือ 1 รูปแบบนี้ประหยัดพื้นที่อย่างมาก

### ฉันสามารถแปลงเอกสาร Word หลายหน้าพร้อมกันได้หรือไม่
 ใช่คุณสามารถ ปรับเปลี่ยน`PageSet` ทรัพย์สินใน`ImageSaveOptions` เพื่อรวมหลายหน้าหรือทั้งเอกสาร

### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Words สำหรับ .NET หรือไม่
 ใช่ Aspose.Words สำหรับ .NET จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเต็มรูปแบบ คุณจะได้รับ[ใบอนุญาตชั่วคราวที่นี่](https://purchase.aspose.com/temporary-license/).

### ฉันสามารถแปลงเอกสาร Word เป็นรูปแบบรูปภาพอื่นใดได้บ้าง
 Aspose.Words รองรับรูปแบบภาพที่หลากหลาย รวมถึง JPEG, BMP และ TIFF เพียงแค่เปลี่ยน`SaveFormat` ใน`ImageSaveOptions`.

### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 คุณสามารถดูเอกสารรายละเอียดได้ที่[หน้าเอกสาร Aspose.Words สำหรับ .NET](https://reference.aspose.com/words/net/).

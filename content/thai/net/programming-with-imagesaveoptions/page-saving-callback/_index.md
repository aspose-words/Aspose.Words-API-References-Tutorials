---
title: หน้าบันทึกการโทรกลับ
linktitle: หน้าบันทึกการโทรกลับ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีบันทึกแต่ละหน้าของเอกสาร Word เป็นรูปภาพ PNG แยกต่างหากโดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำโดยละเอียดทีละขั้นตอนของเรา
type: docs
weight: 10
url: /th/net/programming-with-imagesaveoptions/page-saving-callback/
---
## การแนะนำ

เฮ้! เคยรู้สึกว่าจำเป็นต้องบันทึกแต่ละหน้าของเอกสาร Word เป็นรูปภาพแยกกันหรือไม่? บางทีคุณอาจต้องการแยกรายงานขนาดใหญ่ออกเป็นภาพที่เข้าใจง่าย หรือบางทีคุณอาจต้องสร้างภาพขนาดย่อสำหรับการดูตัวอย่าง ไม่ว่าคุณจะด้วยเหตุผลใดก็ตาม การใช้ Aspose.Words สำหรับ .NET จะทำให้งานนี้เป็นเรื่องง่าย ในคู่มือนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่าการโทรกลับเพื่อบันทึกหน้าเพื่อบันทึกแต่ละหน้าของเอกสารเป็นรูปภาพ PNG แต่ละภาพ มาดำดิ่งกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1.  Aspose.Words สำหรับ .NET: หากคุณยังไม่ได้ดาวน์โหลด ให้ดาวน์โหลดและติดตั้งจาก[ที่นี่](https://releases.aspose.com/words/net/).
2. Visual Studio: ทุกเวอร์ชันควรใช้งานได้ แต่ฉันจะใช้ Visual Studio 2019 สำหรับคำแนะนำนี้
3. ความรู้พื้นฐานของ C#: คุณจะต้องมีความเข้าใจพื้นฐานเกี่ยวกับ C# เพื่อปฏิบัติตาม

## นำเข้าเนมสเปซ

ขั้นแรก เราต้องนำเข้าเนมสเปซที่จำเป็น สิ่งนี้ช่วยให้เราเข้าถึงคลาสและวิธีการที่จำเป็นโดยไม่ต้องพิมพ์เนมสเปซแบบเต็มทุกครั้ง

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ

เอาล่ะ เริ่มต้นด้วยการกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือตำแหน่งที่เอกสาร Word ที่คุณป้อนเข้าและตำแหน่งที่ภาพที่ส่งออกจะถูกบันทึก

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารของคุณ

ต่อไป เราจะโหลดเอกสารที่คุณต้องการดำเนินการ ตรวจสอบให้แน่ใจว่าเอกสารของคุณ ("Rendering.docx") อยู่ในไดเร็กทอรีที่ระบุ

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการบันทึกรูปภาพ

เราจำเป็นต้องกำหนดค่าตัวเลือกสำหรับการบันทึกภาพ ในกรณีนี้ เรากำลังบันทึกหน้าเว็บเป็นไฟล์ PNG

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 ที่นี่,`PageSet` ระบุช่วงของหน้าที่จะบันทึก และ`PageSavingCallback` ชี้ไปที่คลาสการโทรกลับที่กำหนดเองของเรา

## ขั้นตอนที่ 4: ใช้การโทรกลับการบันทึกหน้า

ตอนนี้ ลองใช้คลาสโทรกลับที่จัดการวิธีการบันทึกแต่ละเพจ

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 คลาสนี้ประยุกต์ใช้`IPageSavingCallback` อินเตอร์เฟซและภายใน`PageSaving` วิธีที่เรากำหนดรูปแบบการตั้งชื่อสำหรับหน้าที่บันทึกไว้แต่ละหน้า

## ขั้นตอนที่ 5: บันทึกเอกสารเป็นรูปภาพ

สุดท้าย เราจะบันทึกเอกสารโดยใช้ตัวเลือกที่กำหนดค่าไว้

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## บทสรุป

และคุณก็ได้แล้ว! คุณได้ตั้งค่าการโทรกลับเพื่อบันทึกหน้าเพื่อบันทึกแต่ละหน้าของเอกสาร Word เป็นรูปภาพ PNG แยกต่างหากโดยใช้ Aspose.Words สำหรับ .NET เทคนิคนี้มีประโยชน์อย่างเหลือเชื่อสำหรับแอปพลิเคชันต่างๆ ตั้งแต่การสร้างหน้าตัวอย่างไปจนถึงการสร้างภาพแต่ละหน้าสำหรับรายงาน 

ขอให้มีความสุขในการเขียนโค้ด!

## คำถามที่พบบ่อย

### ฉันสามารถบันทึกหน้าในรูปแบบอื่นที่ไม่ใช่ PNG ได้หรือไม่  
 ได้ คุณสามารถบันทึกหน้าในรูปแบบต่างๆ เช่น JPEG, BMP และ TIFF ได้โดยการเปลี่ยน`SaveFormat` ใน`ImageSaveOptions`.

### จะทำอย่างไรถ้าฉันต้องการบันทึกเฉพาะบางหน้า?  
 คุณสามารถระบุหน้าที่คุณต้องการบันทึกได้โดยการปรับ`PageSet` พารามิเตอร์ใน`ImageSaveOptions`.

### สามารถปรับคุณภาพของภาพได้หรือไม่?  
 อย่างแน่นอน! คุณสามารถตั้งค่าคุณสมบัติเช่น`ImageSaveOptions.JpegQuality` เพื่อควบคุมคุณภาพของภาพที่ส่งออก

### ฉันจะจัดการเอกสารขนาดใหญ่อย่างมีประสิทธิภาพได้อย่างไร  
สำหรับเอกสารขนาดใหญ่ ให้พิจารณาการประมวลผลหน้าเป็นชุดเพื่อจัดการการใช้หน่วยความจำอย่างมีประสิทธิภาพ

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน  
 ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/words/net/) สำหรับคำแนะนำและตัวอย่างที่ครอบคลุม
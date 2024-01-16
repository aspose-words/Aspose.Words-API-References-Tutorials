---
title: หน้าบันทึกการโทรกลับ
linktitle: หน้าบันทึกการโทรกลับ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีปรับแต่งการบันทึกหน้าเอกสารให้เป็นรูปภาพด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-imagesaveoptions/page-saving-callback/
---

ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้ไว้สำหรับการใช้เพจบันทึกการโทรกลับด้วยตัวเลือกการบันทึกรูปภาพ Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถดำเนินการแบบกำหนดเองได้เมื่อบันทึกแต่ละหน้าของเอกสารเป็นรูปภาพ

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 ในขั้นตอนนี้ เราโหลดเอกสารโดยใช้`Document` วิธีการและส่งเส้นทางไปยังไฟล์ DOCX ที่จะโหลด

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการสำรองข้อมูลรูปภาพ

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 ในขั้นตอนนี้ เรากำหนดค่าตัวเลือกการบันทึกรูปภาพโดยสร้างตัวเลือกใหม่`ImageSaveOptions` วัตถุ. เราระบุรูปแบบการสำรองข้อมูลที่ต้องการ ที่นี่ "Png" สำหรับรูปแบบ PNG เราใช้`PageSet` เพื่อระบุช่วงของหน้าที่จะบันทึกตั้งแต่หน้าแรกจนถึงหน้าสุดท้ายของเอกสาร (`doc.PageCount - 1`). เรายังตั้ง`PageSavingCallback` ถึงตัวอย่างของ`HandlePageSavingCallback`ซึ่งเป็นคลาสที่กำหนดเองเพื่อจัดการการโทรกลับการบันทึกเพจ

## ขั้นตอนที่ 4: การใช้การโทรกลับหน้าบันทึก

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // ใช้การกระทำที่กำหนดเองของคุณที่นี่
         // คุณสามารถเข้าถึงข้อมูลเพจผ่านคุณสมบัติ "args.PageIndex"
         // คุณยังสามารถเปลี่ยนตัวเลือกการบันทึกสำหรับแต่ละหน้าแยกกันได้
     }
}
```

 ในขั้นตอนนี้ เราดำเนินการ`HandlePageSavingCallback` คลาสที่ใช้`IPageSavingCallback` อินเตอร์เฟซ. คุณสามารถปรับแต่งคลาสนี้ได้โดยเพิ่มการกระทำเฉพาะของคุณลงใน`PageSaving` วิธี. คุณสามารถเข้าถึงข้อมูลเพจได้ผ่านทาง`args.PageIndex` ทรัพย์สินของ`PageSavingArgs` วัตถุส่งผ่านเป็นอาร์กิวเมนต์

## ขั้นตอนที่ 5: บันทึกหน้าเป็นรูปภาพ

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกแต่ละหน้าของเอกสารเป็นรูปภาพโดยใช้`Save` วิธีการและส่งเส้นทางไปยังไฟล์เอาต์พุตด้วย`.png` ส่วนขยายพร้อมกับตัวเลือกการบันทึกที่ระบุ

ตอนนี้คุณสามารถเรียกใช้ซอร์สโค้ดเพื่อดำเนินการแบบกำหนดเองเมื่อบันทึกแต่ละหน้าของเอกสารเป็นรูปภาพ ไฟล์ผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithImageSaveOptions.PageSavingCallback.png"

### ตัวอย่างซอร์สโค้ดสำหรับ Page Saving Callback โดยใช้ Aspose.Words สำหรับ .NET


```csharp 
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟังก์ชันการโทรกลับบันทึกเพจด้วยตัวเลือกการบันทึกรูปภาพ Aspose.Words สำหรับ .NET เราเรียนรู้วิธีดำเนินการแบบกำหนดเองเมื่อบันทึกแต่ละหน้าของเอกสารเป็นรูปภาพ

คุณสมบัตินี้มีประโยชน์เมื่อคุณต้องการดำเนินการเฉพาะในแต่ละหน้าเมื่อแปลงเป็นรูปภาพ คุณสามารถเข้าถึงข้อมูลเพจและใช้เพื่อปรับแต่งตัวเลือกการสำรองข้อมูลหรือดำเนินการประมวลผลเฉพาะเพจอื่นๆ

Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติขั้นสูงที่หลากหลายสำหรับการจัดการและสร้างเอกสาร บันทึกหน้าเตือนความจำเป็นหนึ่งในเครื่องมือที่มีประสิทธิภาพมากมายที่ช่วยให้คุณสามารถปรับแต่งกระบวนการบันทึกหน้าลงในรูปภาพได้
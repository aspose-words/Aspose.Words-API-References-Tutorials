---
title: จัดการ SpacesOptions
linktitle: จัดการ SpacesOptions
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีจัดการช่องว่างในเอกสาร TXT ของคุณด้วย Aspose.Words for .NET ลบช่องว่างที่ไม่จำเป็นและปรับปรุงให้อ่านง่าย
type: docs
weight: 10
url: /th/net/programming-with-txtloadoptions/handle-spaces-options/
---

ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้ไว้สำหรับการทำงานของ "การจัดการพื้นที่ด้วยตัวเลือกการโหลด TXT" ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณระบุลักษณะการจัดการช่องว่างเมื่อโหลดเอกสาร TXT

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: การสร้างเอกสารข้อความ

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

ในขั้นตอนนี้ เราสร้างสตริงข้อความที่จำลองเอกสารข้อความที่มีบรรทัดที่มีช่องว่างนำหน้าและต่อท้าย

## ขั้นตอนที่ 3: การกำหนดค่าตัวเลือกการอัปโหลด

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

 ในขั้นตอนนี้ เราจะกำหนดค่าตัวเลือกสำหรับการโหลดเอกสาร TXT เราสร้างใหม่`TxtLoadOptions` วัตถุและตั้งค่า`LeadingSpacesOptions` และ`TrailingSpacesOptions` คุณสมบัติที่จะ`TxtLeadingSpacesOptions.Trim` และ`TxtTrailingSpacesOptions.Trim` ตามลำดับ ซึ่งจะเป็นการบอกให้ Aspose.Words ลบช่องว่างนำหน้าและต่อท้ายออกจากบรรทัดเมื่อโหลดเอกสาร

## ขั้นตอนที่ 4: การโหลดเอกสาร

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

 ในขั้นตอนนี้ เราโหลดเอกสารโดยใช้`Document` วิธีการและส่งกระแสข้อมูลหน่วยความจำที่มีสตริงข้อความที่ระบุและตัวเลือกการโหลด

## ขั้นตอนที่ 5: บันทึกเอกสาร

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกเอกสารผลลัพธ์ในรูปแบบ .docx โดยใช้`Save` วิธีการและส่งเส้นทางไปยังไฟล์ที่ส่งออก

ตอนนี้คุณสามารถรันซอร์สโค้ดเพื่อโหลดเอกสารข้อความโดยระบุตัวเลือกการจัดการช่องว่าง เอกสารผลลัพธ์จะถูกบันทึกในไดเร็กทอรีที่ระบุโดยใช้ชื่อ "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx"

### ตัวอย่างซอร์สโค้ดสำหรับคุณสมบัติการจัดการพื้นที่พร้อมตัวเลือกการโหลด TXT พร้อม Aspose.Words สำหรับ .NET*

```csharp

            
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟังก์ชันการทำงานของการจัดการพื้นที่ด้วยตัวเลือกการโหลด TXT ใน Aspose.Words สำหรับ .NET เราได้เรียนรู้วิธีระบุพฤติกรรมการจัดการช่องว่างเมื่อโหลดเอกสาร TXT

คุณลักษณะนี้มีประโยชน์มากในการจัดการกับช่องว่างด้านซ้ายและด้านขวาของบรรทัดในเอกสารโดยไม่จำเป็น ด้วยการกำหนดค่าตัวเลือกการโหลดที่เหมาะสม คุณสามารถลบช่องว่างที่ไม่ต้องการเหล่านี้ออกได้อย่างง่ายดาย ซึ่งช่วยทำให้เนื้อหาเอกสารสะอาดขึ้นและอ่านง่ายขึ้น

Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติขั้นสูงมากมายสำหรับการจัดการและสร้างเอกสาร การจัดการพื้นที่เมื่อโหลดเอกสาร TXT เป็นหนึ่งในเครื่องมืออันทรงพลังมากมายที่คุณมี

 สิ่งสำคัญคือต้องเลือกตัวเลือกการจัดการพื้นที่ที่เหมาะสมกับสถานการณ์เฉพาะของคุณมากที่สุด ในตัวอย่างนี้ เราใช้`Trim`ตัวเลือกในการลบช่องว่างที่ไม่จำเป็นออกจากจุดเริ่มต้นและจุดสิ้นสุดของบรรทัด อย่างไรก็ตาม Aspose.Words ยังมีตัวเลือกอื่น ๆ เพื่อรักษาช่องว่าง ลบออกทั้งหมด หรือคงไว้เหมือนเดิม

อย่าลืมปรับเปลี่ยนตัวเลือกเหล่านี้ตามความต้องการเฉพาะของคุณและโครงสร้างของเอกสาร TXT

ด้วย Aspose.Words สำหรับ .NET คุณสามารถจัดการช่องว่างในเอกสารของคุณได้อย่างง่ายดาย ปรับปรุงคุณภาพเค้าโครงและความสามารถในการอ่านเนื้อหา

ดังนั้น อย่าลังเลที่จะผสานรวมการจัดการช่องว่างเข้ากับตัวเลือกการโหลด TXT ในโปรเจ็กต์ Aspose.Words สำหรับ .NET ของคุณ และใช้ประโยชน์จากข้อดีของมันเพื่อสร้างเอกสารที่มีรูปแบบที่ดีและอ่านง่าย
---
title: ตั้งค่าโฟลเดอร์รูปภาพ
linktitle: ตั้งค่าโฟลเดอร์รูปภาพ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีการตั้งค่าโฟลเดอร์รูปภาพเมื่อส่งออกไปยัง Markdown ด้วย Aspose.Words สำหรับ .NET ปรับแต่งการวางตำแหน่งรูปภาพเพื่อการจัดระเบียบและการบูรณาการที่ดียิ่งขึ้น
type: docs
weight: 10
url: /th/net/programming-with-markdownsaveoptions/set-images-folder/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ต่อไปนี้ซึ่งช่วยในการตั้งค่าโฟลเดอร์รูปภาพสำหรับตัวเลือกการส่งออก Markdown โดยใช้ไลบรารี Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words ไว้ในโปรเจ็กต์ของคุณก่อนที่จะใช้โค้ดนี้

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

อย่าลืมระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีเอกสารที่มีรูปภาพอยู่

## ขั้นตอนที่ 2: โหลดเอกสารที่มีรูปภาพ

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

เราโหลดเอกสารที่ระบุซึ่งมีรูปภาพที่เราต้องการส่งออกด้วยตัวเลือก Markdown

## ขั้นตอนที่ 3: ตั้งค่าโฟลเดอร์รูปภาพสำหรับตัวเลือกการส่งออก Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 เราสร้างอินสแตนซ์ของ`MarkdownSaveOptions` และกำหนดเส้นทางไปยังโฟลเดอร์รูปภาพโดยใช้ไฟล์`ImagesFolder` คุณสมบัติ. ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังโฟลเดอร์ที่คุณต้องการบันทึกภาพที่ส่งออก

## ขั้นตอนที่ 4: บันทึกเอกสารด้วยตัวเลือกการส่งออก Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

เราบันทึกเอกสารลงในสตรีมหน่วยความจำโดยใช้ตัวเลือกการส่งออก Markdown ที่ระบุ จากนั้นคุณสามารถใช้โฟลว์เพื่อดำเนินการอื่นๆ ได้ เช่น บันทึกเนื้อหา Markdown ลงในไฟล์

### ตัวอย่างซอร์สโค้ดเพื่อตั้งค่าโฟลเดอร์รูปภาพสำหรับ MarkdownSaveOptions ด้วย Aspose.Words สำหรับ .NET

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

ซอร์สโค้ดนี้สาธิตวิธีการโหลดเอกสารที่มีรูปภาพ จากนั้นตั้งค่าโฟลเดอร์รูปภาพสำหรับตัวเลือกการส่งออก Markdown โดยใช้ตัวเลือกที่ระบุ เอกสารจะถูกบันทึกลงในสตรีมหน่วยความจำ ซึ่งช่วยให้คุณปรับแต่งตำแหน่งของโฟลเดอร์รูปภาพเมื่อส่งออกเนื้อหา Markdown
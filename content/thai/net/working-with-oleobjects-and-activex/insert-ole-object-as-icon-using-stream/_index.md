---
title: แทรกวัตถุ Ole เป็นไอคอนโดยใช้สตรีม
linktitle: แทรกวัตถุ Ole เป็นไอคอนโดยใช้สตรีม
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกวัตถุ OLE เป็นไอคอนโดยใช้สตรีมด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่างซึ่งแสดงวิธีการแทรกวัตถุ OLE เป็นไอคอนโดยใช้สตรีมด้วย Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: นำเข้าข้อมูลอ้างอิงที่จำเป็น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าข้อมูลอ้างอิงที่จำเป็นเพื่อใช้ Aspose.Words สำหรับ .NET ในโครงการของคุณ ซึ่งรวมถึงการนำเข้าไลบรารี Aspose.Words และการเพิ่มเนมสเปซที่จำเป็นลงในไฟล์ต้นฉบับของคุณ

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## ขั้นตอนที่ 2: สร้างเอกสารและเครื่องมือสร้างเอกสารใหม่
 ในขั้นตอนนี้ เราจะสร้างเอกสารใหม่โดยใช้`Document` คลาสและตัวสร้างเอกสารโดยใช้`DocumentBuilder` ระดับ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกวัตถุ OLE เป็นไอคอนจากสตรีม
 ใช้ตัวสร้างเอกสาร`InsertOleObjectAsIcon` วิธีการแทรกวัตถุ OLE เป็นไอคอนจากสตรีมลงในเอกสาร ระบุสตรีมข้อมูล ประเภทออบเจ็กต์ เส้นทางไอคอน และชื่อออบเจ็กต์ที่ฝัง

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 ใช้เอกสาร`Save` วิธีการบันทึกเอกสารเป็นไฟล์

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกวัตถุ OLE เป็นไอคอนโดยใช้สตรีมด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

นี่คือตัวอย่างโค้ดที่สมบูรณ์สำหรับการแทรกวัตถุ OLE เป็นไอคอนโดยใช้สตรีมที่มี Aspose.Words สำหรับ .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้ก่อนหน้านี้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ

## บทสรุป

คำแนะนำทีละขั้นตอนข้างต้นอธิบายวิธีการแทรกวัตถุ OLE เป็นไอคอนในเอกสาร Word โดยใช้โฟลว์กับ Aspose.Words สำหรับ .NET เมื่อทำตามขั้นตอนที่อธิบายไว้ คุณจะสามารถรวมฟังก์ชันการทำงานนี้เข้ากับโปรเจ็กต์ของคุณได้ อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็น สร้างเอกสารและตัวสร้างเอกสารใหม่ แทรกวัตถุ OLE เป็นไอคอนจากสตรีม จากนั้นบันทึกเอกสาร ใช้โค้ดตัวอย่างที่ให้ไว้เป็นจุดเริ่มต้นและปรับแต่งตามความต้องการของคุณ

### คำถามที่พบบ่อย

#### ถาม: จะนำเข้าข้อมูลอ้างอิงที่จำเป็นเพื่อใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

A. หากต้องการนำเข้าข้อมูลอ้างอิงที่จำเป็น คุณต้องทำตามขั้นตอนเหล่านี้:

 เพิ่มสิ่งต่อไปนี้`using` คำสั่งที่ด้านบนของไฟล์ต้นฉบับของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Words ในโครงการของคุณแล้ว

#### ถาม: จะสร้างเอกสารและตัวสร้างเอกสารใหม่โดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

A. หากต้องการสร้างเอกสารและตัวสร้างเอกสารใหม่ คุณสามารถทำตามขั้นตอนเหล่านี้:

 ใช้`Document` คลาสเพื่อสร้างเอกสารใหม่:

```csharp
Document doc = new Document();
```
 ใช้`DocumentBuilder`คลาสเพื่อสร้างตัวสร้างเอกสารที่เกี่ยวข้องกับเอกสารที่สร้างไว้ก่อนหน้านี้:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### ถามจะแทรกวัตถุ OLE เป็นไอคอนจากสตรีมโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

A. เมื่อต้องการแทรกวัตถุ OLE เป็นไอคอนจากกระแสข้อมูล คุณสามารถทำตามขั้นตอนเหล่านี้:

 ใช้`InsertOleObjectAsIcon` วิธีการสร้างเอกสารเพื่อแทรกวัตถุ OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### ถาม จะบันทึกเอกสารเป็นไฟล์ได้อย่างไร?

A.  หากต้องการบันทึกเอกสารเป็นไฟล์ คุณสามารถใช้ไฟล์`Save` วิธีการของเอกสารระบุเส้นทางปลายทาง:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### ถาม ฉันจะฝังโค้ดเพื่อแทรกวัตถุ OLE เป็นไอคอนจากสตรีมลงในโปรเจ็กต์ของฉันได้อย่างไร

A. เมื่อต้องการฝังโค้ดสำหรับการแทรกวัตถุ OLE เป็นไอคอนจากกระแสข้อมูลลงในโครงการของคุณ ให้ทำตามขั้นตอนเหล่านี้:
-  นำเข้าข้อมูลอ้างอิงที่จำเป็นโดยเพิ่มข้อมูลอ้างอิงที่เหมาะสม`using` งบ
-  สร้างเอกสารใหม่และตัวสร้างเอกสารโดยใช้`Document` และ`DocumentBuilder` ชั้นเรียน
- ใช้รหัสสำหรับการแทรกวัตถุ OLE เป็นไอคอนจากสตรีม
-  บันทึกเอกสารโดยใช้`Save` วิธีการที่มีเส้นทางปลายทางที่เหมาะสม

โดยทำตามขั้นตอนเหล่านี้ คุณจะสามารถแทรกวัตถุ OLE เป็นไอคอนจากสตรีมโดยใช้ Aspose.Words สำหรับ .NET ได้สำเร็จ อย่าลืมปฏิบัติตามคำแนะนำและนำเข้าข้อมูลอ้างอิงที่จำเป็นเพื่อให้ได้ผลลัพธ์ที่ต้องการ
---
title: แทรกวัตถุ Ole ในเอกสาร Word เป็นไอคอน
linktitle: แทรกวัตถุ Ole ในเอกสาร Word เป็นไอคอน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกวัตถุ OLE ในเอกสาร word เป็นไอคอนด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่างซึ่งแสดงวิธีการแทรกวัตถุ OLE ในเอกสาร word เป็นไอคอนโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: นำเข้าข้อมูลอ้างอิงที่จำเป็น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าข้อมูลอ้างอิงที่จำเป็นเพื่อใช้ Aspose.Words สำหรับ .NET ในโครงการของคุณ ซึ่งรวมถึงการนำเข้าไลบรารี Aspose.Words และการเพิ่มเนมสเปซที่จำเป็นลงในไฟล์ต้นฉบับของคุณ

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## ขั้นตอนที่ 2: สร้างเอกสารและเครื่องมือสร้างเอกสารใหม่
 ในขั้นตอนนี้ เราจะสร้างเอกสารใหม่โดยใช้`Document` คลาสและตัวสร้างเอกสารโดยใช้`DocumentBuilder` ระดับ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 3: แทรกวัตถุ OLE เป็นไอคอน
 ใช้ตัวสร้างเอกสาร`InsertOleObjectAsIcon`วิธีการแทรกวัตถุ OLE เป็นไอคอนลงในเอกสาร ระบุเส้นทางไฟล์ OLE ค่าสถานะที่แสดง เส้นทางไอคอน และชื่อวัตถุที่ฝังตัว

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 ใช้เอกสาร`Save` วิธีการบันทึกเอกสารเป็นไฟล์

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกวัตถุ OLE เป็นไอคอนด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

นี่คือตัวอย่างโค้ดที่สมบูรณ์สำหรับการแทรกวัตถุ OLE เป็นไอคอนด้วย Aspose.Words สำหรับ .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้ก่อนหน้านี้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ

## บทสรุป

โดยสรุป เราได้สำรวจคำแนะนำทีละขั้นตอนในการแทรกวัตถุ OLE เป็นไอคอนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถแทรกวัตถุ OLE เป็นไอคอนในเอกสาร Word ของคุณได้สำเร็จโดยใช้ Aspose.Words for .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและปฏิบัติตามคำแนะนำอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

### คำถามที่พบบ่อยสำหรับการแทรกวัตถุ ole ในเอกสาร word เป็นไอคอน

#### ถาม จำเป็นต้องมีการอ้างอิงอะไรบ้างในการแทรกวัตถุ OLE เป็นไอคอนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET

ตอบ: คุณต้องนำเข้าข้อมูลอ้างอิงต่อไปนี้ลงในโปรเจ็กต์ของคุณเพื่อใช้ Aspose.Words สำหรับ .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### ถาม จะสร้างเอกสารและตัวสร้างเอกสารใหม่ใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: คุณสามารถสร้างเอกสารใหม่โดยใช้ไฟล์`Document` คลาสและตัวสร้างเอกสารโดยใช้`DocumentBuilder` ระดับ. นี่คือตัวอย่าง:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### ถามจะแทรกวัตถุ OLE เป็นไอคอนในเอกสารได้อย่างไร

 ตอบ: ใช้ตัวสร้างเอกสาร`InsertOleObjectAsIcon` วิธีการแทรกวัตถุ OLE เป็นไอคอน ระบุเส้นทางไฟล์ OLE ค่าสถานะที่แสดง เส้นทางไอคอน และชื่อวัตถุที่ฝังตัว นี่คือตัวอย่าง:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### ถามจะบันทึกเอกสารโดยแทรกวัตถุ OLE เป็นไอคอนได้อย่างไร

 ตอบ: ใช้เอกสาร`Save` วิธีการบันทึกเอกสารเป็นไฟล์ นี่คือตัวอย่าง:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```
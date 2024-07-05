---
title: แทรกวัตถุ Ole ใน Word ด้วยแพ็คเกจ Ole
linktitle: แทรกวัตถุ Ole ใน Word ด้วยแพ็คเกจ Ole
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกวัตถุ OLE ด้วยแพ็คเกจ OLE ลงในเอกสารโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่างซึ่งแสดงวิธีการแทรกวัตถุ OLE ในคำด้วยแพ็คเกจ OLE โดยใช้ Aspose.Words สำหรับ .NET

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

## ขั้นตอนที่ 3: แทรกวัตถุ OLE ด้วยแพ็คเกจ OLE
 ใช้ตัวสร้างเอกสาร`InsertOleObject` วิธีการแทรกวัตถุ OLE ด้วยแพ็คเกจ OLE ลงในเอกสาร ระบุสตรีมข้อมูล ประเภทออบเจ็กต์ ตัวเลือกการแสดงผล และการตั้งค่าที่จำเป็นอื่นๆ

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 ใช้เอกสาร`Save` วิธีการบันทึกเอกสารเป็นไฟล์

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### ซอร์สโค้ดตัวอย่างสำหรับการแทรกวัตถุ OLE ด้วยแพ็คเกจ OLE ด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

นี่คือตัวอย่างโค้ดที่สมบูรณ์สำหรับการแทรกวัตถุ OLE ด้วยแพ็คเกจ OLE ด้วย Aspose.Words สำหรับ .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้ก่อนหน้านี้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ

## บทสรุป

โดยสรุป เราได้อ่านคำแนะนำทีละขั้นตอนในการแทรกวัตถุ OLE ลงในเอกสาร Word ด้วยแพ็คเกจ OLE โดยใช้ Aspose.Words สำหรับ .NET

เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถแทรกวัตถุ OLE ที่มีแพ็คเกจ OLE ลงในเอกสาร Word ของคุณได้สำเร็จโดยใช้ Aspose.Words for .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและปฏิบัติตามคำแนะนำอย่างระมัดระวังเพื่อให้ได้ผลลัพธ์ที่ต้องการ

### คำถามที่พบบ่อยสำหรับการแทรก ole object ใน word ด้วย ole package

#### ถาม: ฉันจำเป็นต้องนำเข้าข้อมูลรับรองอะไรบ้างเพื่อใช้ Aspose.Words สำหรับ .NET

ตอบ: หากต้องการใช้ Aspose.Words สำหรับ .NET คุณต้องนำเข้าข้อมูลอ้างอิงต่อไปนี้:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### ถาม: จะสร้างเอกสารใหม่และตัวสร้างเอกสารได้อย่างไร

 ตอบ: คุณสามารถสร้างเอกสารใหม่โดยใช้ไฟล์`Document` คลาสและตัวสร้างเอกสารโดยใช้`DocumentBuilder` คลาส ดังที่แสดงด้านล่าง:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### ถาม: จะแทรกวัตถุ OLE พร้อมแพ็คเกจ OLE ลงในเอกสารได้อย่างไร

 ตอบ: ใช้`InsertOleObject`วิธีการสร้างเอกสาร (`DocumentBuilder`) เพื่อแทรกวัตถุ OLE ที่มีแพ็คเกจ OLE ลงในเอกสาร ระบุสตรีมข้อมูล ประเภทออบเจ็กต์ ตัวเลือกการแสดงผล และการตั้งค่าที่จำเป็นอื่นๆ นี่คือตัวอย่าง:

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### ถาม: จะบันทึกเอกสารได้อย่างไร?

 ตอบ: ใช้เอกสาร`Save` วิธีการบันทึกเอกสารเป็นไฟล์ นี่คือตัวอย่าง:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### ถาม: คุณสามารถแสดงตัวอย่างที่สมบูรณ์ของการแทรกวัตถุ OLE ด้วยแพ็คเกจ OLE ด้วย Aspose.Words สำหรับ .NET ได้หรือไม่

ตอบ: นี่คือโค้ดตัวอย่างที่สมบูรณ์ในการแทรกวัตถุ OLE ด้วยแพ็คเกจ OLE โดยใช้ Aspose.Words สำหรับ .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้ก่อนหน้านี้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

นี่เป็นการสรุปบทช่วยสอนของเราเกี่ยวกับการแทรกวัตถุ OLE ด้วยแพ็คเกจ OLE ลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET คุณสามารถนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ หากคุณมีคำถามเพิ่มเติม โปรดอย่าลังเลที่จะติดต่อเรา
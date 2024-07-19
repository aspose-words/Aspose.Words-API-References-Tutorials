---
title: แทรกวัตถุ Ole ในเอกสาร Word
linktitle: แทรกวัตถุ Ole ในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกวัตถุ OLE ในเอกสาร word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-oleobjects-and-activex/insert-ole-object/
---

ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ด้านล่างซึ่งแสดงวิธีการแทรกวัตถุ OLE ในเอกสาร word โดยใช้ Aspose.Words สำหรับ .NET

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

## ขั้นตอนที่ 3: แทรกวัตถุ OLE
 ใช้ตัวสร้างเอกสาร`InsertOleObject`วิธีการแทรกวัตถุ OLE ลงในเอกสาร ระบุ URL ของออบเจ็กต์ OLE ประเภทออบเจ็กต์ ตัวเลือกการแสดงผล และการตั้งค่าที่จำเป็นอื่นๆ

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", จริง, จริง, null);
```

## ขั้นตอนที่ 4: บันทึกเอกสาร
 ใช้เอกสาร`Save` วิธีการบันทึกเอกสารเป็นไฟล์

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกวัตถุ OLE ด้วย Aspose.Words สำหรับ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", จริง, จริง, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

นี่คือตัวอย่างโค้ดที่สมบูรณ์สำหรับการแทรกวัตถุ OLE ด้วย Aspose.Words สำหรับ .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้ก่อนหน้านี้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ

## บทสรุป

โดยสรุป การแทรกวัตถุ OLE ลงในเอกสาร Word เป็นคุณสมบัติอันทรงพลังที่นำเสนอโดย Aspose.Words สำหรับ .NET เมื่อใช้ไลบรารีนี้ คุณสามารถฝังวัตถุ OLE เช่น ไฟล์ HTML, สเปรดชีต Excel, งานนำเสนอ PowerPoint ฯลฯ ลงในเอกสาร Word ของคุณได้อย่างง่ายดาย

ในบทความนี้ เราได้อ่านคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ดใน C# ซึ่งแสดงวิธีการแทรกวัตถุ OLE ลงในเอกสาร Word เราได้กล่าวถึงการอ้างอิงที่จำเป็น การสร้างเอกสารใหม่และตัวสร้างเอกสาร และขั้นตอนในการแทรกออบเจ็กต์ OLE และบันทึกเอกสาร

### คำถามที่พบบ่อยสำหรับการแทรกวัตถุ OLE ลงในเอกสาร Word

#### ถาม: ฉันจำเป็นต้องนำเข้าข้อมูลรับรองอะไรบ้างเพื่อใช้ Aspose.Words สำหรับ .NET

ตอบ: หากต้องการใช้ Aspose.Words สำหรับ .NET คุณต้องนำเข้าข้อมูลอ้างอิงต่อไปนี้:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### ถาม: จะสร้างเอกสารใหม่และตัวสร้างเอกสารได้อย่างไร

 ตอบ: คุณสามารถสร้างเอกสารใหม่โดยใช้ไฟล์`Document` คลาสและตัวสร้างเอกสารโดยใช้`DocumentBuilder` คลาส ดังที่แสดงด้านล่าง:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### ถาม: จะแทรกวัตถุ OLE ในเอกสารได้อย่างไร

 ตอบ: ใช้`InsertOleObject` วิธีการสร้างเอกสาร (`DocumentBuilder`) เพื่อแทรกวัตถุ OLE ลงในเอกสาร ระบุ URL ของออบเจ็กต์ OLE ประเภทออบเจ็กต์ ตัวเลือกการแสดงผล และการตั้งค่าที่จำเป็นอื่นๆ นี่คือตัวอย่าง:

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", จริง, จริง, null);
```

#### ถาม: จะบันทึกเอกสารได้อย่างไร?

 ตอบ: ใช้เอกสาร`Save`วิธีการบันทึกเอกสารเป็นไฟล์ นี่คือตัวอย่าง:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### ถาม: คุณสามารถแสดงตัวอย่างที่สมบูรณ์ของการแทรกวัตถุ OLE ด้วย Aspose.Words สำหรับ .NET ได้หรือไม่

ตอบ: นี่คือโค้ดตัวอย่างที่สมบูรณ์ในการแทรกวัตถุ OLE ด้วย Aspose.Words สำหรับ .NET อย่าลืมนำเข้าข้อมูลอ้างอิงที่จำเป็นและทำตามขั้นตอนที่อธิบายไว้ก่อนหน้านี้เพื่อรวมโค้ดนี้เข้ากับโปรเจ็กต์ของคุณ:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", จริง, จริง, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

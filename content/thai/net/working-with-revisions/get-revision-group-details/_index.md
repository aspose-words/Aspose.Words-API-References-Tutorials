---
title: รับรายละเอียดกลุ่มการแก้ไข
linktitle: รับรายละเอียดกลุ่มการแก้ไข
second_title: Aspose.Words API การประมวลผลเอกสาร
description: รับรายละเอียดกลุ่มการแก้ไขในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-revisions/get-revision-group-details/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีรับรายละเอียดกลุ่มการแก้ไขในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ขั้นตอนแรกคือการอัปโหลดเอกสารที่มีการแก้ไข

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## ขั้นตอนที่ 2: เรียกดูการแก้ไข

ต่อไป เราจะวนดูการแก้ไขที่มีอยู่ในเอกสารและแสดงรายละเอียด เช่น ประเภท ผู้แต่ง วันที่ และข้อความที่แก้ไข

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### ตัวอย่างซอร์สโค้ดสำหรับรับรายละเอียดกลุ่มการแก้ไขโดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์เพื่อรับรายละเอียดกลุ่มการแก้ไขในเอกสารโดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีรับรายละเอียดกลุ่มการแก้ไขในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการใช้ลูปและคุณสมบัติที่เหมาะสม เราสามารถแสดงรายละเอียด เช่น ประเภทการแก้ไข ผู้แต่ง วันที่ และข้อความที่แก้ไข Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติที่มีประสิทธิภาพมากมายสำหรับการจัดการเอกสาร Word รวมถึงการจัดการการแก้ไข ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อรับรายละเอียดกลุ่มการแก้ไขลงในเอกสาร Word ของคุณเองโดยใช้ Aspose.Words สำหรับ .NET

### คำถามที่พบบ่อย

#### ถาม: ฉันจะโหลดเอกสารที่มีการแก้ไขลงใน Aspose.Words สำหรับ .NET ได้อย่างไร

 ตอบ: ใช้`Document` คลาสของ Aspose.Words สำหรับ .NET เพื่อโหลดเอกสารจากไฟล์ที่มีการแก้ไข คุณสามารถระบุเส้นทางเอกสารแบบเต็มได้

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### ถาม: ฉันจะรับรายละเอียดของกลุ่มการแก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: ดำเนินการแก้ไขเอกสารโดยใช้การวนซ้ำและเข้าถึงคุณสมบัติของการแก้ไขแต่ละครั้งเพื่อดูรายละเอียดที่คุณต้องการ คุณสามารถใช้`RevisionType`, `Author`, `DateTime` และ`ParentNode` คุณสมบัติเพื่อรับประเภทการแก้ไข ผู้แต่ง วันที่ และข้อความที่แก้ไขตามลำดับ

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### ถาม: จะตรวจสอบได้อย่างไรว่าการแก้ไขอยู่ในกลุ่มใน Aspose.Words for .NET หรือไม่

 ตอบ: ใช้`Group` ทรัพย์สินของ`Revision` วัตถุเพื่อตรวจสอบว่าการแก้ไขเป็นของกลุ่มหรือไม่ ถ้า`Group` ทรัพย์สินคือ`null`หมายความว่าการแก้ไขนั้นไม่ได้อยู่ในกลุ่มใดๆ

```csharp
if (revision.Group != null)
{
      // การแก้ไขเป็นของกลุ่ม
}
else
{
      // การแก้ไขไม่ได้เป็นของกลุ่มใด ๆ
}
```
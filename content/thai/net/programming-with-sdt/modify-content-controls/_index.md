---
title: แก้ไขการควบคุมเนื้อหา
linktitle: แก้ไขการควบคุมเนื้อหา
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแก้ไขแท็กเอกสารที่มีโครงสร้างใน Word โดยใช้ Aspose.Words สำหรับ .NET อัปเดตข้อความ เมนูแบบเลื่อนลง และรูปภาพทีละขั้นตอน
type: docs
weight: 10
url: /th/net/programming-with-sdt/modify-content-controls/
---
## การแนะนำ

หากคุณเคยทำงานกับเอกสาร Word และจำเป็นต้องปรับเปลี่ยนการควบคุมเนื้อหาที่มีโครงสร้าง เช่น ข้อความธรรมดา รายการดรอปดาวน์ หรือรูปภาพ โดยใช้ Aspose.Words สำหรับ .NET คุณมาถูกที่แล้ว! แท็กเอกสารที่มีโครงสร้าง (SDT) เป็นเครื่องมืออันทรงพลังที่ทำให้ระบบอัตโนมัติของเอกสารง่ายขึ้นและยืดหยุ่นมากขึ้น ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีที่คุณสามารถแก้ไข SDT เหล่านี้ให้เหมาะกับความต้องการของคุณ ไม่ว่าคุณกำลังอัปเดตข้อความ เปลี่ยนตัวเลือกแบบเลื่อนลง หรือสลับรูปภาพ คู่มือนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะพูดถึงสาระสำคัญในการปรับเปลี่ยนการควบคุมเนื้อหา ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1.  ติดตั้ง Aspose.Words สำหรับ .NET แล้ว: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Words แล้ว ถ้าไม่คุณสามารถ[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/words/net/).

2. ความรู้พื้นฐานของ C#: บทช่วยสอนนี้ถือว่าคุณคุ้นเคยกับแนวคิดการเขียนโปรแกรม C# ขั้นพื้นฐาน

3. สภาพแวดล้อมการพัฒนา. NET: คุณควรมี IDE เช่น Visual Studio ที่ตั้งค่าไว้สำหรับการเรียกใช้แอปพลิเคชัน .NET

4. เอกสารตัวอย่าง: เราจะใช้เอกสาร Word ตัวอย่างกับ SDT ประเภทต่างๆ คุณสามารถใช้อันจากตัวอย่างหรือสร้างของคุณเอง

5.  การเข้าถึงเอกสารประกอบ Aspose: สำหรับข้อมูลโดยละเอียดเพิ่มเติม โปรดดูที่[เอกสาร Aspose.Words](https://reference.aspose.com/words/net/).

## นำเข้าเนมสเปซ

หากต้องการเริ่มทำงานกับ Aspose.Words คุณจะต้องนำเข้าเนมสเปซที่เกี่ยวข้องลงในโปรเจ็กต์ C# ของคุณ นี่คือวิธีการ:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

เนมสเปซเหล่านี้จะให้คุณเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการจัดการแท็กเอกสารที่มีโครงสร้างในเอกสาร Word ของคุณ

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางเอกสารของคุณ

 ก่อนทำการเปลี่ยนแปลงใดๆ คุณต้องระบุเส้นทางไปยังเอกสารของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงที่จัดเก็บเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## ขั้นตอนที่ 2: วนซ้ำแท็กเอกสารที่มีโครงสร้าง

 หากต้องการแก้ไข SDT คุณต้องวนซ้ำ SDT ทั้งหมดในเอกสารก่อน นี้จะกระทำโดยใช้`GetChildNodes` วิธีการรับโหนดทุกประเภท`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // แก้ไข SDT ตามประเภท
}
```

## ขั้นตอนที่ 3: แก้ไข SDT ข้อความธรรมดา

หาก SDT เป็นประเภทข้อความธรรมดา คุณสามารถแทนที่เนื้อหาได้ ขั้นแรก ล้างเนื้อหาที่มีอยู่ จากนั้นจึงเพิ่มข้อความใหม่

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 คำอธิบาย: ที่นี่,`RemoveAllChildren()`ล้างเนื้อหาที่มีอยู่ของ SDT จากนั้นเราก็สร้างใหม่`Paragraph`และ`Run` วัตถุเพื่อแทรกข้อความใหม่

## ขั้นตอนที่ 4: แก้ไข SDT รายการแบบเลื่อนลง

 สำหรับรายการแบบเลื่อนลง SDT คุณสามารถเปลี่ยนรายการที่เลือกได้โดยเข้าไปที่`ListItems` ของสะสม. ที่นี่เราเลือกรายการที่สามในรายการ

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

คำอธิบาย: ข้อมูลโค้ดนี้เลือกรายการที่ดัชนี 2 (รายการที่สาม) จากรายการแบบเลื่อนลง ปรับดัชนีตามความต้องการของคุณ

## ขั้นตอนที่ 5: แก้ไขรูปภาพ SDT

หากต้องการอัปเดตรูปภาพภายในรูปภาพ SDT คุณสามารถแทนที่รูปภาพที่มีอยู่ด้วยรูปภาพใหม่ได้

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 คำอธิบาย: รหัสนี้จะตรวจสอบว่ารูปร่างมีรูปภาพหรือไม่ จากนั้นแทนที่ด้วยรูปภาพใหม่ที่ตั้งอยู่ที่`ImagesDir`.

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไขของคุณ

หลังจากทำการเปลี่ยนแปลงที่จำเป็นทั้งหมดแล้ว ให้บันทึกเอกสารที่แก้ไขด้วยชื่อใหม่ เพื่อให้เอกสารต้นฉบับของคุณไม่เสียหาย

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

คำอธิบาย: วิธีนี้จะบันทึกเอกสารด้วยชื่อไฟล์ใหม่ เพื่อให้คุณสามารถแยกความแตกต่างจากต้นฉบับได้อย่างง่ายดาย

## บทสรุป

การปรับเปลี่ยนการควบคุมเนื้อหาในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET นั้นตรงไปตรงมาเมื่อคุณเข้าใจขั้นตอนที่เกี่ยวข้องแล้ว ไม่ว่าคุณกำลังอัปเดตข้อความ เปลี่ยนตัวเลือกแบบเลื่อนลง หรือสลับรูปภาพ Aspose.Words ก็มี API ที่มีประสิทธิภาพสำหรับงานเหล่านี้ เมื่อทำตามบทช่วยสอนนี้ คุณจะจัดการและปรับแต่งการควบคุมเนื้อหาที่มีโครงสร้างของเอกสารได้อย่างมีประสิทธิภาพ ทำให้เอกสารของคุณมีความไดนามิกมากขึ้นและปรับให้เหมาะกับความต้องการของคุณ

## คำถามที่พบบ่อย

1. แท็กเอกสารที่มีโครงสร้าง (SDT) คืออะไร

SDT คือองค์ประกอบในเอกสาร Word ที่ช่วยจัดการและจัดรูปแบบเนื้อหาเอกสาร เช่น กล่องข้อความ รายการดรอปดาวน์ หรือรูปภาพ

2. ฉันจะเพิ่มรายการดรอปดาวน์ใหม่ลงใน SDT ได้อย่างไร

 หากต้องการเพิ่มรายการใหม่ ให้ใช้`ListItems` คุณสมบัติและผนวกใหม่`SdtListItem` เพื่อคอลเลกชัน

3. ฉันสามารถใช้ Aspose.Words เพื่อลบ SDT ออกจากเอกสารได้หรือไม่

ได้ คุณสามารถลบ SDT ได้โดยการเข้าถึงโหนดของเอกสารและลบ SDT ที่ต้องการ

4. ฉันจะจัดการ SDT ที่ซ้อนกันภายในองค์ประกอบอื่นได้อย่างไร

 ใช้`GetChildNodes` วิธีการที่มีพารามิเตอร์ที่เหมาะสมในการเข้าถึง SDT ที่ซ้อนกัน

5. ฉันควรทำอย่างไรหาก SDT ที่ต้องแก้ไขไม่ปรากฏในเอกสาร

ตรวจสอบให้แน่ใจว่า SDT ไม่ได้ถูกซ่อนหรือป้องกัน ตรวจสอบการตั้งค่าเอกสารและตรวจสอบว่าโค้ดของคุณกำหนดเป้าหมายประเภท SDT อย่างถูกต้อง


### ตัวอย่างซอร์สโค้ดสำหรับแก้ไขการควบคุมเนื้อหาโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
	switch (sdt.SdtType)
	{
		case SdtType.PlainText:
		{
			sdt.RemoveAllChildren();
			Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
			Run run = new Run(doc, "new text goes here");
			para.AppendChild(run);
			break;
		}
		case SdtType.DropDownList:
		{
			SdtListItem secondItem = sdt.ListItems[2];
			sdt.ListItems.SelectedValue = secondItem;
			break;
		}
		case SdtType.Picture:
		{
			Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
			if (shape.HasImage)
			{
				shape.ImageData.SetImage(ImagesDir + "Watermark.png");
			}
			break;
		}
	}
}
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

แค่นั้นแหละ! คุณได้แก้ไขการควบคุมเนื้อหาประเภทต่างๆ ในเอกสาร Word ของคุณสำเร็จแล้วโดยใช้ Aspose.Words สำหรับ .NET
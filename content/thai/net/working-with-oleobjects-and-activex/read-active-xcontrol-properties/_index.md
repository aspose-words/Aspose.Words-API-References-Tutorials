---
title: อ่านคุณสมบัติ XControl ที่ใช้งานอยู่จากไฟล์ Word
linktitle: อ่านคุณสมบัติ XControl ที่ใช้งานอยู่จากไฟล์ Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: อ่านคุณสมบัติของตัวควบคุม ActiveX ในไฟล์ Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

ในคำแนะนำทีละขั้นตอนนี้ เราจะแสดงวิธีอ่านคุณสมบัติของตัวควบคุม ActiveX ในไฟล์ Word โดยใช้ Aspose.Words สำหรับ .NET เราจะจัดเตรียมซอร์สโค้ดที่สมบูรณ์ให้กับคุณ และแสดงวิธีจัดรูปแบบเอาต์พุตมาร์กดาวน์

## ขั้นตอนที่ 1: การเริ่มต้นเอกสาร

 ขั้นตอนแรกคือการเริ่มต้น`Document` วัตถุโดยการโหลดเอกสาร Word ที่มีตัวควบคุม ActiveX อย่าลืมเปลี่ยน`MyDir` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่มีเอกสาร

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## ขั้นตอนที่ 2: กู้คืนตัวควบคุม ActiveX

 ในขั้นตอนนี้ เราจะทำซ้ำทีละขั้นตอน`Shape` ของเอกสารเพื่อดึงข้อมูลตัวควบคุม ActiveX และอ่านคุณสมบัติ

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### ตัวอย่างซอร์สโค้ดสำหรับอ่านคุณสมบัติ XControl ที่ใช้งานอยู่โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการอ่านคุณสมบัติของตัวควบคุม ActiveX โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## บทสรุป

คู่มือนี้จะแสดงวิธีอ่านคุณสมบัติของตัวควบคุม ActiveX ในไฟล์ Word โดยใช้ Aspose.Words สำหรับ .NET โดยทำตามขั้นตอนที่อธิบายไว้ คุณสามารถเตรียมใช้งานเอกสาร ดึงข้อมูลตัวควบคุม ActiveX และอ่านคุณสมบัติได้ ใช้โค้ดตัวอย่างที่ให้ไว้เป็นจุดเริ่มต้นและปรับแต่งตามความต้องการเฉพาะของคุณ

การอ่านคุณสมบัติของตัวควบคุม ActiveX ช่วยให้คุณสามารถดึงข้อมูลสำคัญจากไฟล์ Word ของคุณที่มีตัวควบคุมเหล่านี้ได้ Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติอันทรงพลังสำหรับการประมวลผลคำด้วยตัวควบคุม ActiveX และทำให้การประมวลผลเอกสารของคุณเป็นแบบอัตโนมัติ

### คำถามที่พบบ่อย

#### ถาม: ขั้นตอนแรกในการอ่านคุณสมบัติของตัวควบคุม ActiveX ในไฟล์ Word คืออะไร

 ตอบ: ขั้นตอนแรกคือการเริ่มต้นใช้งาน`Document` วัตถุโดยการโหลดเอกสาร Word ที่มีตัวควบคุม ActiveX อย่าลืมเปลี่ยน`MyDir` ด้วยเส้นทางจริงไปยังไดเร็กทอรีที่มีเอกสาร

#### ถาม: ฉันจะนำตัวควบคุม ActiveX เข้าสู่เอกสารได้อย่างไร

 ตอบ: หากต้องการดึงข้อมูลตัวควบคุม ActiveX คุณต้องวนซ้ำแต่ละส่วน`Shape` ของเอกสารและตรวจสอบว่าเป็นตัวควบคุม ActiveX หรือไม่ ใช้`OleFormat` ทรัพย์สินของ`Shape` เพื่อเข้าถึง`OleControl` วัตถุและเรียกค้นคุณสมบัติที่จำเป็น

#### ถาม: ฉันสามารถอ่านคุณสมบัติใดของตัวควบคุม ActiveX ได้บ้าง

ตอบ: คุณสามารถอ่านคุณสมบัติต่างๆ ของตัวควบคุม ActiveX ได้ เช่น คำอธิบายภาพ ค่า สถานะเปิดใช้งานหรือปิดใช้งาน ประเภท และโหนดย่อยที่เกี่ยวข้องกับตัวควบคุม

#### ถาม: ฉันจะได้รับจำนวนตัวควบคุม ActiveX ทั้งหมดในเอกสารได้อย่างไร

 ตอบ: หากต้องการรับจำนวนตัวควบคุม ActiveX ทั้งหมดในเอกสาร คุณสามารถใช้ไฟล์`GetChildNodes` วิธีการของ`Document` วัตถุที่ระบุ`NodeType.Shape` พิมพ์และรวมถึงโหนดย่อยด้วย
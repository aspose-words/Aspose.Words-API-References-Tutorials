---
title: อ่านคุณสมบัติ XControl ที่ใช้งานอยู่จากไฟล์ Word
linktitle: อ่านคุณสมบัติ XControl ที่ใช้งานอยู่จากไฟล์ Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีอ่านคุณสมบัติการควบคุม ActiveX จากไฟล์ Word โดยใช้ Aspose.Words สำหรับ .NET ในคำแนะนำทีละขั้นตอน พัฒนาทักษะการทำงานอัตโนมัติของเอกสารของคุณ
type: docs
weight: 10
url: /th/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## การแนะนำ

ในยุคดิจิทัลปัจจุบัน ระบบอัตโนมัติเป็นกุญแจสำคัญในการเพิ่มประสิทธิภาพการทำงาน หากคุณกำลังทำงานกับเอกสาร Word ที่มีตัวควบคุม ActiveX คุณอาจต้องอ่านคุณสมบัติของเอกสารเหล่านั้นเพื่อวัตถุประสงค์ต่างๆ ตัวควบคุม ActiveX เช่น ช่องทำเครื่องหมายและปุ่ม สามารถเก็บข้อมูลสำคัญได้ การใช้ Aspose.Words สำหรับ .NET ทำให้คุณสามารถแยกและจัดการข้อมูลนี้โดยทางโปรแกรมได้อย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1.  Aspose.Words สำหรับ .NET Library: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/net/).
2. Visual Studio หรือ C# IDE ใดๆ: เพื่อเขียนและรันโค้ดของคุณ
3. เอกสาร Word ที่มีตัวควบคุม ActiveX: ตัวอย่างเช่น "ActiveX Controls.docx"
4. ความรู้พื้นฐานของ C#: จำเป็นต้องปฏิบัติตามความคุ้นเคยกับการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ

ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Words สำหรับ .NET กัน

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## ขั้นตอนที่ 1: โหลดเอกสาร Word

ในการเริ่มต้น คุณจะต้องโหลดเอกสาร Word ที่มีตัวควบคุม ActiveX

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## ขั้นตอนที่ 2: เริ่มต้นสตริงเพื่อเก็บคุณสมบัติ

ถัดไป เตรียมใช้งานสตริงว่างเพื่อจัดเก็บคุณสมบัติของตัวควบคุม ActiveX

```csharp
string properties = "";
```

## ขั้นตอนที่ 3: วนซ้ำรูปร่างในเอกสาร

เราจำเป็นต้องวนซ้ำรูปร่างทั้งหมดในเอกสารเพื่อค้นหาตัวควบคุม ActiveX

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // ประมวลผลตัวควบคุม ActiveX
    }
}
```

## ขั้นตอนที่ 4: แยกคุณสมบัติออกจากตัวควบคุม ActiveX

ภายในลูป ตรวจสอบว่าตัวควบคุมเป็น Forms2OleControl หรือไม่ หากเป็นเช่นนั้นให้ทำการหล่อและแยกคุณสมบัติออก

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## ขั้นตอนที่ 5: นับการควบคุม ActiveX ทั้งหมด

หลังจากวนซ้ำรูปร่างทั้งหมดแล้ว ให้นับจำนวนตัวควบคุม ActiveX ทั้งหมดที่พบ

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## ขั้นตอนที่ 6: แสดงคุณสมบัติ

สุดท้าย ให้พิมพ์คุณสมบัติที่แยกออกมาไปยังคอนโซล

```csharp
Console.WriteLine("\n" + properties);
```

## บทสรุป

และคุณก็ได้แล้ว! คุณได้เรียนรู้วิธีการอ่านคุณสมบัติการควบคุม ActiveX จากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว บทช่วยสอนนี้ครอบคลุมถึงการโหลดเอกสาร การวนซ้ำรูปร่าง และการแตกคุณสมบัติออกจากตัวควบคุม ActiveX ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถทำการแยกข้อมูลสำคัญจากเอกสาร Word ของคุณได้โดยอัตโนมัติ ซึ่งจะช่วยเพิ่มประสิทธิภาพเวิร์กโฟลว์ของคุณ

## คำถามที่พบบ่อย

### ตัวควบคุม ActiveX ในเอกสาร Word คืออะไร
ตัวควบคุม ActiveX เป็นวัตถุแบบโต้ตอบที่ฝังอยู่ในเอกสาร Word เช่น กล่องกาเครื่องหมาย ปุ่ม และช่องข้อความ ใช้ในการสร้างแบบฟอร์มและทำงานอัตโนมัติ

### ฉันสามารถแก้ไขคุณสมบัติของตัวควบคุม ActiveX โดยใช้ Aspose.Words สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Words สำหรับ .NET อนุญาตให้คุณแก้ไขคุณสมบัติของตัวควบคุม ActiveX โดยทางโปรแกรม

### Aspose.Words สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 Aspose.Words สำหรับ .NET ให้ทดลองใช้ฟรี แต่คุณจะต้องซื้อใบอนุญาตเพื่อใช้งานต่อไป คุณสามารถทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).

### ฉันสามารถใช้ Aspose.Words สำหรับ .NET กับภาษา .NET อื่นนอกเหนือจาก C# ได้หรือไม่
ได้ Aspose.Words สำหรับ .NET สามารถใช้กับภาษา .NET ใดก็ได้ รวมถึง VB.NET และ F#

### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Words สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาเอกสารรายละเอียดได้[ที่นี่](https://reference.aspose.com/words/net/).
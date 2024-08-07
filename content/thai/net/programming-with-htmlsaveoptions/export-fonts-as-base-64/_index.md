---
title: ส่งออกแบบอักษรเป็นฐาน 64
linktitle: ส่งออกแบบอักษรเป็นฐาน 64
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีส่งออกแบบอักษรเป็น Base64 โดยใช้ Aspose.Words สำหรับ .NET ในบทช่วยสอนโดยละเอียดนี้ ตรวจสอบให้แน่ใจว่าแบบอักษรถูกฝังและแสดงอย่างถูกต้องในไฟล์ HTML
type: docs
weight: 10
url: /th/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---
## การแนะนำ

เมื่อพูดถึงการจัดการเอกสาร Word โดยทางโปรแกรม Aspose.Words สำหรับ .NET คือขุมพลัง หนึ่งในคุณสมบัติที่ดีของมันคือการส่งออกแบบอักษรเป็น Base64 ภายในไฟล์ HTML ทำให้มั่นใจได้ว่าแบบอักษรจะถูกฝังและแสดงอย่างถูกต้องในเบราว์เซอร์และระบบต่างๆ ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีที่คุณสามารถบรรลุเป้าหมายนี้ได้ พร้อมที่จะทำให้ฟอนต์เอกสาร Word ของคุณเป็นมิตรกับเว็บแล้วหรือยัง? มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะพูดถึงการเขียนโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการแล้ว:

-  Aspose.Words สำหรับ .NET Library: คุณสามารถดาวน์โหลดได้จากไฟล์[กำหนดเผยแพร่](https://releases.aspose.com/words/net/) หน้าหนังสือ.
- .NET Development Environment: IDE ใดๆ เช่น Visual Studio จะทำงานได้อย่างสมบูรณ์แบบ
- ความรู้พื้นฐานของ C#: คุณไม่จำเป็นต้องเป็นมืออาชีพ แต่ความเข้าใจพื้นฐานจะช่วยได้

## นำเข้าเนมสเปซ

หากต้องการใช้ Aspose.Words สำหรับ .NET คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ ทำให้คลาสและวิธีการทั้งหมดพร้อมใช้งาน

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ก่อนอื่น มาตั้งค่าโปรเจ็กต์ของคุณและติดตั้งไลบรารี Aspose.Words กัน

### 1.1 สร้างโครงการใหม่

เปิด Visual Studio และสร้างโครงการแอปคอนโซลใหม่ ตั้งชื่อสิ่งที่มีความหมาย เช่น "ExportFontsBase64"

### 1.2 ติดตั้ง Aspose.Words

คุณสามารถติดตั้ง Aspose.Words สำหรับ .NET ผ่าน NuGet Package Manager:

1. คลิกขวาที่โครงการของคุณใน Solution Explorer
2. เลือก "จัดการแพ็คเกจ NuGet"
3. ค้นหา "Aspose.Words" และติดตั้ง

หรือคุณสามารถรันคำสั่งต่อไปนี้ใน Package Manager Console:

```sh
Install-Package Aspose.Words
```

## ขั้นตอนที่ 2: โหลดเอกสาร Word ของคุณ

ตอนนี้โปรเจ็กต์ของคุณได้รับการตั้งค่าแล้ว มาโหลดเอกสาร Word ที่คุณต้องการส่งออกฟอนต์กัน

### 2.1 กำหนดไดเร็กทอรีเอกสาร

ขั้นแรก ให้กำหนดไดเร็กทอรีที่มีเอกสาร Word ของคุณ:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

### 2.2 โหลดเอกสาร

 จากนั้น โหลดเอกสารของคุณโดยใช้ไฟล์`Document` ระดับ:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

ตรวจสอบให้แน่ใจว่า "Rendering.docx" อยู่ในไดเร็กทอรีที่คุณระบุ

## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการบันทึก HTML

 ในการส่งออกแบบอักษรเป็น Base64 เราจำเป็นต้องกำหนดค่า`HtmlSaveOptions`.


 สร้างอินสแตนซ์ของ`HtmlSaveOptions` และตั้งค่า`ExportFontsAsBase64`ทรัพย์สินเพื่อ`true`-

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

## ขั้นตอนที่ 4: บันทึกเอกสารเป็น HTML

สุดท้าย มาบันทึกเอกสารด้วยตัวเลือกที่กำหนดค่าไว้


 ใช้`Save` วิธีการของ`Document` คลาสเพื่อบันทึกเอกสารของคุณ:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

บรรทัดนี้จะบันทึกเอกสารของคุณเป็นไฟล์ HTML โดยมีแบบอักษรที่ส่งออกเป็น Base64 เพื่อให้แน่ใจว่าแบบอักษรจะฝังอยู่ภายใน HTML

## บทสรุป

ยินดีด้วย! คุณได้ส่งออกแบบอักษรเป็น Base64 จากเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET สำเร็จแล้ว เพื่อให้แน่ใจว่าแบบอักษรของคุณจะถูกรักษาและแสดงอย่างถูกต้องบนแพลตฟอร์มต่างๆ ไม่ว่าคุณกำลังเตรียมเอกสารสำหรับการแสดงผลบนเว็บหรือเพียงแค่รับประกันความเข้ากันได้ คุณลักษณะนี้มีประโยชน์อย่างเหลือเชื่อ

## คำถามที่พบบ่อย

### การเข้ารหัส Base64 คืออะไร
Base64 เป็นวิธีการเข้ารหัสข้อมูลไบนารี (เช่น แบบอักษร) ให้อยู่ในรูปแบบข้อความ ช่วยให้มั่นใจได้ถึงความเข้ากันได้กับรูปแบบข้อความเช่น HTML

### เหตุใดฉันจึงควรใช้ Base64 สำหรับแบบอักษรใน HTML
การใช้ Base64 ช่วยให้มั่นใจได้ว่าแบบอักษรจะถูกฝังโดยตรงใน HTML หลีกเลี่ยงปัญหาไฟล์แบบอักษรที่หายไปและรับประกันการแสดงผลที่สอดคล้องกัน

### ฉันสามารถใช้วิธีนี้กับแหล่งข้อมูลอื่น เช่น รูปภาพ ได้หรือไม่
อย่างแน่นอน! Aspose.Words สำหรับ .NET ช่วยให้คุณสามารถฝังทรัพยากรต่างๆ รวมถึงรูปภาพ เป็น Base64 ในไฟล์ HTML ของคุณ

### จะเกิดอะไรขึ้นหากเอกสารของฉันมีแบบอักษรหลายแบบ
ไม่มีปัญหา! Aspose.Words สำหรับ .NET จะฝังแบบอักษรทั้งหมดที่ใช้ในเอกสารของคุณเป็น Base64 ในไฟล์ HTML ที่ได้

### Aspose.Words สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 Aspose.Words สำหรับ .NET เป็นห้องสมุดเชิงพาณิชย์ อย่างไรก็ตาม คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[กำหนดเผยแพร่](https://releases.aspose.com/) หน้าหนังสือ.

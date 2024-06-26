---
title: ตั้งค่าโฟลเดอร์แบบอักษร True Type
linktitle: ตั้งค่าโฟลเดอร์แบบอักษร True Type
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าโฟลเดอร์แบบอักษรชนิดจริงเมื่อแสดงผลเอกสารโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fonts/set-true-type-fonts-folder/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อตั้งค่าโฟลเดอร์ฟอนต์ชนิดจริงเมื่อเรนเดอร์เอกสารโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีระบุโฟลเดอร์แบบกำหนดเองที่มีฟอนต์ True Type เพื่อใช้ในการเรนเดอร์เอกสารของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือตำแหน่งที่คุณต้องการบันทึกเอกสารที่แสดงผลที่แก้ไขแล้ว แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารที่จะแสดงผล
 ถัดไป คุณต้องโหลดเอกสารเพื่อแสดงผลโดยใช้`Document` ชั้นเรียน อย่าลืมระบุเส้นทางเอกสารที่ถูกต้อง

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ขั้นตอนที่ 3: ตั้งค่าโฟลเดอร์แบบอักษร True Type
ตอนนี้คุณสามารถระบุโฟลเดอร์ของฟอนต์ประเภทจริงเพื่อใช้เมื่อเรนเดอร์โดยการสร้างอินสแตนซ์ของ`FontSettings` คลาสและการใช้งาน`SetFontsFolder()` วิธีการตั้งค่าโฟลเดอร์แบบอักษร คุณสามารถระบุโฟลเดอร์แบบกำหนดเองที่มีแบบอักษร True Type ของคุณได้ พารามิเตอร์ที่สองถึง`SetFontsFolder()` ระบุว่าคุณต้องการค้นหาโฟลเดอร์ย่อยของโฟลเดอร์ที่ระบุด้วยหรือไม่

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## ขั้นตอนที่ 4: บันทึกเอกสารที่แสดงผล
 สุดท้าย คุณสามารถบันทึกเอกสารที่แสดงผลลงในไฟล์ได้โดยใช้`Save()` วิธีการของ`Document` ชั้นเรียน อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้อง

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับโฟลเดอร์แบบอักษร Set True Type โดยใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// โปรดทราบว่าการตั้งค่านี้จะแทนที่แหล่งแบบอักษรเริ่มต้นใดๆ ที่กำลังค้นหาตามค่าเริ่มต้น ตอนนี้จะค้นหาเฉพาะโฟลเดอร์เหล่านี้เท่านั้น
// แบบอักษรเมื่อเรนเดอร์หรือฝังแบบอักษร หากต้องการเพิ่มแหล่งแบบอักษรพิเศษในขณะที่เก็บแหล่งแบบอักษรของระบบไว้ ให้ใช้ทั้ง FontSettings.GetFontSources และ
// การตั้งค่าแบบอักษร SetFontSources แทน
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// ตั้งค่าแบบอักษร
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการตั้งค่าโฟลเดอร์ฟอนต์ชนิดจริงเมื่อเรนเดอร์เอกสารโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถระบุโฟลเดอร์แบบกำหนดเองที่มีฟอนต์ True Type เพื่อใช้ในการเรนเดอร์เอกสารของคุณได้อย่างง่ายดาย Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับการประมวลผลคำพร้อมแบบอักษรในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถควบคุมและปรับแต่งแบบอักษรที่ใช้ในการแสดงผลเอกสารตามความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะกำหนดค่าโฟลเดอร์แบบอักษร TrueType ใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการกำหนดค่าโฟลเดอร์แบบอักษร TrueType ใน Aspose.Words คุณสามารถใช้`SetTrueTypeFontsFolder` วิธีการของ`Fonts` คลาสที่ระบุตำแหน่งของโฟลเดอร์ที่มีแบบอักษร TrueType

#### ถาม: แบบอักษรประเภทใดที่ถือว่าเป็นแบบอักษร TrueType

ตอบ: ฟอนต์ TrueType เป็นรูปแบบฟอนต์ยอดนิยม มักใช้ในเอกสาร Word และมีนามสกุลไฟล์ .ttf หรือ .ttc

#### ถาม: ฉันสามารถระบุโฟลเดอร์แบบอักษร TrueType หลายโฟลเดอร์ใน Aspose.Words ได้หรือไม่

ตอบ: ได้ คุณสามารถระบุโฟลเดอร์แบบอักษร TrueType ได้หลายโฟลเดอร์ใน Aspose.Words โดยใช้`SetTrueTypeFontsFolder` วิธีการของ`Fonts` คลาสพร้อมรายการตำแหน่งโฟลเดอร์

#### ถาม: ฉันจะตรวจสอบโฟลเดอร์แบบอักษร TrueType ที่กำหนดค่าใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการตรวจสอบโฟลเดอร์ TrueType Fonts ที่กำหนดค่าไว้ใน Aspose.Words คุณสามารถใช้`GetTrueTypeFontsFolder` วิธีการของ`Fonts` คลาสเพื่อรับตำแหน่งของโฟลเดอร์ TrueType Fonts ที่กำหนดค่าไว้

#### ถาม: เหตุใดการกำหนดค่าโฟลเดอร์แบบอักษร TrueType ใน Aspose.Words จึงมีความสำคัญ

ตอบ: การตั้งค่าโฟลเดอร์แบบอักษร TrueType ใน Aspose.Words มีความสำคัญเนื่องจากช่วยให้ Aspose.Words ค้นหาแบบอักษรที่จำเป็นสำหรับการประมวลผลเอกสาร Word ช่วยให้มั่นใจได้ถึงความสอดคล้องในการจัดรูปแบบและลักษณะที่ปรากฏของเอกสาร แม้ในระบบที่แตกต่างกัน
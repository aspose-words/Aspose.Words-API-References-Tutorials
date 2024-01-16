---
title: ตั้งค่าอินสแตนซ์เริ่มต้นของโฟลเดอร์แบบอักษร
linktitle: ตั้งค่าอินสแตนซ์เริ่มต้นของโฟลเดอร์แบบอักษร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าโฟลเดอร์แบบอักษรเริ่มต้นเมื่อแสดงผลเอกสารโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fonts/set-fonts-folders-default-instance/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอนเพื่อตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้นเมื่อเรนเดอร์เอกสารโดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มาและให้คำแนะนำที่ครอบคลุมเพื่อช่วยให้คุณเข้าใจและนำคุณสมบัตินี้ไปใช้ในโครงการของคุณเอง ในตอนท้ายของบทช่วยสอนนี้ คุณจะรู้วิธีตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้นเพื่อใช้เมื่อเรนเดอร์เอกสารของคุณโดยใช้ Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ นี่คือตำแหน่งที่คุณต้องการบันทึกเอกสารที่แสดงผลที่แก้ไขแล้ว แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางที่เหมาะสม

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: ตั้งค่าโฟลเดอร์แบบอักษรเริ่มต้น
จากนั้นคุณสามารถตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้นได้โดยใช้ไฟล์`FontSettings.DefaultInstance` ชั้นเรียนและ`SetFontsFolder()` วิธี. ระบุเส้นทางไปยังโฟลเดอร์แบบอักษรที่คุณต้องการใช้เป็นโฟลเดอร์เริ่มต้น

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## ขั้นตอนที่ 3: โหลดเอกสารเพื่อแสดงผล
 ตอนนี้คุณสามารถโหลดเอกสารเพื่อแสดงผลโดยใช้`Document` ระดับ. อย่าลืมระบุเส้นทางเอกสารที่ถูกต้อง

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ขั้นตอนที่ 4: บันทึกเอกสารที่แสดงผล
 สุดท้าย คุณสามารถบันทึกเอกสารที่แสดงผลลงในไฟล์ได้โดยใช้`Save()` วิธีการของ`Document` ระดับ. อย่าลืมระบุเส้นทางและชื่อไฟล์ที่ถูกต้อง

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับอินสแตนซ์เริ่มต้นของโฟลเดอร์แบบอักษรที่ใช้ Aspose.Words สำหรับ .NET 

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้นเมื่อเรนเดอร์เอกสารโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถระบุโฟลเดอร์แบบอักษรที่จะใช้เป็นโฟลเดอร์เริ่มต้นได้อย่างง่ายดายเมื่อแสดงผลเอกสารของคุณ Aspose.Words นำเสนอ API ที่ทรงพลังและยืดหยุ่นสำหรับการประมวลผลคำพร้อมแบบอักษรในเอกสารของคุณ ด้วยความรู้นี้ คุณสามารถควบคุมและปรับแต่งแหล่งแบบอักษรที่ใช้ในการเรนเดอร์เอกสารของคุณตามความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้นใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการตั้งค่าโฟลเดอร์แบบอักษรเริ่มต้นใน Aspose.Words คุณต้องใช้ไฟล์`Fonts` ชั้นเรียนและ`SetFontsFolders` วิธีการระบุตำแหน่งโฟลเดอร์แบบอักษรที่กำหนดเอง

#### ถาม: การตั้งค่าโฟลเดอร์แบบอักษรเริ่มต้นส่งผลต่อเอกสาร Word ทั้งหมดที่ประมวลผลด้วย Aspose.Words หรือไม่

ตอบ: ใช่ การตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้นจะส่งผลต่อเอกสาร Word ทั้งหมดที่ประมวลผลด้วย Aspose.Words เมื่อคุณตั้งค่าโฟลเดอร์แบบอักษรเริ่มต้นแล้ว Aspose.Words จะใช้ตำแหน่งเหล่านี้เพื่อค้นหาแบบอักษรในเอกสารทั้งหมด

#### ถาม: ฉันสามารถตั้งค่าโฟลเดอร์แบบอักษรเริ่มต้นหลายโฟลเดอร์ใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถตั้งค่าโฟลเดอร์แบบอักษรเริ่มต้นได้หลายโฟลเดอร์ใน Aspose.Words คุณเพียงแค่ต้องระบุตำแหน่งของโฟลเดอร์แบบอักษรที่กำหนดเองโดยใช้`SetFontsFolders` วิธีการของ`Fonts` ระดับ.

#### ถาม: ฉันจะตรวจสอบโฟลเดอร์แบบอักษรเริ่มต้นที่ตั้งค่าไว้ใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการตรวจสอบโฟลเดอร์แบบอักษรเริ่มต้นที่กำหนดไว้ใน Aspose.Words คุณสามารถใช้ไฟล์`GetFolders` วิธีการของ`Fonts` คลาสเพื่อรับตำแหน่งของโฟลเดอร์แบบอักษรที่กำหนดค่าไว้

#### ถาม: การตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้นอนุญาตให้ฉันใช้ฟอนต์แบบกำหนดเองในเอกสาร Word ของฉันได้หรือไม่

ตอบ: ได้ โดยการตั้งค่าโฟลเดอร์ฟอนต์เริ่มต้น คุณสามารถใช้ฟอนต์แบบกำหนดเองในเอกสาร Word ของคุณได้ คุณเพียงแค่ต้องวางแบบอักษรในโฟลเดอร์ที่ระบุและ Aspose.Words จะใช้แบบอักษรเหล่านี้เมื่อสร้างหรือจัดการเอกสาร
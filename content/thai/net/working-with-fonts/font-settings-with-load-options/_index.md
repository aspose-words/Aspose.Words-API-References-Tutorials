---
title: การตั้งค่าแบบอักษรพร้อมตัวเลือกการโหลด
linktitle: การตั้งค่าแบบอักษรพร้อมตัวเลือกการโหลด
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีโหลดเอกสาร Word ด้วยตัวเลือกการโหลดแบบกำหนดเองและการตั้งค่าแบบอักษรที่เกี่ยวข้อง
type: docs
weight: 10
url: /th/net/working-with-fonts/font-settings-with-load-options/
---
ในบทช่วยสอนนี้ เราจะแสดงวิธีใช้ตัวเลือกการโหลดด้วยการตั้งค่าแบบอักษรในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET ตัวเลือกการโหลดช่วยให้คุณสามารถระบุการตั้งค่าเพิ่มเติมเมื่อโหลดเอกสาร รวมถึงการตั้งค่าแบบอักษร เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
 ขั้นแรก คุณต้องตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการโหลดด้วยการตั้งค่าแบบอักษร
 ต่อไปเราจะสร้างอินสแตนซ์ของ`LoadOptions`และระบุการตั้งค่าแบบอักษรโดยสร้างอินสแตนซ์ใหม่ของ`FontSettings` และมอบหมายให้`loadOptions.FontSettings`.

```csharp
// กำหนดค่าตัวเลือกการโหลดด้วยการตั้งค่าแบบอักษร
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();
```

## ขั้นตอนที่ 3: โหลดเอกสารพร้อมตัวเลือกการโหลด
 ตอนนี้เราจะโหลดเอกสารโดยใช้`LoadOptions` และระบุตัวเลือกการโหลดที่เรากำหนดค่าไว้

```csharp
// โหลดเอกสารพร้อมตัวเลือกการโหลด
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```

### ตัวอย่างซอร์สโค้ดสำหรับการตั้งค่าแบบอักษรพร้อมตัวเลือกการโหลดโดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = new FontSettings();
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เห็นวิธีการใช้ตัวเลือกการโหลดด้วยการตั้งค่าแบบอักษรในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ตัวเลือกการโหลดช่วยให้คุณปรับแต่งการโหลดเอกสารโดยการระบุการตั้งค่าเพิ่มเติม รวมถึงการตั้งค่าแบบอักษร คุณสามารถใช้คุณสมบัตินี้เพื่อปรับแต่งการโหลดเอกสารให้ตรงตามความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: ฉันจะระบุแบบอักษรเริ่มต้นเมื่อโหลดเอกสารลงใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการระบุแบบอักษรเริ่มต้นเมื่อโหลดเอกสารใน Aspose.Words คุณสามารถใช้`LoadOptions` คลาสและตั้งค่า`DefaultFontName` คุณสมบัติเป็นชื่อของแบบอักษรที่ต้องการ

#### ถาม: ฉันสามารถระบุการตั้งค่าแบบอักษรอื่นใดด้วยตัวเลือกการโหลดใน Aspose.Words ได้บ้าง

ตอบ: นอกจากการระบุแบบอักษรเริ่มต้นแล้ว คุณยังสามารถระบุการตั้งค่าแบบอักษรอื่นๆ เช่น การเข้ารหัสเริ่มต้นโดยใช้คุณสมบัติที่เหมาะสมของ`LoadOptions` ชั้นเรียน เช่น`DefaultEncoding`.

#### ถาม: จะเกิดอะไรขึ้นหากแบบอักษรเริ่มต้นที่ระบุไม่พร้อมใช้งานเมื่อโหลดเอกสาร

ตอบ: หากไม่มีแบบอักษรเริ่มต้นที่ระบุเมื่อโหลดเอกสารใน Aspose.Words จะใช้แบบอักษรทดแทนเพื่อแสดงข้อความในเอกสาร นี่อาจทำให้รูปลักษณ์แตกต่างจากแบบอักษรดั้งเดิมเล็กน้อย

#### ถาม: ฉันสามารถระบุการตั้งค่าแบบอักษรที่แตกต่างกันสำหรับเอกสารที่อัพโหลดแต่ละฉบับได้หรือไม่

 ตอบ: ได้ คุณสามารถระบุการตั้งค่าแบบอักษรที่แตกต่างกันสำหรับเอกสารที่โหลดแต่ละรายการได้โดยใช้อินสแตนซ์ที่แยกกันของ`LoadOptions` และตั้งค่าแบบอักษรที่ต้องการสำหรับแต่ละอินสแตนซ์ ซึ่งช่วยให้คุณปรับแต่งลักษณะแบบอักษรสำหรับแต่ละเอกสารได้อย่างอิสระ
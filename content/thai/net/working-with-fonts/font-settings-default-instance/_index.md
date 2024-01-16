---
title: การตั้งค่าแบบอักษร อินสแตนซ์เริ่มต้น
linktitle: การตั้งค่าแบบอักษร อินสแตนซ์เริ่มต้น
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีกำหนดการตั้งค่าแบบอักษรเริ่มต้นในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fonts/font-settings-default-instance/
---

ในบทช่วยสอนนี้ เราจะอธิบายวิธีกำหนดการตั้งค่าแบบอักษรเริ่มต้นในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การตั้งค่าแบบอักษรเริ่มต้นช่วยให้คุณสามารถระบุแหล่งที่มาของแบบอักษรที่ใช้ในการโหลดและแสดงผลเอกสาร เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

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

## ขั้นตอนที่ 2: กำหนดการตั้งค่าแบบอักษรเริ่มต้น
 ต่อไปเราจะสร้างอินสแตนซ์ของ`FontSettings` โดยใช้`FontSettings.DefaultInstance`จากนั้นเราจะระบุแหล่งแบบอักษรที่ใช้ในการโหลดและแสดงผลเอกสาร ในตัวอย่างนี้ เรากำลังใช้แหล่งแบบอักษรของระบบและแหล่งแบบอักษรของโฟลเดอร์

```csharp
// กำหนดการตั้งค่าแบบอักษรเริ่มต้น
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## ขั้นตอนที่ 3: อัปโหลดเอกสารด้วยการตั้งค่าแบบอักษร
 ตอนนี้เราจะโหลดเอกสารโดยใช้`LoadOptions` และระบุการตั้งค่าแบบอักษรที่จะใช้

```csharp
// โหลดเอกสารด้วยการตั้งค่าแบบอักษร
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### ตัวอย่างซอร์สโค้ดสำหรับอินสแตนซ์เริ่มต้นการตั้งค่าแบบอักษรโดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เห็นวิธีกำหนดการตั้งค่าแบบอักษรเริ่มต้นในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET ด้วยการระบุแหล่งแบบอักษรที่ใช้ในการโหลดและแสดงผลเอกสาร คุณสามารถควบคุมลักษณะที่ปรากฏของแบบอักษรในเอกสารของคุณได้ คุณสามารถใช้คุณสมบัตินี้เพื่อปรับแต่งการตั้งค่าแบบอักษรในโครงการของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะตั้งค่าแบบอักษรเริ่มต้นใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการตั้งค่าแบบอักษรเริ่มต้นใน Aspose.Words คุณสามารถใช้`FontSettings` ชั้นเรียนและ`DefaultFontName` คุณสมบัติระบุชื่อแบบอักษรที่ต้องการ

#### ถาม: ฉันสามารถระบุขนาดตัวอักษรเริ่มต้นใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถระบุขนาดตัวอักษรเริ่มต้นใน Aspose.Words ได้โดยใช้`DefaultFontSize` ทรัพย์สินของ`FontSettings` ระดับ. คุณสามารถกำหนดขนาดจุดที่ต้องการได้

#### ถาม: เป็นไปได้ไหมที่จะตั้งค่าสีแบบอักษรเริ่มต้นใน Aspose.Words

 ตอบ: ได้ คุณสามารถตั้งค่าสีแบบอักษรเริ่มต้นใน Aspose.Words ได้โดยใช้`DefaultColor` ทรัพย์สินของ`FontSettings` ระดับ. คุณสามารถระบุสีโดยใช้ค่า RGB หรือชื่อที่กำหนดไว้ล่วงหน้าได้

#### ถาม: การตั้งค่าแบบอักษรเริ่มต้นมีผลกับเอกสารทั้งหมดหรือไม่

ตอบ: ได้ การตั้งค่าแบบอักษรเริ่มต้นจะมีผลกับเอกสารทั้งหมดที่สร้างหรือแก้ไขใน Aspose.Words เว้นแต่จะมีการตั้งค่าเฉพาะสำหรับเอกสารแต่ละฉบับ
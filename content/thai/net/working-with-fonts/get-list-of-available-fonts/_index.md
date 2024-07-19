---
title: รับรายการแบบอักษรที่มีอยู่
linktitle: รับรายการแบบอักษรที่มีอยู่
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีรับรายการแบบอักษรที่มีอยู่ใน Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fonts/get-list-of-available-fonts/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีรับรายการแบบอักษรที่มีอยู่ใน Aspose.Words สำหรับ .NET รายการแบบอักษรที่พร้อมใช้งานช่วยให้คุณทราบว่าคุณสามารถใช้แบบอักษรใดในเอกสารของคุณได้ เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

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

## ขั้นตอนที่ 2: กำหนดค่าแหล่งแบบอักษร
 ต่อไปเราจะสร้างอินสแตนซ์ของ`FontSettings` และรับแหล่งแบบอักษรที่มีอยู่โดยใช้`GetFontsSources()` วิธี. นอกจากนี้เรายังจะเพิ่มแหล่งแบบอักษรใหม่โดยการระบุโฟลเดอร์ที่มีแบบอักษร

```csharp
// กำหนดค่าแหล่งแบบอักษร
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// เพิ่มแหล่งแบบอักษรใหม่
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## ขั้นตอนที่ 3: รับรายการแบบอักษรที่มีอยู่
 ตอนนี้เราจะเรียกดูแบบอักษรที่มีอยู่โดยใช้`GetAvailableFonts()` วิธีการในแหล่งแบบอักษรที่อัปเดตครั้งแรก

```csharp
// รับรายการแบบอักษรที่มีอยู่
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### ตัวอย่างซอร์สโค้ดสำหรับรับรายการแบบอักษรที่ใช้ได้โดยใช้ Aspose.Words สำหรับ .NET 

```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// เพิ่มแหล่งที่มาของโฟลเดอร์ใหม่ซึ่งจะสั่งให้ Aspose.Words ค้นหาแบบอักษรในโฟลเดอร์ต่อไปนี้
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// เพิ่มโฟลเดอร์ที่กำหนดเองซึ่งมีแบบอักษรของเราลงในรายการแหล่งแบบอักษรที่มีอยู่
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีรับรายการแบบอักษรที่มีอยู่ใน Aspose.Words สำหรับ .NET ซึ่งจะช่วยให้คุณทราบว่าคุณสามารถใช้แบบอักษรใดในเอกสารของคุณได้ คุณสามารถใช้คุณสมบัตินี้เพื่อเลือกแบบอักษรที่เหมาะสมกับความต้องการของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะดึงรายการแบบอักษรที่มีอยู่ใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการดึงรายการแบบอักษรที่มีอยู่ใน Aspose.Words คุณสามารถใช้`FontsProvider` ชั้นเรียนและ`GetAvailableFonts` วิธี. วิธีนี้จะส่งคืนรายการแบบอักษรทั้งหมดที่ติดตั้งในระบบของคุณ

#### ถาม: ฉันสามารถกรองรายการแบบอักษรที่มีอยู่ตามเกณฑ์ที่กำหนดใน Aspose.Words ได้หรือไม่

ตอบ: ได้ คุณสามารถกรองรายการแบบอักษรที่มีอยู่ใน Aspose.Words โดยใช้เกณฑ์เฉพาะได้ ตัวอย่างเช่น คุณสามารถกรองแบบอักษรตามตระกูล สไตล์ หรือภาษาได้

#### ถาม: ฉันจะใช้รายการแบบอักษรที่มีอยู่ในเอกสาร Word ได้อย่างไร

 ตอบ: หากต้องการใช้รายการแบบอักษรที่มีอยู่ในเอกสาร Word ของคุณ คุณสามารถเรียกดูรายการและเลือกแบบอักษรที่เหมาะสมโดยใช้วิธีการและคุณสมบัติของ`FontSettings` คลาสใน Aspose.Words
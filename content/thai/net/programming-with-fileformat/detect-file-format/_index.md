---
title: ตรวจจับรูปแบบไฟล์เอกสาร
linktitle: ตรวจจับรูปแบบไฟล์เอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีตรวจจับรูปแบบไฟล์เอกสารโดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนที่ครอบคลุมนี้
type: docs
weight: 10
url: /th/net/programming-with-fileformat/detect-file-format/
---
## การแนะนำ

ในโลกดิจิทัลปัจจุบัน การจัดการรูปแบบเอกสารที่แตกต่างกันอย่างมีประสิทธิภาพเป็นสิ่งสำคัญ ไม่ว่าคุณจะจัดการ Word, PDF, HTML หรือรูปแบบอื่น ๆ ความสามารถในการตรวจจับและประมวลผลไฟล์เหล่านี้อย่างถูกต้องสามารถช่วยประหยัดเวลาและความพยายามได้มาก ในบทช่วยสอนนี้ เราจะสำรวจวิธีการตรวจหารูปแบบไฟล์เอกสารโดยใช้ Aspose.Words สำหรับ .NET คู่มือนี้จะอธิบายทุกสิ่งที่คุณจำเป็นต้องรู้ ตั้งแต่ข้อกำหนดเบื้องต้นไปจนถึงคำแนะนำทีละขั้นตอนโดยละเอียด

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:

-  Aspose.Words สำหรับ .NET: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/net/) - ตรวจสอบให้แน่ใจว่าคุณมีใบอนุญาตที่ถูกต้อง ถ้าไม่คุณสามารถได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
- Visual Studio: เวอร์ชันล่าสุดใด ๆ จะทำงานได้ดี
- .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งเวอร์ชันที่ถูกต้อง

## นำเข้าเนมสเปซ

ในการเริ่มต้น คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อให้ง่ายต่อการติดตาม

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรี

ขั้นแรก เราต้องตั้งค่าไดเร็กทอรีที่จะจัดเรียงไฟล์ตามรูปแบบของไฟล์

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// สร้างไดเร็กทอรีหากยังไม่มี
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## ขั้นตอนที่ 2: รับรายการไฟล์

ต่อไป เราจะแสดงรายการไฟล์จากไดเร็กทอรี ไม่รวมเอกสารที่เสียหาย

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## ขั้นตอนที่ 3: ตรวจจับรูปแบบไฟล์

ตอนนี้ เราวนซ้ำแต่ละไฟล์และตรวจจับรูปแบบของไฟล์โดยใช้ Aspose.Words

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // แสดงประเภทเอกสาร
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## บทสรุป

การตรวจจับรูปแบบไฟล์เอกสารโดยใช้ Aspose.Words สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อน ด้วยการตั้งค่าไดเร็กทอรี รับรายการไฟล์ และการใช้ Aspose.Words เพื่อตรวจจับรูปแบบไฟล์ คุณสามารถจัดระเบียบและจัดการเอกสารของคุณได้อย่างมีประสิทธิภาพ วิธีการนี้ไม่เพียงแต่ช่วยประหยัดเวลา แต่ยังช่วยให้คุณจัดการรูปแบบเอกสารต่างๆ ได้อย่างถูกต้องอีกด้วย

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words for .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับเอกสาร Word โดยทางโปรแกรม ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงเอกสารในรูปแบบต่างๆ

### Aspose.Words สามารถตรวจจับเอกสารที่เข้ารหัสได้หรือไม่
ใช่ Aspose.Words สามารถตรวจจับได้ว่าเอกสารถูกเข้ารหัสหรือไม่ และคุณสามารถจัดการเอกสารดังกล่าวได้

### Aspose.Words ตรวจพบรูปแบบใดได้บ้าง
Aspose.Words สามารถตรวจจับรูปแบบได้หลากหลาย รวมถึง DOC, DOCX, RTF, HTML, MHTML, ODT และอื่นๆ อีกมากมาย

### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Words ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[กำหนดให้จัดซื้อ](https://purchase.aspose.com/temporary-license/) หน้าหนังสือ.

### ฉันจะหาเอกสารสำหรับ Aspose.Words ได้ที่ไหน
 สามารถดูเอกสารประกอบสำหรับ Aspose.Words ได้[ที่นี่](https://reference.aspose.com/words/net/).

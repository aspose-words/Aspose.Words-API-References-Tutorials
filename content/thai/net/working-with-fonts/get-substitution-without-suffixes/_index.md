---
title: รับการทดแทนโดยไม่มีคำต่อท้าย
linktitle: รับการทดแทนโดยไม่มีคำต่อท้าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีจัดการการทดแทนแบบอักษรโดยไม่มีส่วนต่อท้ายใน Aspose.Words for .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อให้แน่ใจว่าเอกสารของคุณจะดูสมบูรณ์แบบทุกครั้ง
type: docs
weight: 10
url: /th/net/working-with-fonts/get-substitution-without-suffixes/
---
## การแนะนำ

ยินดีต้อนรับสู่คำแนะนำที่ครอบคลุมเกี่ยวกับการจัดการการทดแทนแบบอักษรโดยใช้ Aspose.Words สำหรับ .NET หากคุณเคยประสบปัญหากับแบบอักษรที่ปรากฏไม่ถูกต้องในเอกสารของคุณ คุณมาถูกที่แล้ว บทช่วยสอนนี้จะนำคุณไปสู่กระบวนการทีละขั้นตอนเพื่อจัดการการแทนที่แบบอักษรโดยไม่มีส่วนต่อท้ายอย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานของ C#: การทำความเข้าใจการเขียนโปรแกรม C# จะทำให้ง่ายต่อการปฏิบัติตามและดำเนินการตามขั้นตอนต่างๆ
-  Aspose.Words สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[ลิงค์ดาวน์โหลด](https://releases.aspose.com/words/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาเช่น Visual Studio เพื่อเขียนและรันโค้ดของคุณ
-  เอกสารตัวอย่าง: เอกสารตัวอย่าง (เช่น`Rendering.docx`) เพื่อใช้งานในระหว่างบทช่วยสอนนี้

## นำเข้าเนมสเปซ

ขั้นแรก เราต้องนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่ได้รับจาก Aspose.Words

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System.Collections.Generic;
```

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร

ในการเริ่มต้น ให้ระบุไดเร็กทอรีที่มีเอกสารของคุณอยู่ ซึ่งจะช่วยในการค้นหาเอกสารที่คุณต้องการใช้งาน

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: ตั้งค่าตัวจัดการคำเตือนการทดแทน

ต่อไป เราต้องตั้งค่าตัวจัดการคำเตือนที่จะแจ้งให้เราทราบทุกครั้งที่มีการแทนที่แบบอักษรในระหว่างการประมวลผลเอกสาร นี่เป็นสิ่งสำคัญสำหรับการตรวจจับและจัดการกับปัญหาแบบอักษร

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## ขั้นตอนที่ 3: เพิ่มแหล่งแบบอักษรที่กำหนดเอง

ในขั้นตอนนี้ เราจะเพิ่มแหล่งแบบอักษรที่กำหนดเองเพื่อให้แน่ใจว่า Aspose.Words สามารถค้นหาและใช้แบบอักษรที่ถูกต้องได้ สิ่งนี้มีประโยชน์อย่างยิ่งหากคุณมีแบบอักษรเฉพาะเก็บไว้ในไดเร็กทอรีที่กำหนดเอง

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

ในรหัสนี้:
-  เราดึงแหล่งแบบอักษรปัจจุบันและเพิ่มใหม่`FolderFontSource` ชี้ไปที่ไดเร็กทอรีแบบอักษรที่กำหนดเองของเรา (`C:\\MyFonts\\`-
- จากนั้นเราจะอัปเดตแหล่งแบบอักษรด้วยรายการใหม่นี้

## ขั้นตอนที่ 4: บันทึกเอกสาร

สุดท้าย ให้บันทึกเอกสารหลังจากใช้การตั้งค่าการแทนที่แบบอักษร สำหรับบทช่วยสอนนี้ เราจะบันทึกเป็น PDF

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## ขั้นตอนที่ 5: สร้างคลาสตัวจัดการคำเตือน

 เพื่อจัดการคำเตือนอย่างมีประสิทธิภาพ ให้สร้างคลาสแบบกำหนดเองที่ใช้`IWarningCallback` อินเตอร์เฟซ คลาสนี้จะบันทึกและบันทึกคำเตือนการแทนที่แบบอักษร

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

ในชั้นเรียนนี้:
-  ที่`Warning`วิธีการบันทึกคำเตือนที่เกี่ยวข้องกับการทดแทนแบบอักษร
-  ที่`FontWarnings` คอลเลกชันจะจัดเก็บคำเตือนเหล่านี้เพื่อการตรวจสอบหรือบันทึกเพิ่มเติม

## บทสรุป

ตอนนี้คุณเชี่ยวชาญกระบวนการจัดการการทดแทนแบบอักษรโดยไม่มีส่วนต่อท้ายโดยใช้ Aspose.Words สำหรับ .NET แล้ว ความรู้นี้จะช่วยให้แน่ใจว่าเอกสารของคุณคงรูปลักษณ์ที่ต้องการไว้ โดยไม่คำนึงถึงแบบอักษรที่มีอยู่ในระบบ ทดลองใช้การตั้งค่าและแหล่งที่มาต่างๆ ต่อไปเพื่อใช้ประโยชน์จากพลังของ Aspose.Words ได้อย่างเต็มที่

## คำถามที่พบบ่อย

### ฉันจะใช้แบบอักษรจากไดเร็กทอรีที่กำหนดเองหลายรายการได้อย่างไร

 คุณสามารถเพิ่มได้หลายรายการ`FolderFontSource` อินสแตนซ์ไปยัง`fontSources` แสดงรายการและอัปเดตแหล่งแบบอักษรตามลำดับ

### ฉันจะดาวน์โหลด Aspose.Words for .NET รุ่นทดลองใช้ฟรีได้ที่ไหน

 คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[กำหนดหน้าทดลองใช้ฟรี](https://releases.aspose.com/).

###  ฉันสามารถจัดการกับคำเตือนหลายประเภทโดยใช้`IWarningCallback`?

 ใช่`IWarningCallback` อินเทอร์เฟซช่วยให้คุณสามารถจัดการกับคำเตือนประเภทต่างๆ ได้ ไม่ใช่แค่การแทนที่แบบอักษรเท่านั้น

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words ได้ที่ไหน

 สำหรับการสนับสนุนโปรดไปที่[ฟอรัมสนับสนุน Aspose.Words](https://forum.aspose.com/c/words/8).

### สามารถซื้อใบอนุญาตชั่วคราวได้หรือไม่?

 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
---
title: รับการทดแทนโดยไม่มีคำต่อท้าย
linktitle: รับการทดแทนโดยไม่มีคำต่อท้าย
second_title: Aspose.Words API การประมวลผลเอกสาร
description: ในบทช่วยสอนนี้ เรียนรู้วิธีรับการแทนที่แบบไม่มีส่วนต่อท้ายในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-fonts/get-substitution-without-suffixes/
---

ในบทช่วยสอนนี้ เราจะแสดงวิธีรับการแทนที่โดยไม่มีส่วนต่อท้ายในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET การทดแทนที่ไม่มีส่วนต่อท้ายจะใช้ในการแก้ปัญหาการทดแทนแบบอักษรเมื่อแสดงหรือพิมพ์เอกสาร เราจะอธิบายทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณ

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

## ขั้นตอนที่ 2: โหลดเอกสารและกำหนดค่าการทดแทนโดยไม่มีส่วนต่อท้าย
 ต่อไปเราจะโหลดเอกสารโดยใช้ไฟล์`Document` คลาสและกำหนดค่าการทดแทนแบบไม่มีส่วนต่อท้ายโดยใช้`DocumentSubstitutionWarnings` ระดับ. นอกจากนี้เรายังจะเพิ่มแหล่งแบบอักษรโดยการระบุโฟลเดอร์ที่มีแบบอักษร

```csharp
// โหลดเอกสารและกำหนดค่าการทดแทนโดยไม่มีส่วนต่อท้าย
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## ขั้นตอนที่ 3: บันทึกเอกสาร
สุดท้ายนี้ เราจะบันทึกเอกสารโดยใช้การแทนที่แบบไม่มีส่วนต่อท้าย

```csharp
// บันทึกเอกสาร
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### ตัวอย่างซอร์สโค้ดสำหรับรับการทดแทนโดยไม่มีส่วนต่อท้ายโดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## บทสรุป
ในบทช่วยสอนนี้ เราเห็นวิธีรับการแทนที่โดยไม่มีส่วนต่อท้ายในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET การแทนที่โดยไม่มีส่วนต่อท้ายมีประโยชน์ในการแก้ปัญหาการแทนที่แบบอักษร คุณสามารถใช้คุณสมบัตินี้เพื่อปรับปรุงการแสดงผลและการพิมพ์เอกสารของคุณได้

### คำถามที่พบบ่อย

#### ถาม: เหตุใด Aspose.Words จึงเพิ่มส่วนต่อท้ายในการแทนที่แบบอักษร

ตอบ: Aspose.Words เพิ่มส่วนต่อท้ายให้กับการแทนที่แบบอักษรเพื่อหลีกเลี่ยงความขัดแย้งระหว่างแบบอักษรดั้งเดิมและแบบอักษรที่ถูกแทนที่ สิ่งนี้ช่วยให้มั่นใจได้ถึงความเข้ากันได้สูงสุดเมื่อแปลงและจัดการเอกสาร

#### ถาม: ฉันจะดึงข้อมูลการแทนที่แบบอักษรโดยไม่มีส่วนต่อท้ายใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการดึงข้อมูลการแทนที่แบบอักษรโดยไม่มีส่วนต่อท้ายใน Aspose.Words คุณสามารถใช้ไฟล์`FontSubstitutionSettings` ชั้นเรียนและ`RemoveSuffixes` คุณสมบัติ. การตั้งค่าคุณสมบัตินี้เป็น`true` จะได้รับการทดแทนแบบอักษรโดยไม่มีส่วนต่อท้ายที่เพิ่ม

#### ถาม: เป็นไปได้หรือไม่ที่จะปิดใช้งานการเพิ่มส่วนต่อท้ายให้กับการทดแทนแบบอักษรใน Aspose.Words

ตอบ: ไม่ได้ ไม่สามารถปิดใช้งานการเพิ่มส่วนต่อท้ายให้กับการแทนที่แบบอักษรใน Aspose.Words ได้ ส่วนต่อท้ายจะถูกเพิ่มตามค่าเริ่มต้นเพื่อให้มั่นใจถึงความเข้ากันได้และความสอดคล้องของเอกสาร

#### ถาม: ฉันจะกรองส่วนต่อท้ายที่ไม่ต้องการในการทดแทนแบบอักษรใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการกรองส่วนต่อท้ายที่ไม่ต้องการในการทดแทนแบบอักษรใน Aspose.Words คุณสามารถใช้เทคนิคการประมวลผลสตริง เช่น การใช้`Replace` หรือ`Substring` วิธีการลบส่วนต่อท้ายเฉพาะที่คุณไม่ต้องการรวมไว้
---
title: ใช้อักขระแท็บต่อระดับสำหรับการเยื้องรายการ
linktitle: ใช้อักขระแท็บต่อระดับสำหรับการเยื้องรายการ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีใช้รายการเยื้องพร้อมฟีเจอร์อักขระแท็บใน Aspose.Words สำหรับ .NET ประหยัดเวลาและปรับปรุงขั้นตอนการทำงานของคุณด้วยคุณสมบัติอันทรงพลังนี้
type: docs
weight: 10
url: /th/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

ในบทช่วยสอนนี้ เราจะสำรวจซอร์สโค้ด C# ที่ให้มาสำหรับฟีเจอร์ "ใช้อักขระแท็บหนึ่งตัวต่อระดับสำหรับการเยื้องรายการ" ด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถใช้อักขระแท็บสำหรับการเยื้องรายการในแต่ละระดับ ซึ่งให้ความยืดหยุ่นและการควบคุมลักษณะที่ปรากฏของเอกสารของคุณได้มากขึ้น

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสมแล้ว

## ขั้นตอนที่ 2: การสร้างเอกสารและตัวสร้าง

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ในขั้นตอนนี้ เราจะสร้างใหม่`Document` วัตถุและสิ่งที่เกี่ยวข้อง`DocumentBuilder` วัตถุ. วัตถุเหล่านี้จะช่วยให้เราจัดการและสร้างเอกสารของเราได้

## ขั้นตอนที่ 3: การสร้างรายการที่มีการเยื้องสามระดับ

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

ในขั้นตอนนี้ เราใช้รูปแบบเริ่มต้นของหมายเลขรายการโดยใช้`ApplyNumberDefault()` วิธีการจัดรูปแบบรายการ ต่อไป เราจะเพิ่มสามรายการในรายการของเราโดยใช้ตัวสร้างเอกสาร`Writeln()` และ`Write()` วิธีการ เราใช้`ListIndent()` วิธีการเพิ่มการเยื้องในแต่ละระดับ

## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกการบันทึก

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 ในขั้นตอนนี้ เรากำหนดค่าตัวเลือกสำหรับการบันทึกเอกสาร เราสร้างใหม่`TxtSaveOptions` วัตถุและตั้งค่า`ListIndentation.Count` คุณสมบัติเป็น 1 เพื่อระบุจำนวนอักขระแท็บต่อระดับการเยื้อง เรายังตั้งค่า`ListIndentation.Character` คุณสมบัติเป็น '\t' เพื่อระบุว่าเราต้องการใช้อักขระแท็บ

## ขั้นตอนที่ 5: บันทึกเอกสาร

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 ในขั้นตอนสุดท้ายนี้ เราจะบันทึกเอกสารด้วยตัวเลือกการบันทึกที่ระบุ เราใช้`Save()` วิธีการของเอกสารผ่านเส้นทางแบบเต็มของไฟล์เอาต์พุตและตัวเลือกการบันทึก


ตอนนี้คุณสามารถรันซอร์สโค้ดเพื่อสร้างเอกสารที่มีการเยื้องรายการโดยใช้อักขระแท็บ ไฟล์เอาต์พุตจะถูกบันทึกในไดเร็กทอรีที่ระบุชื่อ "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt"

### ตัวอย่างซอร์สโค้ดสำหรับฟีเจอร์ใช้อักขระแท็บหนึ่งตัวต่อระดับสำหรับการเยื้องรายการด้วย Aspose.Words สำหรับ .NET:

```csharp

// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// สร้างรายการที่มีการเยื้องสามระดับ
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

เมื่อคุณสร้างเอกสารด้วยการเยื้องรายการโดยใช้อักขระแท็บเสร็จแล้ว คุณสามารถใช้ Markdown เพื่อจัดรูปแบบเนื้อหาบทความของคุณได้ ตรวจสอบให้แน่ใจว่าใช้แท็กการจัดรูปแบบที่เหมาะสมเพื่อเน้นชื่อ คำบรรยาย และซอร์สโค้ดที่รวมไว้

### คำถามที่พบบ่อย

#### ถาม: คุณลักษณะ "ใช้อักขระแท็บหนึ่งตัวต่อระดับสำหรับการเยื้องรายการ" กับ Aspose.Words สำหรับ .NET คืออะไร
คุณลักษณะ "ใช้อักขระแท็บหนึ่งตัวต่อระดับสำหรับการเยื้องรายการ" ด้วย Aspose.Words สำหรับ .NET ช่วยให้สามารถใช้อักขระแท็บสำหรับการเยื้องรายการในแต่ละระดับ ซึ่งให้ความยืดหยุ่นและการควบคุมลักษณะที่ปรากฏของเอกสารของคุณมากขึ้น

#### ถาม: ฉันจะใช้ฟีเจอร์นี้กับ Aspose.Words สำหรับ .NET ได้อย่างไร
เมื่อต้องการใช้คุณลักษณะนี้กับ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนเหล่านี้:

ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณโดยเพิ่มข้อมูลอ้างอิงที่จำเป็นและนำเข้าเนมสเปซที่เหมาะสม

 สร้างใหม่`Document` วัตถุและสิ่งที่เกี่ยวข้อง`DocumentBuilder` วัตถุ.

 ใช้`DocumentBuilder` เพื่อสร้างรายการที่มีการเยื้องหลายระดับโดยใช้วิธีการ`ApplyNumberDefault()` เพื่อใช้รูปแบบหมายเลขรายการเริ่มต้น`Writeln()` และ`Write()` เพื่อเพิ่มรายการลงในรายการและ`ListIndent()`เพื่อเพิ่มการเยื้องในแต่ละระดับ

 กำหนดค่าตัวเลือกการบันทึกโดยการสร้างไฟล์`TxtSaveOptions` วัตถุและการตั้งค่าคุณสมบัติ`ListIndentation.Count` เป็นจำนวนอักขระแท็บต่อระดับและ`ListIndentation.Character` ถึง`'\t'` เพื่อใช้อักขระแท็บ

 บันทึกเอกสารโดยใช้`Save()` วิธีการของเอกสารที่ระบุเส้นทางแบบเต็มของไฟล์เอาต์พุตและตัวเลือกการบันทึก

#### ถาม: เป็นไปได้ไหมที่จะปรับแต่งจำนวนอักขระแท็บต่อระดับสำหรับการเยื้องรายการ?
 ได้ คุณสามารถกำหนดจำนวนอักขระแท็บต่อระดับสำหรับการเยื้องรายการได้โดยการเปลี่ยนค่าของ`ListIndentation.Count` ทรัพย์สินใน`TxtSaveOptions` ระดับ. คุณสามารถระบุจำนวนอักขระแท็บที่คุณต้องการสำหรับการเยื้องแต่ละระดับได้

#### ถาม: ฉันสามารถใช้อักขระอื่นใดในการเยื้องรายการด้วย Aspose.Words สำหรับ .NET ได้หรือไม่
 นอกจากอักขระแท็บแล้ว คุณยังสามารถใช้อักขระอื่นสำหรับการเยื้องรายการด้วย Aspose.Words สำหรับ .NET คุณสามารถตั้งค่า`ListIndentation.Character` คุณสมบัติให้กับอักขระที่ต้องการ เช่น ช่องว่าง (`' '`) สำหรับการเยื้องรายการ

#### ถาม: Aspose.Words สำหรับ .NET มีคุณสมบัติอื่นใดในการจัดการรายการหรือไม่
ใช่ Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติมากมายสำหรับการจัดการรายการในเอกสาร Word คุณสามารถสร้างรายการที่เรียงลำดับเลขหรือสัญลักษณ์แสดงหัวข้อย่อย ตั้งค่าระดับการเยื้อง ปรับแต่งลักษณะของรายการ เพิ่มรายการ และอื่นๆ อีกมากมาย
---
title: รีสตาร์ทหมายเลขรายการ
linktitle: รีสตาร์ทหมายเลขรายการ
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรีเซ็ตหมายเลขของรายการในเอกสาร Word ด้วย Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/working-with-list/restart-list-number/
---
ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแสดงวิธีรีเซ็ตหมายเลขของรายการในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่า Aspose.Words สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Releases]https://releases.aspose.com/words/net/

## ขั้นตอนที่ 1: การสร้างเอกสารและตัวสร้างเอกสาร

ขั้นแรก สร้างเอกสารใหม่และตัวสร้างเอกสารที่เกี่ยวข้อง:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: การสร้างและปรับแต่งรายการแรก

ถัดไป สร้างรายการตามเทมเพลตที่มีอยู่ จากนั้นปรับระดับของเทมเพลต:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## ขั้นตอนที่ 3: การเพิ่มรายการลงในรายการแรก

ใช้ตัวสร้างเอกสารเพื่อเพิ่มรายการลงในรายการแรกและลบหมายเลขรายการ:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## ขั้นตอนที่ 4: การสร้างและปรับแต่งรายการที่สอง

หากต้องการใช้รายการแรกซ้ำโดยการรีเซ็ตหมายเลข ให้สร้างสำเนาของเค้าโครงรายการเดิม:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

คุณยังสามารถเปลี่ยนแปลงเพิ่มเติมในรายการที่สองได้หากจำเป็น

## ขั้นตอนที่ 5: การเพิ่มรายการลงในรายการที่สอง

ใช้ตัวสร้างเอกสารอีกครั้งเพื่อเพิ่มรายการลงในรายการที่สองและลบหมายเลขรายการ:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## ขั้นตอนที่ 6: บันทึกเอกสารที่แก้ไข

สุดท้าย ให้บันทึกเอกสารที่แก้ไข:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

ดังนั้น ! คุณได้รีเซ็ตหมายเลขรายการในเอกสาร Word เรียบร้อยแล้วโดยใช้ Aspose.Words for .NET

### ตัวอย่างซอร์สโค้ดสำหรับการรีเซ็ตหมายเลขรายการ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// สร้างรายการตามเทมเพลต
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// หากต้องการนำรายการแรกมาใช้ซ้ำ เราจำเป็นต้องเริ่มการกำหนดหมายเลขใหม่โดยสร้างสำเนาของการจัดรูปแบบรายการดั้งเดิม
List list2 = doc.Lists.AddCopy(list1);

// เราสามารถแก้ไขรายการใหม่ได้ทุกทางรวมถึงการตั้งหมายเลขเริ่มต้นใหม่
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### คำถามที่พบบ่อย

#### ถาม: ฉันจะรีสตาร์ทการกำหนดหมายเลขของรายการใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการรีสตาร์ทการกำหนดหมายเลขของรายการใน Aspose.Words คุณสามารถใช้`ListRestartAtNumber` วิธีการของ`List` ระดับ. วิธีการนี้จะช่วยให้คุณสามารถตั้งค่าการโทรใหม่ซึ่งควรเริ่มรายการใหม่ ตัวอย่างเช่นคุณสามารถใช้`list.ListRestartAtNumber(1)` เพื่อเริ่มนับเลขใหม่จาก 1

#### ถาม: เป็นไปได้ไหมที่จะปรับแต่งคำนำหน้าและส่วนต่อท้ายของการกำหนดหมายเลขรายการที่รีสตาร์ทใน Aspose.Words

 ตอบ: ได้ คุณสามารถปรับแต่งคำนำหน้าและส่วนต่อท้ายของการกำหนดหมายเลขรายการที่รีสตาร์ทใน Aspose.Words ได้ ที่`ListLevel` คลาสเสนอคุณสมบัติเช่น`ListLevel.NumberPrefix`และ`ListLevel.NumberSuffix`ซึ่งช่วยให้คุณสามารถระบุคำนำหน้าและคำต่อท้ายสำหรับแต่ละระดับในรายการได้ คุณสามารถใช้คุณสมบัติเหล่านี้เพื่อปรับแต่งคำนำหน้าและคำต่อท้ายได้ตามต้องการ

#### ถาม: ฉันจะระบุค่าลำดับเลขเฉพาะที่ควรรีสตาร์ทรายการได้อย่างไร

 ตอบ: หากต้องการระบุค่าตัวเลขเฉพาะที่ควรรีสตาร์ทรายการ คุณสามารถใช้`ListRestartAtNumber` วิธีการส่งผ่านค่าที่ต้องการเป็นอาร์กิวเมนต์ ตัวอย่างเช่น หากต้องการเริ่มการนับเลขใหม่จาก 5 คุณสามารถใช้`list.ListRestartAtNumber(5)`.

#### ถาม: เป็นไปได้ไหมที่จะรีสตาร์ทการกำหนดหมายเลขรายการหลายระดับใน Aspose.Words

 ตอบ: ใช่ Aspose.Words รองรับการรีสตาร์ทการกำหนดหมายเลขของรายการหลายระดับ คุณสามารถสมัคร`ListRestartAtNumber` วิธีการในแต่ละระดับรายการเพื่อเริ่มการนับเลขใหม่ทีละรายการ ตัวอย่างเช่นคุณสามารถใช้`list.Levels[0].ListRestartAtNumber(1)` เพื่อรีสตาร์ทระดับรายการแรกจาก 1 และ`list.Levels[1].ListRestartAtNumber(1)` เพื่อรีสตาร์ทรายการระดับที่สองโดยเริ่มจาก 1 เป็นต้น




---
title: เริ่มรายการใหม่ในแต่ละส่วน
linktitle: เริ่มรายการใหม่ในแต่ละส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีรีเซ็ตรายการลำดับเลขไปยังแต่ละส่วนในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/working-with-list/restart-list-at-each-section/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแสดงวิธีรีเซ็ตรายการลำดับเลขให้กับแต่ละส่วนในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะอธิบายซอร์สโค้ด C# ที่ให้มา และแสดงวิธีนำไปใช้ในโครงการของคุณเอง

 ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่า Aspose.Words สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากคุณยังไม่ได้ดาวน์โหลดและติดตั้งไลบรารีจาก[Aspose.Releases]https://releases.aspose.com/words/net/

## ขั้นตอนที่ 1: การสร้างเอกสารและรายการ

ขั้นแรก สร้างเอกสารใหม่และเพิ่มรายการลำดับเลขเริ่มต้น:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## ขั้นตอนที่ 2: การเพิ่มรายการลงในรายการ

 จากนั้นใช้ก`DocumentBuilder` เพื่อเพิ่มรายการลงในรายการ คุณสามารถใช้การวนซ้ำเพื่อเพิ่มหลายรายการลงในรายการ:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

ในตัวอย่างนี้ เรากำลังแทรกตัวแบ่งส่วนหลังรายการที่ 15 เพื่อแสดงการเรียงลำดับเลขใหม่

## ขั้นตอนที่ 3: บันทึกเอกสารที่แก้ไข

สุดท้าย ให้บันทึกเอกสารที่แก้ไข:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

ดังนั้น! คุณได้รีเซ็ตรายการลำดับเลขไปยังแต่ละส่วนในเอกสาร Word เรียบร้อยแล้วโดยใช้ Aspose.Words for .NET

### ตัวอย่างซอร์สโค้ดสำหรับการรีเซ็ตรายการในแต่ละส่วน

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

คุณสามารถใช้โค้ดนี้ในโครงการของคุณเองและแก้ไขให้เหมาะกับความต้องการเฉพาะของคุณได้

### คำถามที่พบบ่อย

#### ถาม: ฉันจะเริ่มรายการใหม่ในทุกส่วนใน Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการรีสตาร์ทรายการในทุกส่วนใน Aspose คุณต้องสร้างอินสแตนซ์ของ`List`คลาสและกำหนดรายการลำดับเลขให้กับคลาสนั้น จากนั้นคุณสามารถใช้`List.IsRestartAtEachSection` คุณสมบัติเพื่อระบุว่าควรรีสตาร์ทลำดับหมายเลขในแต่ละส่วน คุณสามารถเชื่อมโยงรายการนี้กับส่วนหนึ่งหรือหลายส่วนของเอกสารของคุณ เพื่อให้การเริ่มลำดับเลขใหม่อย่างถูกต้องในแต่ละส่วน

#### ถาม: ฉันสามารถปรับแต่งรูปแบบการเรียงลำดับเลขของรายการใน Aspose.Words ได้หรือไม่

 ตอบ: ได้ คุณสามารถปรับแต่งรูปแบบการเรียงลำดับเลขของรายการใน Aspose.Words ได้ ที่`List` class มีคุณสมบัติหลายประการสำหรับสิ่งนี้ เช่น`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`ฯลฯ คุณสามารถใช้คุณสมบัติเหล่านี้เพื่อตั้งค่าประเภทรายการ (ตัวเลข สัญลักษณ์แสดงหัวข้อย่อย ฯลฯ) รูปแบบการกำหนดหมายเลข (เลขอารบิค เลขโรมัน ตัวอักษร ฯลฯ) และตัวเลือกการจัดรูปแบบลำดับเลขอื่นๆ

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มระดับเพิ่มเติมในรายการลำดับเลขใน Aspose.Words

 ตอบ: ได้ คุณสามารถเพิ่มระดับเพิ่มเติมให้กับรายการลำดับเลขใน Aspose.Words ได้ ที่`ListLevel`class ช่วยให้คุณสามารถตั้งค่าคุณสมบัติการจัดรูปแบบสำหรับแต่ละระดับของรายการได้ คุณสามารถตั้งค่าตัวเลือกต่างๆ เช่น คำนำหน้า ส่วนต่อท้าย การจัดตำแหน่ง การเยื้อง ฯลฯ ซึ่งจะทำให้คุณสามารถสร้างรายการที่มีลำดับชั้นได้หลายระดับ
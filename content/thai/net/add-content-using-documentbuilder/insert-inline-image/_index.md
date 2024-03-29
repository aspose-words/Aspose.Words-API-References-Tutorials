---
title: แทรกรูปภาพอินไลน์ในเอกสาร Word
linktitle: แทรกรูปภาพอินไลน์ในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกรูปภาพอินไลน์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/add-content-using-documentbuilder/insert-inline-image/
---
ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีแทรกรูปภาพในบรรทัดลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เราจะแนะนำคุณตลอดกระบวนการและจัดเตรียมข้อมูลโค้ด C# ที่จำเป็นให้กับคุณ เมื่อสิ้นสุดคู่มือนี้ คุณจะสามารถเพิ่มรูปภาพลงในข้อความในเอกสารของคุณได้โดยตรง

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้งไลบรารี Aspose.Words สำหรับ .NET บนระบบของคุณ

## ขั้นตอนที่ 1: สร้างเอกสารใหม่และ DocumentBuilder
ในการเริ่มต้น ให้สร้างเอกสารใหม่โดยใช้คลาส Document และเตรียมใช้งานอ็อบเจ็กต์ DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ขั้นตอนที่ 2: แทรกรูปภาพอินไลน์
จากนั้น ใช้เมธอด InsertImage ของคลาส DocumentBuilder เพื่อแทรกรูปภาพแบบอินไลน์ลงในเอกสาร ระบุเส้นทางไฟล์รูปภาพเป็นพารามิเตอร์:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## ขั้นตอนที่ 3: บันทึกเอกสาร
หลังจากแทรกรูปภาพอินไลน์แล้ว ให้บันทึกเอกสารลงในไฟล์โดยใช้วิธีบันทึกของคลาสเอกสาร:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับการแทรกรูปภาพอินไลน์โดยใช้ Aspose.Words สำหรับ .NET
นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับการแทรกรูปภาพอินไลน์โดยใช้ Aspose.Words สำหรับ .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีแทรกรูปภาพอินไลน์ลงในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ซอร์สโค้ดที่ให้มา คุณสามารถเพิ่มรูปภาพภายในข้อความในเอกสารของคุณได้อย่างราบรื่น

รูปภาพอินไลน์มีประโยชน์สำหรับสถานการณ์ต่างๆ เช่น การเพิ่มภาพประกอบ โลโก้ หรือองค์ประกอบภาพอื่นๆ ลงในโฟลว์ของเอกสารโดยตรง

### คำถามที่พบบ่อยสำหรับการแทรกรูปภาพอินไลน์ในเอกสาร word

#### ถาม: ฉันสามารถปรับขนาดรูปภาพอินไลน์ภายในเอกสาร Word ได้หรือไม่

ตอบ: ได้ คุณสามารถปรับขนาดรูปภาพอินไลน์ได้โดยใช้ Aspose.Words สำหรับ .NET หลังจากแทรกรูปภาพ คุณสามารถปรับขนาดได้โดยการปรับคุณสมบัติความกว้างและความสูงของวัตถุรูปร่างที่แสดงถึงรูปภาพ

#### ถาม: เป็นไปได้ไหมที่จะเพิ่มข้อความแสดงแทนลงในรูปภาพในบรรทัดเพื่อวัตถุประสงค์ในการเข้าถึง

ตอบ: ได้ คุณสามารถเพิ่มข้อความแสดงแทนลงในรูปภาพในบรรทัดเพื่อปรับปรุงการเข้าถึงได้ Aspose.Words สำหรับ .NET รองรับการเพิ่มข้อความแสดงแทนให้กับรูปภาพ ช่วยให้โปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่นๆ สามารถอธิบายเนื้อหารูปภาพให้กับผู้ใช้ที่มีความบกพร่องทางการมองเห็นได้

#### ถาม: ฉันสามารถใช้การจัดรูปแบบหรือสไตล์กับรูปภาพในบรรทัดได้หรือไม่

ตอบ: แน่นอน! Aspose.Words สำหรับ .NET มีตัวเลือกการจัดรูปแบบที่หลากหลายสำหรับรูปภาพในบรรทัด คุณสามารถใช้สไตล์ เส้นขอบ เอฟเฟกต์ และคุณลักษณะการจัดรูปแบบอื่นๆ กับรูปภาพเพื่อให้ตรงกับการออกแบบภาพของเอกสารของคุณได้

#### ถาม: Aspose.Words สำหรับ .NET รองรับการแทรกรูปภาพจากสตรีมหรืออาร์เรย์ไบต์หรือไม่

ตอบ: ได้ คุณสามารถแทรกรูปภาพอินไลน์จากสตรีมหรืออาร์เรย์ไบต์ได้โดยใช้ Aspose.Words สำหรับ .NET สิ่งนี้ช่วยให้คุณทำงานกับรูปภาพที่โหลดจากแหล่งภายนอกหรือรูปภาพที่สร้างขึ้นแบบไดนามิก

#### ถาม: ฉันสามารถแทรกรูปภาพในตำแหน่งเฉพาะภายในเนื้อหาข้อความได้หรือไม่

ตอบ: ใช่ คลาส DocumentBuilder ใน Aspose.Words สำหรับ .NET ให้การควบคุมตำแหน่งการแทรกรูปภาพในบรรทัดที่แม่นยำ คุณสามารถระบุตำแหน่งที่แน่นอนภายในข้อความที่ควรแทรกรูปภาพได้
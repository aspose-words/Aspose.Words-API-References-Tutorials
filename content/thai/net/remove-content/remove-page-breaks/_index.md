---
title: ลบตัวแบ่งหน้าในเอกสาร Word
linktitle: ลบตัวแบ่งหน้า
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีลบตัวแบ่งหน้าในเอกสาร Word โดยใช้ Aspose.Words Library สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อการจัดวางที่ราบรื่น
type: docs
weight: 10
url: /th/net/remove-content/remove-page-breaks/
---
ในบทช่วยสอนนี้ เราจะสำรวจวิธีลบตัวแบ่งหน้าในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET ตัวแบ่งหน้าบางครั้งอาจรบกวนการจัดรูปแบบและเค้าโครงของเอกสาร และอาจจำเป็นต้องลบออกโดยทางโปรแกรม เราจะให้คำแนะนำทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจกระบวนการและนำไปใช้ในโปรเจ็กต์ C# ของคุณเอง

## ความต้องการ

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Aspose.Words สำหรับไลบรารี .NET แล้ว
- Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ ที่ตั้งค่าไว้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ได้รับการอ้างอิงอย่างถูกต้องในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: การโหลดเอกสาร

หากต้องการลบตัวแบ่งหน้าออกจากเอกสาร เราต้องโหลดเอกสารลงในหน่วยความจำก่อน รหัสต่อไปนี้สาธิตวิธีการโหลดเอกสารจากไดเรกทอรีเฉพาะ:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "your-document.docx");
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางจริงไปยังเอกสารของคุณ

## ขั้นตอนที่ 3: การลบตัวแบ่งหน้า

เมื่อโหลดเอกสารแล้ว เราก็สามารถเริ่มลบตัวแบ่งหน้าได้ ข้อมูลโค้ดด้านล่างสาธิตวิธีการวนซ้ำทุกย่อหน้าในเอกสาร ตรวจสอบตัวแบ่งหน้า และลบออก:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
     // หากย่อหน้ามีตัวแบ่งหน้ามาก่อน ให้ล้างออก
     if (para.ParagraphFormat.PageBreakBefore)
         para.ParagraphFormat.PageBreakBefore = false;

     // ตรวจสอบการทำงานทั้งหมดในย่อหน้าเพื่อดูตัวแบ่งหน้าและลบออก
     foreach(Run run in para.Runs)
     {
         if (run.Text.Contains(ControlChar.PageBreak))
             run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
     }
}
```

ข้อมูลโค้ดด้านบนจะวนซ้ำทุกย่อหน้าในเอกสารและตรวจสอบว่าแต่ละย่อหน้ามีตัวแบ่งหน้าอยู่ก่อนหน้าหรือไม่ หากตรวจพบตัวแบ่งหน้า มันจะถูกล้าง จากนั้นจะตรวจสอบแต่ละการทำงานภายในย่อหน้าเพื่อหาตัวแบ่งหน้าและลบออก

## ขั้นตอนที่ 4: บันทึกเอกสารที่แก้ไข

หลังจากลบตัวแบ่งหน้าแล้ว เราจำเป็นต้องบันทึกเอกสารที่แก้ไข รหัสต่อไปนี้สาธิตวิธีการบันทึกเอกสารที่ปรับเปลี่ยนไปยังตำแหน่งเฉพาะ:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 แทนที่`"modified-document.docx"`ด้วยชื่อที่ต้องการสำหรับเอกสารที่คุณแก้ไข

### ตัวอย่างซอร์สโค้ดสำหรับการลบตัวแบ่งหน้าโดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// โหลดเอกสาร
Document doc = new Document(dataDir + "your-document.docx");

NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
	// หากย่อหน้ามีตัวแบ่งหน้าก่อนชุด ให้ล้างออก
	if (para.ParagraphFormat.PageBreakBefore)
		para.ParagraphFormat.PageBreakBefore = false;

	// ตรวจสอบการทำงานทั้งหมดในย่อหน้าเพื่อดูตัวแบ่งหน้าและลบออก
	foreach (Run run in para.Runs)
	{
		if (run.Text.Contains(ControlChar.PageBreak))
			run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
	}
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);        

```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีลบตัวแบ่งหน้าออกจากเอกสารโดยใช้ไลบรารี Aspose.Words สำหรับ .NET เมื่อทำตามคำแนะนำทีละขั้นตอน คุณจะสามารถใช้ฟังก์ชันนี้ในโปรเจ็กต์ C# ของคุณเองได้แล้ว การลบตัวแบ่งหน้าสามารถช่วยให้คุณรักษาเค้าโครงและการจัดรูปแบบที่สอดคล้องกันในเอกสารของคุณได้

### คำถามที่พบบ่อย

#### ถาม: เหตุใดฉันจึงควรใช้ Aspose.Words เพื่อลบตัวแบ่งหน้าในเอกสาร Word

ตอบ: Aspose.Words เป็นไลบรารีคลาสที่ทรงพลังและอเนกประสงค์สำหรับจัดการเอกสาร Word ในแอปพลิเคชัน .NET ด้วยการใช้ Aspose.Words คุณจะได้รับโซลูชันที่มีประสิทธิภาพและง่ายดายในการลบตัวแบ่งหน้าออกจากเอกสารของคุณ ซึ่งช่วยให้คุณปรับแต่งเค้าโครงของเอกสารของคุณ กำจัดตัวแบ่งหน้าที่ไม่ต้องการ และรักษาการนำเสนอที่สอดคล้องกัน

#### ถาม: ฉันจะอัปโหลดเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการลบตัวแบ่งหน้าในเอกสาร Word คุณต้องโหลดเอกสารลงในหน่วยความจำก่อนโดยใช้วิธี Load() ของ Aspose.Words นี่คือโค้ดตัวอย่างในการโหลดเอกสารจากไดเร็กทอรีเฉพาะ:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "your-document.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` พร้อมเส้นทางจริงไปยังเอกสารของคุณ

#### ถาม: วิธีลบตัวแบ่งหน้าในเอกสารโดยใช้ Aspose.Words

ตอบ: เมื่อโหลดเอกสารแล้ว คุณสามารถเริ่มลบตัวแบ่งหน้าได้ ใช้การวนซ้ำเพื่อวนซ้ำย่อหน้าทั้งหมดในเอกสาร ตรวจสอบว่ามีส่วนแบ่งหน้าหรือไม่ และลบออกหากจำเป็น นี่คือโค้ดตัวอย่าง:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
      // ถ้าย่อหน้ามีตัวแบ่งหน้ามาก่อน ให้เอาออก
      if (para.ParagraphFormat.PageBreakBefore)
          para.ParagraphFormat.PageBreakBefore = false;

      // ตรวจสอบองค์ประกอบ Run ทั้งหมดในย่อหน้าเพื่อหาตัวแบ่งหน้าและลบออก
      foreach(Run run in para.Runs)
      {
          if (run.Text.Contains(ControlChar.PageBreak))
              run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
      }
}
```

โค้ดนี้จะวนซ้ำย่อหน้าทั้งหมดในเอกสาร ตรวจสอบว่ามีส่วนแบ่งหน้านำหน้าหรือไม่ จากนั้นจึงลบออก จากนั้นจะตรวจสอบแต่ละองค์ประกอบ Run ในย่อหน้าเพื่อหาตัวแบ่งหน้าและลบออก

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หลังจากลบตัวแบ่งหน้าแล้ว คุณต้องบันทึกเอกสารที่แก้ไข ใช้เมธอด Save() เพื่อบันทึกเอกสารที่แก้ไขไปยังตำแหน่งเฉพาะ นี่คือโค้ดตัวอย่าง:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 แทนที่`"modified-document.docx"`ด้วยชื่อที่ต้องการสำหรับเอกสารที่คุณแก้ไข
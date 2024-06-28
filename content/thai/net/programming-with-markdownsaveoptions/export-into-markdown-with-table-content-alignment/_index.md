---
title: ส่งออกไปยัง Markdown ด้วยการจัดตำแหน่งเนื้อหาตาราง
linktitle: ส่งออกไปยัง Markdown ด้วยการจัดตำแหน่งเนื้อหาตาราง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีส่งออกเนื้อหาตารางที่มีการจัดแนวต่างๆ ไปยังไฟล์ Markdown โดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
ต่อไปนี้เป็นคำแนะนำทีละขั้นตอนเพื่ออธิบายซอร์สโค้ด C# ต่อไปนี้ที่ช่วยส่งออกเนื้อหาไปยังไฟล์ Markdown ด้วยการจัดแนวเนื้อหาตารางโดยใช้ไลบรารี Aspose.Words สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Words ไว้ในโปรเจ็กต์ของคุณก่อนที่จะใช้โค้ดนี้

## ขั้นตอนที่ 1: ตั้งค่าเส้นทางไดเรกทอรีเอกสาร

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

ตรวจสอบให้แน่ใจว่าได้ระบุเส้นทางที่ถูกต้องไปยังไดเร็กทอรีเอกสารของคุณที่จะบันทึกเอกสารที่แก้ไข

## ขั้นตอนที่ 2: สร้างเอกสารและตัวสร้างเอกสาร

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ที่นี่เราสร้างอินสแตนซ์ของ`Document` คลาสและตัวอย่างของ`DocumentBuilder` คลาสซึ่งจะทำให้เราสามารถจัดการเอกสารและเพิ่มองค์ประกอบได้

## ขั้นตอนที่ 3: แทรกเซลล์ลงในตารางโดยมีการจัดแนวย่อหน้าต่างๆ

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

เราใช้ตัวสร้างเอกสารเพื่อแทรกเซลล์ลงในตารางและตั้งค่าการจัดแนวย่อหน้าที่แตกต่างกันสำหรับแต่ละเซลล์

## ขั้นตอนที่ 4: ตั้งค่าตัวเลือกการส่งออก Markdown และบันทึกเอกสารที่แก้ไข

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

เราตั้งค่าตัวเลือกการส่งออก Markdown ด้วยการจัดแนวเนื้อหาตารางที่แตกต่างกัน จากนั้นบันทึกเอกสารที่แก้ไขโดยใช้ตัวเลือกการจัดตำแหน่งแต่ละรายการ

### ตัวอย่างซอร์สโค้ดที่จะส่งออกไปยัง Markdown พร้อมการจัดตำแหน่งเนื้อหาตารางโดยใช้ Aspose.Words สำหรับ .NET

```csharp

            
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// ทำให้ย่อหน้าทั้งหมดภายในตารางถูกจัดแนว
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// การจัดตำแหน่งในกรณีนี้จะนำมาจากย่อหน้าแรกในคอลัมน์ตารางที่เกี่ยวข้อง
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// บันทึกเอกสารที่แก้ไข
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```

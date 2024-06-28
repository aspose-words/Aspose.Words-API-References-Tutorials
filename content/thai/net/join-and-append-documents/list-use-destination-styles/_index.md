---
title: รายการใช้สไตล์ปลายทาง
linktitle: รายการใช้สไตล์ปลายทาง
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีเข้าร่วมและผนวกเอกสาร Word ในขณะที่รักษารูปแบบรายการของเอกสารปลายทางโดยใช้ Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/join-and-append-documents/list-use-destination-styles/
---

บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ฟีเจอร์รายการใช้สไตล์ปลายทางของ Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถเข้าร่วมและต่อท้ายเอกสาร Word ในขณะที่ใช้สไตล์รายการของเอกสารปลายทาง

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. ติดตั้ง Aspose.Words สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose หรือติดตั้งผ่าน NuGet
2. Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ

## ขั้นตอนที่ 1: เริ่มต้นไดเร็กทอรีเอกสาร

 ขั้นแรก คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ แก้ไขค่าของ`dataDir` ตัวแปรไปยังเส้นทางที่เอกสารของคุณอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: โหลดเอกสารต้นทางและปลายทาง

ถัดไป คุณต้องโหลดเอกสารต้นทางและปลายทางโดยใช้ Aspose.Words`Document` ชั้นเรียน อัพเดตชื่อไฟล์ใน`Document` ตัวสร้างตามชื่อเอกสารของคุณ

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## ขั้นตอนที่ 3: ตั้งค่าเอกสารต้นฉบับให้ดำเนินการต่อหลังจากเอกสารปลายทาง

 เพื่อให้แน่ใจว่าเนื้อหาจากเอกสารต้นฉบับดำเนินต่อไปหลังจากสิ้นสุดเอกสารปลายทาง คุณต้องตั้งค่า`SectionStart` คุณสมบัติของส่วนแรกในเอกสารต้นฉบับถึง`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## ขั้นตอนที่ 4: จัดการการจัดรูปแบบรายการ

ในการจัดการการจัดรูปแบบรายการ คุณจะต้องวนซ้ำแต่ละย่อหน้าในเอกสารต้นฉบับและตรวจสอบว่าเป็นรายการหรือไม่ หากเป็นเช่นนั้น คุณจะต้องเปรียบเทียบรหัสรายการกับรายการที่มีอยู่ในเอกสารปลายทาง หากมีรายการที่มี ID เดียวกัน คุณจะสร้างสำเนาของรายการในเอกสารต้นฉบับและอัปเดตรูปแบบรายการของย่อหน้าเพื่อใช้รายการที่คัดลอก

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## ขั้นตอนที่ 5: ผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทาง

 ตอนนี้คุณสามารถผนวกเอกสารต้นฉบับเข้ากับเอกสารปลายทางได้โดยใช้`AppendDocument` วิธีการของ`Document` ชั้นเรียน ที่`ImportFormatMode.UseDestinationStyles` พารามิเตอร์ช่วยให้มั่นใจว่ารูปแบบรายการของเอกสารปลายทางถูกใช้ในระหว่างการดำเนินการผนวก

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## ขั้นตอนที่ 6: บันทึกเอกสารขั้นสุดท้าย

สุดท้าย ให้บันทึกเอกสารที่ผสานโดยเปิดใช้งานคุณลักษณะ List Use Destination Styles โดยใช้`Save` วิธีการของ`Document` ชั้นเรียน

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### ตัวอย่างซอร์สโค้ดสำหรับรายการใช้สไตล์ปลายทางโดยใช้ Aspose.Words สำหรับ .NET 

นี่คือซอร์สโค้ดแบบเต็มสำหรับฟีเจอร์ "List Use Destination Styles" ใน C# โดยใช้ Aspose.Words สำหรับ .NET:


```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// ตั้งค่าเอกสารต้นทางให้ดำเนินการต่อโดยตรงหลังจากสิ้นสุดเอกสารปลายทาง
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// ติดตามรายการที่สร้างขึ้น
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// ตรวจสอบว่าเอกสารปลายทางมีรายการที่มี ID นี้อยู่แล้วหรือไม่ ถ้าเป็นเช่นนั้นก็อาจนี้
			// ทำให้ทั้งสองรายการทำงานพร้อมกัน สร้างสำเนาของรายการในเอกสารต้นฉบับแทน
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// มีรายการคัดลอกใหม่สำหรับ ID นี้แล้ว ดึงรายการที่เก็บไว้
				// และใช้ในย่อหน้าปัจจุบัน
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// เพิ่มสำเนาของรายการนี้ลงในเอกสารและเก็บไว้เพื่อใช้อ้างอิงในภายหลัง
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// ตั้งค่ารายการของย่อหน้านี้ให้เป็นรายการที่คัดลอก
				para.ListFormat.List = currentList;
			}
		}
	}
	// ผนวกเอกสารต้นฉบับต่อท้ายเอกสารปลายทาง
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

แค่นั้นแหละ! คุณได้นำคุณลักษณะ List Use Destination Styles ไปใช้โดยใช้ Aspose.Words for .NET เรียบร้อยแล้ว เอกสารขั้นสุดท้ายจะมีเนื้อหาที่ผสานเข้ากับสไตล์รายการจากเอกสารปลายทาง
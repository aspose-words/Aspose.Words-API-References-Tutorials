---
title: แทรกเอกสารที่แทนที่
linktitle: แทรกเอกสารที่แทนที่
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกเอกสาร Word หนึ่งไปยังอีกเอกสารหนึ่งได้อย่างราบรื่นโดยใช้ Aspose.Words สำหรับ .NET พร้อมคำแนะนำโดยละเอียดทีละขั้นตอนของเรา เหมาะสำหรับนักพัฒนาที่ต้องการปรับปรุงการประมวลผลเอกสาร
type: docs
weight: 10
url: /th/net/clone-and-combine-documents/insert-document-at-replace/
---
## การแนะนำ

สวัสดี ผู้เชี่ยวชาญด้านเอกสาร! เคยพบว่าตัวเองต้องใช้โค้ดมากจนต้องพยายามหาวิธีแทรกเอกสาร Word หนึ่งไปยังอีกเอกสารหนึ่งได้อย่างราบรื่นหรือไม่? อย่ากลัวเลย เพราะวันนี้เรากำลังดำดิ่งสู่โลกของ Aspose.Words สำหรับ .NET เพื่อให้งานนั้นเป็นเรื่องง่าย เราจะอธิบายคำแนะนำโดยละเอียดทีละขั้นตอนเกี่ยวกับวิธีการใช้ไลบรารีที่มีประสิทธิภาพนี้เพื่อแทรกเอกสาร ณ จุดเฉพาะระหว่างการดำเนินการค้นหาและแทนที่ พร้อมที่จะเป็นพ่อมด Aspose.Words แล้วหรือยัง? มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะพูดถึงโค้ด มีบางสิ่งที่คุณต้องมี:

-  Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนเครื่องของคุณแล้ว หากยังไม่มีก็สามารถดาวน์โหลดได้จาก[ที่นี่](https://visualstudio.microsoft.com/).
-  Aspose.Words สำหรับ .NET: คุณจะต้องมีไลบรารี Aspose.Words คุณสามารถรับได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/words/net/).
- ความรู้พื้นฐาน C#: ความเข้าใจพื้นฐานเกี่ยวกับ C# และ .NET จะช่วยให้คุณปฏิบัติตามบทช่วยสอนนี้

เอาล่ะ เพื่อไม่ให้เป็นการรบกวน เรามาทำให้มือของเราสกปรกด้วยโค้ดกันดีกว่า!

## นำเข้าเนมสเปซ

ก่อนอื่น เราต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Words นี่เหมือนกับการรวบรวมเครื่องมือทั้งหมดของคุณก่อนเริ่มโปรเจ็กต์ เพิ่มสิ่งเหล่านี้โดยใช้คำสั่งที่ด้านบนของไฟล์ C# ของคุณ:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

ตอนนี้เรามีข้อกำหนดเบื้องต้นแล้ว เรามาแบ่งกระบวนการออกเป็นขั้นตอนเล็กๆ น้อยๆ กัน แต่ละขั้นตอนมีความสำคัญและจะนำเราเข้าใกล้เป้าหมายมากขึ้น

## ขั้นตอนที่ 1: การตั้งค่าไดเร็กทอรีเอกสาร

ขั้นแรก เราต้องระบุไดเร็กทอรีที่เก็บเอกสารของเรา เหมือนกับการจัดเวทีก่อนการแสดงครั้งใหญ่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 แทนที่`"YOUR DOCUMENT DIRECTORY"` พร้อมเส้นทางไปยังไดเร็กทอรีของคุณ นี่คือที่ที่เอกสารของคุณจะอยู่และหายใจได้

## ขั้นตอนที่ 2: โหลดเอกสารหลัก

ต่อไปเราจะโหลดเอกสารหลักที่เราต้องการแทรกเอกสารอื่นเข้าไป คิดว่านี่เป็นเวทีหลักของเราที่ทุกการกระทำจะเกิดขึ้น

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

รหัสนี้โหลดเอกสารหลักจากไดเร็กทอรีที่ระบุ

## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกการค้นหาและแทนที่

หากต้องการค้นหาตำแหน่งเฉพาะที่เราต้องการแทรกเอกสาร เราใช้ฟังก์ชันการค้นหาและแทนที่ ก็เหมือนกับการใช้แผนที่เพื่อค้นหาจุดที่แน่นอนสำหรับการเพิ่มใหม่ของเรา

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

ที่นี่ เรากำลังกำหนดทิศทางย้อนกลับและระบุตัวจัดการการเรียกกลับแบบกำหนดเองที่เราจะกำหนดต่อไป

## ขั้นตอนที่ 4: ดำเนินการแทนที่

ตอนนี้ เราบอกให้เอกสารหลักของเราค้นหาข้อความตัวยึดตำแหน่งที่เฉพาะเจาะจงและแทนที่ด้วยไม่มีอะไรเลย ขณะเดียวกันก็ใช้การโทรกลับแบบกำหนดเองของเราเพื่อแทรกเอกสารอื่น

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

รหัสนี้ดำเนินการค้นหาและแทนที่ จากนั้นบันทึกเอกสารที่อัปเดต

## ขั้นตอนที่ 5: สร้างตัวจัดการการโทรกลับการจำลองแบบกำหนดเอง

ตัวจัดการการโทรกลับแบบกำหนดเองของเราคือจุดที่ความมหัศจรรย์เกิดขึ้น ตัวจัดการนี้จะกำหนดวิธีการแทรกเอกสารระหว่างการดำเนินการค้นหาและแทนที่

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // แทรกเอกสารหลังย่อหน้าที่มีข้อความที่ตรงกัน
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // ลบย่อหน้าที่มีข้อความตรงกัน
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

ที่นี่ เราโหลดเอกสารที่จะแทรก จากนั้นเรียกใช้เมธอดตัวช่วยเพื่อดำเนินการแทรก

## ขั้นตอนที่ 6: กำหนดวิธีการแทรกเอกสาร

ชิ้นส่วนสุดท้ายของปริศนาของเราคือวิธีการแทรกเอกสารในตำแหน่งที่ระบุ

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// วนซ้ำโหนดระดับบล็อกทั้งหมดในส่วนเนื้อหาของส่วน
		// จากนั้นโคลนและแทรกทุกโหนดที่ไม่ใช่ย่อหน้าว่างสุดท้ายของส่วน
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

วิธีนี้จะดูแลการนำเข้าโหนดจากเอกสารที่จะแทรกและวางไว้ที่จุดที่ถูกต้องในเอกสารหลัก

## บทสรุป

และคุณก็ได้แล้ว! คำแนะนำที่ครอบคลุมเกี่ยวกับการแทรกเอกสารหนึ่งไปยังอีกเอกสารหนึ่งโดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถทำให้งานการประกอบและการจัดการเอกสารเป็นอัตโนมัติได้อย่างง่ายดาย ไม่ว่าคุณจะสร้างระบบการจัดการเอกสารหรือเพียงต้องการปรับปรุงขั้นตอนการประมวลผลเอกสารของคุณ Aspose.Words คือผู้ช่วยที่ไว้วางใจได้ของคุณ

## คำถามที่พบบ่อย

### Aspose.Words สำหรับ .NET คืออะไร
Aspose.Words for .NET เป็นไลบรารีที่มีประสิทธิภาพสำหรับการจัดการเอกสาร Word โดยทางโปรแกรม ช่วยให้คุณสร้าง แก้ไข แปลง และประมวลผลเอกสาร Word ได้อย่างง่ายดาย

### ฉันสามารถแทรกเอกสารหลายฉบับพร้อมกันได้หรือไม่
ได้ คุณสามารถแก้ไขตัวจัดการการเรียกกลับเพื่อจัดการกับการแทรกหลายรายการได้โดยการวนซ้ำชุดเอกสาร

### มีการทดลองใช้ฟรีหรือไม่?
 อย่างแน่นอน! คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### ฉันจะรับการสนับสนุนสำหรับ Aspose.Words ได้อย่างไร
คุณสามารถรับการสนับสนุนได้โดยไปที่[ฟอรั่ม Aspose.Words](https://forum.aspose.com/c/words/8).

### ฉันสามารถเก็บรูปแบบของเอกสารที่แทรกไว้ได้หรือไม่
 ใช่`NodeImporter`คลาสช่วยให้คุณระบุวิธีจัดการการจัดรูปแบบเมื่อนำเข้าโหนดจากเอกสารหนึ่งไปยังอีกเอกสารหนึ่ง
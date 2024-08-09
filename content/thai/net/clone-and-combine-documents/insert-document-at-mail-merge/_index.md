---
title: แทรกเอกสารที่จดหมายเวียน
linktitle: แทรกเอกสารที่จดหมายเวียน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแทรกเอกสารในช่องจดหมายเวียนโดยใช้ Aspose.Words สำหรับ .NET ในบทช่วยสอนที่ครอบคลุมทีละขั้นตอนนี้
type: docs
weight: 10
url: /th/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## การแนะนำ

ยินดีต้อนรับสู่โลกแห่งระบบอัตโนมัติของเอกสารด้วย Aspose.Words สำหรับ .NET! คุณเคยสงสัยบ้างไหมว่าจะแทรกเอกสารแบบไดนามิกลงในเขตข้อมูลเฉพาะภายในเอกสารหลักระหว่างการดำเนินการจดหมายเวียนได้อย่างไร คุณอยู่ในสถานที่ที่เหมาะสม บทช่วยสอนนี้จะแนะนำคุณทีละขั้นตอนตลอดกระบวนการแทรกเอกสารที่เขตข้อมูลจดหมายเวียนโดยใช้ Aspose.Words สำหรับ .NET มันเหมือนกับการต่อปริศนาที่ชิ้นส่วนแต่ละชิ้นตกลงเข้าที่พอดี เอาล่ะ มาดำดิ่งกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1.  Aspose.Words สำหรับ .NET: คุณทำได้[ดาวน์โหลดเวอร์ชันล่าสุดได้ที่นี่](https://releases.aspose.com/words/net/) - หากคุณต้องการซื้อใบอนุญาต คุณสามารถทำได้[ที่นี่](https://purchase.aspose.com/buy) - หรือคุณสามารถรับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) หรือลองใช้กับ[ทดลองใช้ฟรี](https://releases.aspose.com/).
2. สภาพแวดล้อมการพัฒนา: Visual Studio หรือ C# IDE อื่น ๆ
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับการเขียนโปรแกรม C# จะทำให้บทช่วยสอนนี้เป็นเรื่องง่าย

## นำเข้าเนมสเปซ

ก่อนอื่น คุณจะต้องนำเข้าเนมสเปซที่จำเป็น สิ่งเหล่านี้เปรียบเสมือนองค์ประกอบสำคัญของโครงการของคุณ

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

เรามาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้ แต่ละขั้นตอนจะต่อยอดจากขั้นตอนก่อนหน้า ซึ่งจะนำคุณไปสู่โซลูชันที่สมบูรณ์

## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีของคุณ

ก่อนที่คุณจะเริ่มแทรกเอกสารได้ คุณต้องกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณก่อน นี่คือที่จัดเก็บเอกสารของคุณ

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ขั้นตอนที่ 2: กำลังโหลดเอกสารหลัก

ต่อไป คุณจะโหลดเอกสารหลัก เอกสารนี้ประกอบด้วยเขตข้อมูลผสานที่จะแทรกเอกสารอื่น ๆ

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## ขั้นตอนที่ 3: การตั้งค่าการโทรกลับการรวมฟิลด์

ในการจัดการกระบวนการรวม คุณจะต้องตั้งค่าฟังก์ชันโทรกลับ ฟังก์ชั่นนี้จะรับผิดชอบในการแทรกเอกสารในช่องผสานที่ระบุ

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## ขั้นตอนที่ 4: การดำเนินการจดหมายเวียน

ตอนนี้ได้เวลาดำเนินการจดหมายเวียนแล้ว นี่คือจุดที่ความมหัศจรรย์เกิดขึ้น คุณจะต้องระบุฟิลด์ผสานและเอกสารที่ควรแทรกลงในฟิลด์นี้

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## ขั้นตอนที่ 5: บันทึกเอกสาร

หลังจากจดหมายเวียนเสร็จสมบูรณ์ คุณจะบันทึกเอกสารที่ปรับเปลี่ยน เอกสารใหม่นี้จะมีเนื้อหาที่แทรกอยู่ในตำแหน่งที่คุณต้องการ

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## ขั้นตอนที่ 6: การสร้างตัวจัดการการโทรกลับ

ตัวจัดการการเรียกกลับเป็นคลาสที่ทำให้การประมวลผลพิเศษสำหรับเขตข้อมูลผสาน จะโหลดเอกสารที่ระบุในค่าฟิลด์และแทรกลงในฟิลด์ผสานปัจจุบัน

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## ขั้นตอนที่ 7: การแทรกเอกสาร

วิธีการนี้จะแทรกเอกสารที่ระบุลงในย่อหน้าปัจจุบันหรือเซลล์ตาราง

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

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

## บทสรุป

และคุณก็ได้แล้ว! คุณได้แทรกเอกสารลงในเขตข้อมูลเฉพาะระหว่างการดำเนินการจดหมายเวียนโดยใช้ Aspose.Words สำหรับ .NET เรียบร้อยแล้ว ฟีเจอร์อันทรงพลังนี้สามารถช่วยคุณประหยัดเวลาและความพยายามได้มาก โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับเอกสารปริมาณมาก เปรียบเสมือนการมีผู้ช่วยส่วนตัวที่คอยดูแลทุกงานหนักให้กับคุณ ดังนั้นไปข้างหน้าและลองดู ขอให้มีความสุขในการเขียนโค้ด!

## คำถามที่พบบ่อย

### ฉันสามารถแทรกเอกสารหลายฉบับในช่องผสานที่แตกต่างกันได้หรือไม่
ใช่คุณสามารถ เพียงระบุฟิลด์ผสานที่เหมาะสมและเส้นทางเอกสารที่เกี่ยวข้องใน`MailMerge.Execute` วิธี.

### เป็นไปได้ไหมที่จะจัดรูปแบบเอกสารที่แทรกแตกต่างจากเอกสารหลัก?
 อย่างแน่นอน! คุณสามารถใช้`ImportFormatMode` พารามิเตอร์ใน`NodeImporter` เพื่อควบคุมการจัดรูปแบบ

### จะเกิดอะไรขึ้นถ้าชื่อเขตข้อมูลผสานเป็นแบบไดนามิก
คุณสามารถจัดการชื่อเขตข้อมูลผสานแบบไดนามิกโดยส่งเป็นพารามิเตอร์ไปยังตัวจัดการการเรียกกลับ

### ฉันสามารถใช้วิธีนี้กับไฟล์รูปแบบอื่นได้หรือไม่?
ใช่ Aspose.Words รองรับไฟล์หลากหลายรูปแบบ รวมถึง DOCX, PDF และอื่นๆ

### ฉันจะจัดการกับข้อผิดพลาดระหว่างขั้นตอนการแทรกเอกสารได้อย่างไร
ใช้การจัดการข้อผิดพลาดในตัวจัดการการเรียกกลับของคุณเพื่อจัดการข้อยกเว้นใด ๆ ที่อาจเกิดขึ้น
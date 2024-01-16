---
title: ลบสารบัญในเอกสาร Word
linktitle: ลบสารบัญในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีลบสารบัญในเอกสาร Word โดยใช้ Aspose.Words for .NET
type: docs
weight: 10
url: /th/net/remove-content/remove-table-of-contents/
---
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการลบสารบัญในเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET บางครั้งสารบัญอาจมีการซ้ำซ้อนหรือไม่จำเป็น และโค้ดนี้จะช่วยให้คุณลบสารบัญได้อย่างมีประสิทธิภาพ เราจะให้คำแนะนำทีละขั้นตอนเพื่อช่วยให้คุณเข้าใจและนำโค้ดไปใช้ในโครงการ .NET ของคุณเอง

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีรายการต่อไปนี้:
- ความรู้การทำงานของภาษาการเขียนโปรแกรม C #
- ไลบรารี Aspose.Words สำหรับ .NET ที่ติดตั้งในโครงการของคุณ
- เอกสาร Word ที่มีสารบัญที่คุณต้องการลบ

## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
 ขั้นแรก คุณต้องตั้งค่าเส้นทางไดเรกทอรีไปยังตำแหน่งของเอกสาร Word ของคุณ แทนที่`"YOUR DOCUMENT DIRECTORY"` ในโค้ดด้วยเส้นทางที่เหมาะสม

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ขั้นตอนที่ 2: อัปโหลดเอกสาร
 ต่อไปเราจะโหลดเอกสาร Word ลงในอินสแตนซ์ของ`Document` ชั้นเรียนโดยใช้`Load` วิธี.

```csharp
// โหลดเอกสาร
Document doc = new Document(dataDir + "your-document.docx");
```

## ขั้นตอนที่ 3: ลบสารบัญ
 หากต้องการลบสารบัญ เราจะวนซ้ำประเภท TOC (สารบัญ)`FieldStart` โหนดในเอกสาร เราจะจัดเก็บโหนดเหล่านี้เพื่อให้เราสามารถเข้าถึงได้อย่างรวดเร็วและสร้างรายการโหนดที่จะลบ

```csharp
// จัดเก็บโหนด FieldStart ของฟิลด์ TOC ในเอกสารเพื่อการเข้าถึงที่รวดเร็ว
List<FieldStart> fieldStarts = new List<FieldStart>();
// นี่คือรายการสำหรับจัดเก็บโหนดที่พบใน TOC ที่ระบุ พวกเขาจะถูกลบเมื่อสิ้นสุดวิธีนี้
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// ตรวจสอบว่ามีดัชนี TOC ที่ระบุอยู่หรือไม่
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // จะปลอดภัยกว่าถ้าจัดเก็บโหนดเหล่านี้และลบออกทั้งหมดในตอนท้าย
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // เมื่อเราเจอโหนด FieldEnd ประเภท FieldTOC
     //เรารู้ว่าเรามาถึงจุดสิ้นสุดของ TOC ปัจจุบันแล้ว และเราหยุดอยู่แค่นี้
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### ตัวอย่างซอร์สโค้ดสำหรับการลบสารบัญโดยใช้ Aspose.Words สำหรับ .NET 
```csharp

// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// โหลดเอกสาร
Document doc = new Document(dataDir + "your-document.docx");

// จัดเก็บโหนด FieldStart ของฟิลด์ TOC ในเอกสารเพื่อการเข้าถึงที่รวดเร็ว
List<FieldStart> fieldStarts = new List<FieldStart>();
// นี่คือรายการสำหรับจัดเก็บโหนดที่พบใน TOC ที่ระบุ พวกเขาจะถูกลบออกเมื่อสิ้นสุดวิธีนี้
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// ตรวจสอบให้แน่ใจว่ามี TOC ที่ระบุโดยดัชนีที่ส่งผ่านอยู่
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// จะปลอดภัยกว่าถ้าจัดเก็บโหนดเหล่านี้และลบออกทั้งหมดพร้อมกันในภายหลัง
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// เมื่อเราพบโหนด FieldEnd ประเภท FieldTOC แล้ว
	// เรารู้ว่าเรามาถึงจุดสิ้นสุดของ TOC ปัจจุบันและหยุดอยู่แค่นี้
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้นำเสนอคำแนะนำทีละขั้นตอนในการลบสารบัญออกจากเอกสาร Word โดยใช้ไลบรารี Aspose.Words สำหรับ .NET ด้วยการทำตามโค้ดและคำแนะนำที่ให้มา คุณสามารถกำจัดสารบัญและปรับปรุงเลย์เอาต์ของเอกสารของคุณได้อย่างง่ายดาย อย่าลืมปรับเส้นทางไดเรกทอรีและชื่อไฟล์ให้เหมาะกับความต้องการเฉพาะของคุณ

### คำถามที่พบบ่อย

#### ถาม: เหตุใดฉันจึงควรใช้ Aspose.Words เพื่อลบสารบัญในเอกสาร Word

ตอบ: Aspose.Words เป็นไลบรารีคลาสที่ทรงพลังและอเนกประสงค์สำหรับจัดการเอกสาร Word ในแอปพลิเคชัน .NET ด้วยการใช้ Aspose.Words คุณสามารถลบสารบัญออกจากเอกสารของคุณได้อย่างมีประสิทธิภาพ ซึ่งจะมีประโยชน์หากสารบัญซ้ำซ้อนหรือไม่จำเป็น วิธีนี้ช่วยให้คุณปรับแต่งเนื้อหาของเอกสารและปรับปรุงการนำเสนอโดยรวมได้

#### ถาม: ฉันจะอัปโหลดเอกสารใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หากต้องการลบสารบัญในเอกสาร Word คุณต้องโหลดเอกสารลงในหน่วยความจำก่อนโดยใช้เมธอด Load() ของ Aspose.Words นี่คือโค้ดตัวอย่างในการโหลดเอกสารจากไดเร็กทอรีเฉพาะ:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "your-document.docx");
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` พร้อมเส้นทางจริงไปยังเอกสารของคุณ

#### ถาม: ฉันจะลบสารบัญในเอกสารโดยใช้ Aspose.Words ได้อย่างไร

 ตอบ: หากต้องการลบ TOC คุณต้องทำซ้ำผ่าน`FieldStart` พิมพ์โหนดของ TOC ในเอกสาร คุณสามารถจัดเก็บโหนดเหล่านี้เพื่อการเข้าถึงที่รวดเร็วและสร้างรายการโหนดที่จะลบได้ นี่คือโค้ดตัวอย่าง:

```csharp
// จัดเก็บโหนด FieldStart ของฟิลด์ TOC ในเอกสารเพื่อการเข้าถึงที่รวดเร็ว
List<FieldStart> fieldStarts = new List<FieldStart>();
//นี่คือรายการสำหรับจัดเก็บโหนดที่พบใน TOC ที่ระบุ พวกเขาจะถูกลบเมื่อสิ้นสุดวิธีนี้
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// ตรวจสอบว่ามีดัชนีสารบัญที่ระบุอยู่หรือไม่
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// จะปลอดภัยกว่าถ้าจัดเก็บโหนดเหล่านี้และลบออกทั้งหมดในตอนท้าย
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// เมื่อเราเจอโหนด FieldEnd ประเภท FieldTOC
//เรารู้ว่าเรามาถึงจุดสิ้นสุดของ TOC ปัจจุบันแล้ว และเราหยุดอยู่แค่นี้
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### ถาม: จะบันทึกเอกสารที่แก้ไขใน Aspose.Words สำหรับ .NET ได้อย่างไร

ตอบ: หลังจากลบสารบัญแล้ว คุณต้องบันทึกเอกสารที่แก้ไขโดยใช้เมธอด Save() ระบุเส้นทางและรูปแบบไฟล์เอาต์พุตที่ต้องการ (เช่น DOCX) สำหรับเอกสารที่แก้ไข นี่คือโค้ดตัวอย่าง:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```
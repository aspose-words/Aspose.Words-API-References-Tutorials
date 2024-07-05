---
title: การหาดัชนี
linktitle: การหาดัชนี
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีค้นหาดัชนีตาราง แถว และเซลล์ในเอกสาร Word ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-tables/finding-index/
---

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีใช้ Aspose.Words สำหรับ .NET เพื่อค้นหาดัชนีของตาราง แถว และเซลล์ในเอกสาร Word เราจะทำตามคำแนะนำทีละขั้นตอนเพื่อทำความเข้าใจโค้ดและใช้งานคุณลักษณะนี้ ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถค้นหาดัชนีขององค์ประกอบอาร์เรย์ในเอกสาร Word ของคุณโดยทางโปรแกรม

## ขั้นตอนที่ 1: การตั้งค่าโครงการ
1. เรียกใช้ Visual Studio และสร้างโครงการ C# ใหม่
2. เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Words สำหรับ .NET

## ขั้นตอนที่ 2: กำลังโหลดเอกสารและเข้าถึงตาราง
ในการเริ่มการประมวลผลคำด้วยตาราง เราจำเป็นต้องโหลดเอกสารที่มีอยู่และเข้าถึงได้ ทำตามขั้นตอนเหล่านี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสารของคุณ
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// โหลดเอกสาร
Document doc = new Document(dataDir + "Tables.docx");

// การเข้าถึงอาร์เรย์
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

อย่าลืมแทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไดเรกทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: ค้นหาตาราง แถว และดัชนีเซลล์
ต่อไป เราจะค้นหาดัชนีตาราง แถว และเซลล์ในอาร์เรย์โดยใช้วิธีการที่ Aspose.Words สำหรับ .NET ให้มา ใช้รหัสต่อไปนี้:

```csharp
// ค้นหาดัชนีตาราง
NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
int tableIndex = allTables.IndexOf(table);
Console.WriteLine("\nTable index is " + tableIndex);

// ค้นหาดัชนีแถว
int rowIndex = table.IndexOf(table.LastRow);
Console.WriteLine("\nLine index is " + rowIndex);

// ค้นหาดัชนีเซลล์
Row row = table. LastRow;
int cellIndex = row.IndexOf(row.Cells[4]);
Console.WriteLine("\nCell index is " + cellIndex);
```

 ในที่นี้เราใช้`GetChildNodes` วิธีการรับตารางทั้งหมดในเอกสาร แล้วเราก็ใช้`IndexOf` เพื่อค้นหาดัชนีของตารางเฉพาะในกลุ่มของตารางทั้งหมด ในทำนองเดียวกันเราใช้`IndexOf` เพื่อค้นหาดัชนีของแถวสุดท้ายในตาราง และ`IndexOf` ภายในแถวเพื่อค้นหาดัชนีของเซลล์ที่ต้องการ

### ตัวอย่างซอร์สโค้ดสำหรับการค้นหาดัชนีโดยใช้ Aspose.Words สำหรับ .NET 

```csharp
	// เส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	NodeCollection allTables = doc.GetChildNodes(NodeType.Table, true);
	int tableIndex = allTables.IndexOf(table);
	Console.WriteLine("\nTable index is " + tableIndex);
	int rowIndex = table.IndexOf(table.LastRow);
	Console.WriteLine("\nRow index is " + rowIndex);
	Row row = table.LastRow;
	int cellIndex = row.IndexOf(row.Cells[4]);
	Console.WriteLine("\nCell index is " + cellIndex);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีค้นหาดัชนีของตาราง แถว และเซลล์ในเอกสาร Word โดยใช้ Aspose.Words สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้และใช้โค้ด C# ที่ให้มา คุณสามารถค้นหาและระบุตำแหน่งที่แน่นอนขององค์ประกอบอาร์เรย์ในเอกสาร Word ของคุณโดยทางโปรแกรมได้ คุณสมบัตินี้ช่วยให้คุณจัดการและโต้ตอบกับองค์ประกอบอาเรย์ได้อย่างแม่นยำเพื่อให้เหมาะกับความต้องการเฉพาะของคุณ
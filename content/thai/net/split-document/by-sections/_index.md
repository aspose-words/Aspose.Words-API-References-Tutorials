---
title: แยกเอกสาร Word ตามส่วน
linktitle: แยกเอกสาร Word ตามส่วน
second_title: Aspose.Words API การประมวลผลเอกสาร
description: เรียนรู้วิธีแบ่งเอกสาร Word ออกเป็นส่วนๆ โดยใช้ Aspose.Words สำหรับ .NET พร้อมตัวอย่างโค้ดที่สมบูรณ์
type: docs
weight: 10
url: /th/net/split-document/by-sections/
---

ในตัวอย่างนี้ เราจะแสดงวิธีแบ่งเอกสาร Word ออกเป็นส่วนต่างๆ โดยใช้คุณลักษณะ By Sections ของ Aspose.Words สำหรับ .NET ทำตามขั้นตอนด้านล่างเพื่อทำความเข้าใจซอร์สโค้ดและรับเอกสารแยกกันสำหรับแต่ละส่วน

## ขั้นตอนที่ 1: กำลังโหลดเอกสาร

ในการเริ่มต้น เราต้องระบุไดเรกทอรีของเอกสารของคุณและโหลดเอกสารลงในวัตถุเอกสาร มีวิธีดังนี้:

```csharp
// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## ขั้นตอนที่ 2: แบ่งเอกสารออกเป็นส่วนๆ

ตอนนี้เราจะวนซ้ำแต่ละส่วนของเอกสารและแบ่งเอกสารออกเป็นส่วนเล็กๆ ทีละส่วน ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// แบ่งเอกสารออกเป็นส่วนเล็กๆ ในกรณีนี้ โดยแยกตามส่วน
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// บันทึกแต่ละส่วนเป็นเอกสารแยกกัน
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### ตัวอย่างซอร์สโค้ดสำหรับ By Sections โดยใช้ Aspose.Words สำหรับ .NET

นี่คือซอร์สโค้ดที่สมบูรณ์สำหรับฟีเจอร์ By Sections ของ Aspose.Words สำหรับ .NET:

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

for (int i = 0; i < doc.Sections.Count; i++)
{
	// แบ่งเอกสารออกเป็นส่วนเล็กๆ ในกรณีนี้ โดยแยกตามส่วน
	Section section = doc.Sections[i].Clone();

	Document newDoc = new Document();
	newDoc.Sections.Clear();

	Section newSection = (Section) newDoc.ImportNode(section, true);
	newDoc.Sections.Add(newSection);

	// บันทึกแต่ละส่วนเป็นเอกสารแยกกัน
	newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
}
```

ด้วยรหัสนี้ คุณจะสามารถแบ่งเอกสาร Word ออกเป็นส่วนๆ ได้โดยใช้ Aspose.Words สำหรับ .NET

ตอนนี้คุณสามารถทำงานกับส่วนเฉพาะได้อย่างง่ายดาย

### บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจฟังก์ชันการแบ่งเอกสารตามส่วนของ Aspose.Words สำหรับ .NET เราเรียนรู้วิธีแบ่งเอกสาร Word ออกเป็นส่วนๆ โดยสร้างเอกสารแยกกันสำหรับแต่ละส่วน ด้วยการโหลดเอกสาร วนซ้ำแต่ละส่วน และบันทึกเป็นเอกสารแยกกัน เราจึงสามารถทำงานกับส่วนเฉพาะได้อย่างมีประสิทธิภาพ

การใช้คุณสมบัติแยกเอกสารตามส่วนจะเป็นประโยชน์เมื่อคุณต้องการจัดการหรือวิเคราะห์ส่วนเฉพาะของเอกสาร เช่น บท ส่วน หรือส่วนอื่นๆ Aspose.Words สำหรับ .NET มอบโซลูชันที่เชื่อถือได้และตรงไปตรงมาในการจัดการการแยกส่วน ช่วยให้สามารถประมวลผลเอกสารได้อย่างมีประสิทธิภาพ

รู้สึกอิสระที่จะสำรวจคุณสมบัติอันทรงพลังอื่นๆ ที่นำเสนอโดย Aspose.Words สำหรับ .NET เพื่อปรับปรุงความสามารถในการประมวลผลเอกสารของคุณและปรับปรุงขั้นตอนการทำงานของคุณ

### คำถามที่พบบ่อย

#### คำถามที่ 1: ฉันสามารถแบ่งเอกสาร Word ออกเป็นส่วน ๆ ตามเกณฑ์เฉพาะอื่นนอกเหนือจากตัวแบ่งส่วนได้หรือไม่
ได้ คุณสามารถปรับแต่งเกณฑ์การแบ่งได้ตามความต้องการเฉพาะของคุณ นอกเหนือจากการแบ่งส่วนแล้ว คุณยังสามารถแบ่งเอกสารตามองค์ประกอบอื่นๆ เช่น ส่วนหัว ที่คั่นหน้า หรือเนื้อหาเฉพาะ โดยใช้คุณสมบัติและวิธีการต่างๆ ที่ Aspose.Words สำหรับ .NET มอบให้

#### คำถามที่ 2: เป็นไปได้ไหมที่จะรวมส่วนต่างๆ กลับเป็นเอกสารเดียว
 ได้ คุณสามารถรวมส่วนที่แยกจากกันกลับเข้าไปในเอกสารเดียวได้โดยการนำเข้าและรวมส่วนต่างๆ จากเอกสารหลายฉบับโดยใช้`ImportNode` และ`Sections.Add` วิธีการ ซึ่งจะทำให้คุณสามารถย้อนกลับกระบวนการแยกและสร้างเอกสารต้นฉบับขึ้นมาใหม่ได้

#### คำถามที่ 3: มีข้อจำกัดเกี่ยวกับจำนวนส่วนที่สามารถแบ่งได้โดยใช้คุณลักษณะ "ตามส่วน" หรือไม่
จำนวนส่วนที่สามารถแบ่งได้โดยใช้คุณลักษณะ "ตามส่วน" ขึ้นอยู่กับความสามารถของ Aspose.Words สำหรับ .NET และทรัพยากรระบบที่มีอยู่ โดยทั่วไปแล้วจะรองรับการแบ่งเอกสารที่มีส่วนจำนวนมาก แต่เอกสารที่ยาวมากหรือมีจำนวนส่วนที่สูงมากอาจต้องใช้ทรัพยากรระบบเพิ่มเติมและเวลาในการประมวลผล

#### คำถามที่ 4: หลังจากแยกแล้ว ฉันสามารถดำเนินการเฉพาะในแต่ละส่วนได้หรือไม่
ได้ หลังจากแบ่งเอกสารออกเป็นส่วนๆ แล้ว คุณสามารถดำเนินการเฉพาะในแต่ละส่วนแยกกันได้ คุณสามารถจัดการเนื้อหา ใช้การจัดรูปแบบ แยกข้อมูลเฉพาะ หรือดำเนินการประมวลผลเอกสารอื่นๆ ตามความต้องการของคุณ

#### คำถามที่ 5: ฉันสามารถแยกเอกสาร Word ที่มีการป้องกันด้วยรหัสผ่านหรือเข้ารหัสโดยใช้ฟีเจอร์ "ตามส่วน" ได้หรือไม่
ไม่ คุณลักษณะ "ตามส่วน" ใช้งานได้กับเอกสาร Word ที่ไม่มีการป้องกัน หากเอกสารมีการป้องกันด้วยรหัสผ่านหรือเข้ารหัส คุณจะต้องระบุรหัสผ่านที่ถูกต้องและลบการป้องกันก่อนที่จะแบ่งเอกสารออกเป็นส่วนๆ
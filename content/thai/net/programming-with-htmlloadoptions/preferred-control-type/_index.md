---
title: ประเภทการควบคุมที่ต้องการในเอกสาร Word
linktitle: ประเภทการควบคุมที่ต้องการในเอกสาร Word
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนเพื่อระบุประเภทการควบคุมที่ต้องการในเอกสาร word เมื่อโหลดเอกสาร HTML ด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-htmlloadoptions/preferred-control-type/
---
บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการใช้ฟีเจอร์ชนิดการควบคุมที่ต้องการกับ Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนอย่างละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีระบุประเภทการควบคุมที่ต้องการเมื่อโหลดเอกสาร HTML

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดูไลบรารีและคำแนะนำในการติดตั้งได้จากเว็บไซต์ Aspose

## ขั้นตอนที่ 1: กำหนดโค้ด HTML

 ในการเริ่มต้น คุณต้องกำหนดโค้ด HTML ที่คุณต้องการโหลดเป็นเอกสาร ในตัวอย่างนี้ เราได้กำหนด`html` ตัวแปรที่มีรหัส HTML ของตัวเลือกพร้อมตัวเลือก

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## ขั้นตอนที่ 2: ตั้งค่าตัวเลือกการโหลด HTML

 ต่อไปเราจะสร้างไฟล์`HtmlLoadOptions` วัตถุและตั้งค่า`PreferredControlType`ทรัพย์สินเพื่อ`HtmlControlType.StructuredDocumentTag`- สิ่งนี้จะบอก Aspose.Words ให้ใช้ StructuredDocumentTags เพื่อแสดง HTML เมื่อโหลด

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## ขั้นตอนที่ 3: โหลดและบันทึกเอกสาร

 เราใช้`Document` คลาสเพื่อโหลดโค้ด HTML จากสตรีมหน่วยความจำพร้อมตัวเลือกการโหลดที่กำหนดไว้ก่อนหน้านี้ จากนั้นเราจะบันทึกเอกสารในไดเร็กทอรีที่ระบุด้วย`.docx`รูปแบบไฟล์.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### ตัวอย่างซอร์สโค้ดสำหรับประเภทการควบคุมที่ต้องการด้วย Aspose.Words สำหรับ .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

นั่นคือทั้งหมด! คุณได้ระบุประเภทการควบคุมที่ต้องการสำเร็จแล้วเมื่อโหลดเอกสาร HTML ด้วย Aspose.Words สำหรับ .NET

## บทสรุป

 ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะได้เรียนรู้วิธีใช้ฟีเจอร์ "ประเภทการควบคุมที่ต้องการ" ใน Aspose.Words สำหรับ .NET เพื่อระบุประเภทการควบคุมที่ต้องการเมื่อโหลดเอกสาร HTML การตั้งค่า`PreferredControlType`ทรัพย์สินเพื่อ`HtmlControlType.StructuredDocumentTag` อนุญาตให้ Aspose.Words ใช้ StructuredDocumentTags (SDT) เพื่อการแสดงและการประมวลผลเนื้อหา HTML ที่ดีขึ้น คุณสามารถสำรวจการควบคุมประเภทอื่นๆ ได้เช่นกันเพื่อให้เหมาะกับความต้องการเฉพาะของคุณ การใช้คุณสมบัตินี้ช่วยให้มั่นใจในการจัดการเอกสาร HTML ในแอปพลิเคชัน C# ของคุณด้วย Aspose.Words ได้อย่างแม่นยำและมีประสิทธิภาพ

### คำถามที่พบบ่อยสำหรับประเภทการควบคุมที่ต้องการในเอกสาร word

#### ถาม: ฟีเจอร์ "ประเภทการควบคุมที่ต้องการ" ใน Aspose.Words สำหรับ .NET คืออะไร

ตอบ: คุณลักษณะ "ประเภทการควบคุมที่ต้องการ" ช่วยให้คุณสามารถระบุประเภทการควบคุมที่ต้องการเพื่อแสดงองค์ประกอบ HTML เมื่อโหลดเอกสาร HTML ช่วยในการเลือกประเภทการควบคุมที่เหมาะสมสำหรับการแสดงและการประมวลผลเนื้อหา HTML ที่ดีขึ้น

#### ถาม: ฉันจะตั้งค่าประเภทการควบคุมที่ต้องการเมื่อโหลดเอกสาร HTML ได้อย่างไร

 ตอบ: หากต้องการตั้งค่าประเภทการควบคุมที่ต้องการ คุณต้องสร้าง`HtmlLoadOptions` วัตถุและตั้งค่า`PreferredControlType` ทรัพย์สินได้ตามต้องการ`HtmlControlType` - ในตัวอย่างที่ให้มา`HtmlControlType.StructuredDocumentTag` ถูกนำมาใช้.

#### ถาม: การใช้ StructuredDocumentTags (SDT) เป็นประเภทการควบคุมที่ต้องการมีความสำคัญอย่างไร

ตอบ: StructuredDocumentTags (SDT) เป็นองค์ประกอบที่ใช้ XML ซึ่งสามารถใช้เพื่อแสดงเนื้อหาและการควบคุมที่ซับซ้อนในเอกสาร Word การใช้ SDT เป็นตัวควบคุมประเภทที่ต้องการสามารถให้ความเข้ากันได้และการแสดงเนื้อหา HTML ได้ดีขึ้น

#### ถาม: ฉันจะมั่นใจได้อย่างไรว่า Aspose.Words ใช้ประเภทการควบคุมที่ต้องการเมื่อโหลดเอกสาร HTML

 ตอบ: โดยการตั้งค่า`PreferredControlType`ทรัพย์สินเพื่อ`HtmlControlType.StructuredDocumentTag`ดังที่แสดงในซอร์สโค้ดตัวอย่าง Aspose.Words จะใช้ SDT เพื่อแสดงองค์ประกอบ HTML เมื่อโหลดเอกสาร

#### ถาม: ฉันสามารถใช้การควบคุมประเภทอื่นเป็นตัวเลือกที่ต้องการได้หรือไม่

 ตอบ: ใช่ นอกเหนือจาก`HtmlControlType.StructuredDocumentTag` , Aspose.Words สำหรับ .NET รองรับการควบคุมประเภทอื่นๆ เช่น`HtmlControlType.ContentControl` และ`HtmlControlType.CustomXmlMarkup`.
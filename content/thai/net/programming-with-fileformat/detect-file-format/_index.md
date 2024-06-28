---
title: ตรวจจับรูปแบบไฟล์เอกสาร
linktitle: ตรวจจับรูปแบบไฟล์เอกสาร
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตรวจจับรูปแบบไฟล์เอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-fileformat/detect-file-format/
---

บทความนี้ให้คำแนะนำทีละขั้นตอนเกี่ยวกับวิธีการใช้คุณลักษณะการตรวจจับรูปแบบไฟล์เอกสารกับ Aspose.Words สำหรับ .NET เราจะอธิบายโค้ดแต่ละส่วนโดยละเอียด ในตอนท้ายของบทช่วยสอนนี้ คุณจะสามารถเข้าใจวิธีการตรวจสอบรูปแบบของไฟล์เอกสารต่างๆ

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Words สำหรับ .NET ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดูไลบรารีและคำแนะนำในการติดตั้งได้จากเว็บไซต์ Aspose

## ขั้นตอนที่ 1: กำหนดไดเรกทอรี

 ในการเริ่มต้น คุณจะต้องกำหนดไดเร็กทอรีที่คุณต้องการจัดเก็บไฟล์ตามรูปแบบ แทนที่`"YOUR DOCUMENT DIRECTORY"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ เราสร้างไดเร็กทอรี "Supported", "Unknown", "Encrypted" และ "Pre97" หากยังไม่มีอยู่

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// สร้างไดเร็กทอรีหากยังไม่มี
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## ขั้นตอนที่ 2: เรียกดูไฟล์

 จากนั้นเราก็ใช้`GetFiles` วิธีการของ`Directory` คลาสเพื่อรับรายการไฟล์ในไดเร็กทอรีที่ระบุ เรายังใช้ก`Where`ส่วนคำสั่งเพื่อยกเว้นไฟล์เฉพาะชื่อ "Corrupted document.docx"

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## ขั้นตอนที่ 3: ตรวจหารูปแบบของแต่ละไฟล์

 เราวนซ้ำแต่ละไฟล์ในรายการและใช้ไฟล์`DetectFileFormat` วิธีการของ`FileFormatUtil` คลาสเพื่อตรวจจับรูปแบบของไฟล์ เรายังแสดงประเภทเอกสารที่ตรวจพบด้วย

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// แสดงประเภทเอกสาร
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ...เพิ่มเคสสำหรับรูปแบบเอกสารอื่นๆ ที่รองรับ
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

นั่นคือทั้งหมด! คุณตรวจพบรูปแบบของไฟล์เอกสารที่แตกต่างกันโดยใช้ Aspose.Words สำหรับ .NET สำเร็จ

### ตัวอย่างซอร์สโค้ดสำหรับการตรวจจับรูปแบบไฟล์ด้วย Aspose.Words สำหรับ .NET

```csharp

	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// สร้างไดเร็กทอรีหากยังไม่มี
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// แสดงประเภทเอกสาร
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### คำถามที่พบบ่อยสำหรับการตรวจหารูปแบบไฟล์เอกสาร

#### จะตรวจสอบรูปแบบของไฟล์เอกสารโดยใช้ Aspose.Words สำหรับ .NET ได้อย่างไร

 หากต้องการตรวจจับรูปแบบของไฟล์เอกสารโดยใช้ Aspose.Words สำหรับ .NET คุณสามารถทำตามขั้นตอนที่ให้ไว้ในบทช่วยสอน ใช้`DetectFileFormat` วิธีการของ`FileFormatUtil`class จะช่วยให้คุณสามารถตรวจจับรูปแบบของไฟล์เอกสารได้ ซึ่งจะช่วยให้คุณสามารถระบุได้ว่าเป็นเอกสาร Microsoft Word 97-2003, เทมเพลต, เอกสาร Office Open XML WordprocessingML หรือรูปแบบอื่นๆ ที่รองรับ รหัสที่ให้ไว้ในบทช่วยสอนจะแนะนำคุณตลอดขั้นตอนการใช้งานคุณสมบัตินี้

#### Aspose.Words for .NET รองรับรูปแบบเอกสารใดบ้าง

Aspose.Words สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึงเอกสาร Microsoft Word 97-2003 (DOC), เทมเพลต (DOT), เอกสาร Office Open XML WordprocessingML (DOCX), เอกสาร Office Open XML WordprocessingML พร้อมมาโคร (DOCM), Office Open เทมเพลต XML WordprocessingML ที่ไม่มีมาโคร (DOTX), เทมเพลต Office Open OpenDocument Text (OTT), เอกสาร MS Word 6 หรือ Word 95 และรูปแบบเอกสารที่ไม่รู้จัก

#### วิธีจัดการกับไฟล์เอกสารที่เข้ารหัสระหว่างการตรวจจับรูปแบบ

 เมื่อตรวจพบรูปแบบของไฟล์เอกสาร คุณสามารถใช้รูปแบบ`IsEncrypted` ทรัพย์สินของ`FileFormatInfo` วัตถุเพื่อตรวจสอบว่าไฟล์ถูกเข้ารหัสหรือไม่ หากไฟล์ถูกเข้ารหัส คุณสามารถดำเนินการขั้นตอนเพิ่มเติมเพื่อจัดการกับกรณีเฉพาะนี้ได้ เช่น การคัดลอกไฟล์ไปยังไดเร็กทอรีสำหรับเอกสารที่เข้ารหัสโดยเฉพาะ คุณสามารถใช้`File.Copy` วิธีการทำเช่นนี้

#### ควรดำเนินการอย่างไรเมื่อไม่ทราบรูปแบบของเอกสาร

เมื่อไม่ทราบรูปแบบของเอกสาร คุณสามารถตัดสินใจจัดการในรูปแบบเฉพาะสำหรับแอปพลิเคชันของคุณได้ ในตัวอย่างที่ให้ไว้ในบทช่วยสอน เอกสารจะถูกคัดลอกไปยังไดเร็กทอรีเฉพาะสำหรับเอกสารที่ไม่ทราบรูปแบบ คุณสามารถปรับแต่งการกระทำนี้ให้เหมาะกับความต้องการเฉพาะของคุณได้

#### มีคุณสมบัติอื่นใดของ Aspose.Words สำหรับ .NET ที่สามารถใช้ร่วมกับการตรวจจับรูปแบบเอกสารได้หรือไม่

ใช่ Aspose.Words สำหรับ .NET นำเสนอคุณสมบัติอื่นๆ มากมายสำหรับการประมวลผลและจัดการเอกสาร Word ตัวอย่างเช่น คุณสามารถใช้ไลบรารีเพื่อแยกข้อความ รูปภาพ หรือข้อมูลเมตาจากเอกสาร นำการเปลี่ยนแปลงการจัดรูปแบบ ผสานเอกสาร แปลงเอกสารเป็นรูปแบบต่างๆ และอื่นๆ อีกมากมาย
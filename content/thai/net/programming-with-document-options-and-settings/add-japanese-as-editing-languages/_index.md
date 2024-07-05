---
title: เพิ่มภาษาญี่ปุ่นเป็นภาษาสำหรับการแก้ไข
linktitle: เพิ่มภาษาญี่ปุ่นเป็นภาษาสำหรับการแก้ไข
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการเพิ่มภาษาญี่ปุ่นเป็นภาษาแก้ไขด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

ในบทช่วยสอนนี้ เราจะนำคุณทีละขั้นตอนเพื่อทำความเข้าใจและใช้งานฟังก์ชันการเพิ่มภาษาญี่ปุ่นเป็นภาษาแก้ไขด้วย Aspose.Words สำหรับ .NET คุณลักษณะนี้ช่วยให้คุณสามารถตั้งค่าภาษาเมื่อโหลดเอกสารและเพิ่มภาษาญี่ปุ่นเป็นภาษาสำหรับแก้ไข

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่ไม่มีภาษาสำหรับการแก้ไขเริ่มต้นและเราต้องการเพิ่มภาษาญี่ปุ่น ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
LoadOptions loadOptions = new LoadOptions();

// ตั้งค่ากำหนดภาษาที่จะใช้เมื่อโหลดเอกสาร
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## ขั้นตอนที่ 3: การตรวจสอบภาษาเริ่มต้น

หลังจากโหลดเอกสาร เราจะตรวจสอบว่าภาษาเริ่มต้นสำหรับการแก้ไขได้รับการตั้งค่าเป็นภาษาญี่ปุ่นอย่างถูกต้องหรือไม่ ใช้รหัสต่อไปนี้เพื่อรับรหัสภาษาฟาร์อีสเทอร์น:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

รหัสจะตรวจสอบว่ารหัสภาษาฟาร์อีสเทิร์นตรงกับรหัสภาษาญี่ปุ่นหรือไม่ ตามผลลัพธ์จะแสดงข้อความที่เกี่ยวข้อง

### ตัวอย่างซอร์สโค้ดสำหรับการเพิ่มภาษาญี่ปุ่นเป็นภาษาการแก้ไขโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// ตั้งค่ากำหนดภาษาที่จะใช้เมื่อมีการโหลดเอกสาร
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```


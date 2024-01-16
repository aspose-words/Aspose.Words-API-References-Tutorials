---
title: ตั้งค่าภาษารัสเซียเป็นภาษาการแก้ไขเริ่มต้น
linktitle: ตั้งค่าภาษารัสเซียเป็นภาษาการแก้ไขเริ่มต้น
second_title: Aspose.Words API การประมวลผลเอกสาร
description: คำแนะนำทีละขั้นตอนในการตั้งค่าภาษารัสเซียเป็นภาษาเริ่มต้นในการแก้ไขเอกสารด้วย Aspose.Words สำหรับ .NET
type: docs
weight: 10
url: /th/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับซอร์สโค้ด C# เพื่อตั้งค่าภาษารัสเซียเป็นภาษาแก้ไขเริ่มต้นด้วย Aspose.Words สำหรับ .NET คุณสมบัตินี้ช่วยให้คุณสามารถตั้งค่าภาษาเริ่มต้นเมื่อโหลดเอกสาร

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ในการเริ่มต้น ให้สร้างโปรเจ็กต์ C# ใหม่ใน IDE ที่คุณชื่นชอบ ตรวจสอบให้แน่ใจว่าไลบรารี Aspose.Words สำหรับ .NET ถูกอ้างอิงในโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: กำลังโหลดเอกสาร

ในขั้นตอนนี้ เราจะโหลดเอกสาร Word ที่เราต้องการตั้งค่าภาษารัสเซียเป็นภาษาเริ่มต้นสำหรับการแก้ไข ใช้รหัสต่อไปนี้เพื่อโหลดเอกสาร:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// พาธไปยังไดเร็กทอรีเอกสาร
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 แทนที่`"YOUR DOCUMENTS DIRECTORY"` ด้วยเส้นทางจริงของไดเร็กทอรีที่เอกสารของคุณตั้งอยู่

## ขั้นตอนที่ 3: การตรวจสอบภาษาเริ่มต้น

หลังจากอัปโหลดเอกสาร เราจะตรวจสอบว่าภาษาเริ่มต้นได้รับการตั้งค่าอย่างถูกต้องเป็นภาษารัสเซียหรือไม่ ใช้รหัสต่อไปนี้เพื่อรับรหัสภาษาเริ่มต้น:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

รหัสจะตรวจสอบว่ารหัสภาษาตรงกับภาษารัสเซียหรือไม่ ตามผลลัพธ์จะแสดงข้อความที่เกี่ยวข้อง

### ตัวอย่างซอร์สโค้ดสำหรับตั้งค่าภาษารัสเซียเป็นภาษาการแก้ไขเริ่มต้นโดยใช้ Aspose.Words สำหรับ .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 อย่าลืมระบุเส้นทางเอกสารที่ถูกต้องใน`dataDir` ตัวแปร.

ตอนนี้คุณได้เรียนรู้วิธีตั้งค่าภาษารัสเซียเป็นภาษาเริ่มต้นสำหรับการแก้ไขสำหรับเอกสารโดยใช้ Aspose.Words สำหรับ .NET โดยทำตามคำแนะนำขั้นตอน
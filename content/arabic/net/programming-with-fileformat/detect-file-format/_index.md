---
title: كشف تنسيق ملف المستند
linktitle: كشف تنسيق ملف المستند
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لاكتشاف تنسيق ملف المستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-fileformat/detect-file-format/
---

توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة الكشف عن تنسيق ملف المستند مع Aspose.Words لـ .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستتمكن من فهم كيفية اكتشاف تنسيق ملفات المستندات المختلفة.

قبل البدء، تأكد من تثبيت وتكوين مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وتعليمات التثبيت على موقع Aspose.

## الخطوة 1: تحديد الدلائل

 للبدء، تحتاج إلى تحديد الدلائل التي تريد تخزين الملفات فيها وفقًا لتنسيقها. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك. نقوم بإنشاء الدلائل "مدعم" و"غير معروف" و"مشفر" و"Pre97" إذا لم تكن موجودة بالفعل.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// قم بإنشاء الدلائل إذا لم تكن موجودة بالفعل.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## الخطوة 2: تصفح الملفات

 ثم نستخدم`GetFiles` طريقة`Directory` class للحصول على قائمة الملفات في الدليل المحدد. نحن نستخدم أيضا أ`Where`عبارة لاستبعاد ملف محدد يسمى "مستند تالف.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## الخطوة 3: الكشف عن تنسيق كل ملف

 نقوم بالتكرار خلال كل ملف في القائمة ونستخدم ملف`DetectFileFormat` طريقة`FileFormatUtil` فئة للكشف عن تنسيق الملف. نعرض أيضًا نوع المستند المكتشف.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// عرض نوع الوثيقة
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
// ... أضف حالات لتنسيقات المستندات المدعومة الأخرى
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

هذا كل شئ ! لقد نجحت في اكتشاف تنسيق ملفات المستندات المختلفة باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لاكتشاف تنسيق الملف باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// قم بإنشاء الدلائل إذا لم تكن موجودة بالفعل.
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

		// عرض نوع الوثيقة
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

### الأسئلة المتداولة حول اكتشاف تنسيق ملف المستند

#### كيفية اكتشاف تنسيق ملف المستند باستخدام Aspose.Words لـ .NET؟

 لاكتشاف تنسيق ملف مستند باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات الواردة في البرنامج التعليمي. باستخدام`DetectFileFormat` طريقة`FileFormatUtil`سيسمح لك الفصل باكتشاف تنسيق ملف المستند. سيسمح لك هذا بتحديد ما إذا كان مستند Microsoft Word 97-2003 أو قالبًا أو مستند Office Open XML WordprocessingML أو تنسيقات أخرى مدعومة. سيرشدك الكود الموجود في البرنامج التعليمي خلال تنفيذ هذه الميزة.

#### ما هي تنسيقات المستندات التي يدعمها Aspose.Words لـ .NET؟

يدعم Aspose.Words for .NET مجموعة متنوعة من تنسيقات المستندات بما في ذلك مستندات Microsoft Word 97-2003 (DOC)، والقوالب (DOT)، ومستندات Office Open XML WordprocessingML (DOCX)، ومستندات Office Open XML WordprocessingML مع وحدات الماكرو (DOCM)، وOffice Open قوالب XML WordprocessingML بدون وحدات ماكرو (DOTX)، قوالب Office Open XML WordprocessingML مع وحدات ماكرو (DOTM)، مستندات OPC المسطحة، مستندات RTF، مستندات Microsoft Word 2003 WordprocessingML، مستندات HTML، مستندات MHTML (أرشيف الويب)، مستندات نص OpenDocument (ODT)، قوالب OpenDocument Text (OTT)، ومستندات MS Word 6 أو Word 95، وتنسيقات المستندات غير المعروفة.

#### كيفية التعامل مع ملفات المستندات المشفرة أثناء الكشف عن التنسيق؟

 عند اكتشاف تنسيق ملف مستند، يمكنك استخدام الملف`IsEncrypted` ملكية`FileFormatInfo` كائن للتحقق مما إذا كان الملف مشفرًا. إذا كان الملف مشفرًا، فيمكنك اتخاذ خطوات إضافية للتعامل مع هذه الحالة المحددة، مثل نسخ الملف إلى دليل مخصص للمستندات المشفرة. يمكنك استخدام ال`File.Copy` طريقة للقيام بذلك.

#### ما هي الإجراءات التي يجب اتخاذها عندما يكون تنسيق المستند غير معروف؟

عندما يكون تنسيق المستند غير معروف، يمكنك أن تقرر التعامل معه بطريقة خاصة بتطبيقك. في المثال المقدم في البرنامج التعليمي، يتم نسخ المستند إلى دليل محدد مخصص للمستندات ذات التنسيق غير المعروف. يمكنك تخصيص هذا الإجراء ليناسب احتياجاتك الخاصة.

#### هل هناك أي ميزات أخرى لـ Aspose.Words for .NET يمكن استخدامها مع اكتشاف تنسيق المستند؟

نعم، يوفر Aspose.Words for .NET العديد من الميزات الأخرى لمعالجة مستندات Word ومعالجتها. على سبيل المثال، يمكنك استخدام المكتبة لاستخراج النص أو الصور أو بيانات التعريف من المستندات، وتطبيق تغييرات التنسيق، ودمج المستندات، وتحويل المستندات إلى تنسيقات مختلفة، والمزيد.
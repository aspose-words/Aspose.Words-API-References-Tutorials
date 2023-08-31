---
title: قائمة استخدام أنماط الوجهة
linktitle: قائمة استخدام أنماط الوجهة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ضم مستندات Word وإلحاقها مع الحفاظ على أنماط قائمة المستند الوجهة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/list-use-destination-styles/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة "قائمة استخدام أنماط الوجهة" في Aspose.Words for .NET. تسمح لك هذه الميزة بالانضمام إلى مستندات Word وإلحاقها أثناء استخدام أنماط القائمة الخاصة بالمستند الوجهة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت Aspose.Words لـ .NET. يمكنك تنزيله من موقع Aspose أو تثبيته عبر NuGet.
2. Visual Studio أو أي بيئة تطوير أخرى لـ C#.

## الخطوة 1: تهيئة أدلة المستندات

 أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. تعديل قيمة`dataDir`متغير إلى المسار حيث توجد المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستندات المصدر والوجهة

 بعد ذلك، تحتاج إلى تحميل المستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في`Document` مُنشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## الخطوة 3: قم بتعيين المستند المصدر للمتابعة بعد المستند الوجهة

 للتأكد من أن المحتوى من المستند المصدر يستمر بعد نهاية المستند الوجهة، تحتاج إلى تعيين`SectionStart` خاصية القسم الأول في الوثيقة المصدر ل`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: التعامل مع تنسيق القائمة

للتعامل مع تنسيق القائمة، سوف تقوم بالتكرار خلال كل فقرة في المستند المصدر والتحقق مما إذا كان عنصر قائمة. إذا كان الأمر كذلك، فسوف تقوم بمقارنة معرف القائمة بالقوائم الموجودة في المستند الوجهة. في حالة وجود قائمة بنفس المعرف، فسوف تقوم بإنشاء نسخة من القائمة في المستند المصدر وتحديث تنسيق قائمة الفقرة لاستخدام القائمة المنسوخة.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## الخطوة 5: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.UseDestinationStyles` تضمن المعلمة استخدام أنماط قائمة المستند الوجهة أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## الخطوة 6: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج مع تمكين ميزة "قائمة استخدام أنماط الوجهة" باستخدام`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### مثال على التعليمات البرمجية المصدر لقائمة استخدام أنماط الوجهة باستخدام Aspose.Words لـ .NET 

إليك الكود المصدري الكامل لميزة "قائمة استخدام أنماط الوجهة" في لغة C# باستخدام Aspose.Words for .NET:


```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//قم بتعيين المستند المصدر للمتابعة مباشرة بعد نهاية المستند الوجهة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// تتبع القوائم التي تم إنشاؤها.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// تحقق مما إذا كان المستند الوجهة يحتوي على قائمة بهذا المعرف بالفعل. إذا كان الأمر كذلك، فهذا قد يكون
			//يتسبب في تشغيل القائمتين معًا. قم بإنشاء نسخة من القائمة في المستند المصدر بدلاً من ذلك.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// هناك قائمة منسوخة حديثًا موجودة بالفعل لهذا المعرف، قم باسترداد القائمة المخزنة،
				// واستخدامها في الفقرة الحالية.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// أضف نسخة من هذه القائمة إلى المستند وقم بتخزينها للرجوع إليها لاحقًا.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// اضبط قائمة هذه الفقرة على القائمة المنسوخة.
				para.ListFormat.List = currentList;
			}
		}
	}
	// إلحاق المستند المصدر بنهاية المستند الوجهة.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة "قائمة استخدام أنماط الوجهة" باستخدام Aspose.Words لـ .NET. سيحتوي المستند النهائي على المحتوى المدمج مع أنماط القائمة من المستند الوجهة.
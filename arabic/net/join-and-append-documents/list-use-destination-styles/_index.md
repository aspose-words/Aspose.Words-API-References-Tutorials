---
title: قائمة استخدام أنماط الوجهة
linktitle: قائمة استخدام أنماط الوجهة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية الانضمام إلى مستندات Word وإلحاقها مع الاحتفاظ بأنماط قائمة المستندات الوجهة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/list-use-destination-styles/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة قائمة استخدام أنماط الوجهة في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها أثناء استخدام أنماط القائمة الخاصة بالمستند الوجهة.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تم تثبيت Aspose.Words for .NET. يمكنك تنزيله من موقع Aspose أو تثبيته عبر NuGet.
2. Visual Studio أو أي بيئة تطوير C # أخرى.

## الخطوة 1: تهيئة دلائل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى دليل المستند الخاص بك. قم بتعديل قيمة ملف`dataDir`متغير إلى المسار حيث توجد المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستندات المصدر والوجهة

 بعد ذلك ، تحتاج إلى تحميل مستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في ملف`Document` المُنشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## الخطوة 3: قم بتعيين المستند المصدر للمتابعة بعد مستند الوجهة

 للتأكد من استمرار المحتوى من المستند المصدر بعد نهاية المستند الوجهة ، تحتاج إلى تعيين`SectionStart` من القسم الأول في المستند المصدر إلى`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: معالجة تنسيق القائمة

للتعامل مع تنسيق القائمة ، ستقوم بالتكرار خلال كل فقرة في المستند المصدر والتحقق مما إذا كانت عنصر قائمة. إذا كان الأمر كذلك ، فستقارن معرف القائمة بالقوائم الموجودة في مستند الوجهة. في حالة وجود قائمة بنفس المعرف ، ستقوم بإنشاء نسخة من القائمة في المستند المصدر وتحديث تنسيق قائمة الفقرة لاستخدام القائمة المنسوخة.

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

## الخطوة 5: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.UseDestinationStyles` تضمن المعلمة استخدام أنماط قائمة المستند الوجهة أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## الخطوة 6: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع تمكين ميزة List Use Destination Styles باستخدام ملحق`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### مثال على شفرة المصدر لقائمة استخدم أنماط الوجهة باستخدام Aspose.Words for .NET 

إليك شفرة المصدر الكاملة لميزة "List Use Destination Styles" في C # باستخدام Aspose.Words for .NET:


```csharp
	//المسار إلى دليل المستند الخاص بك
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
			// تحقق مما إذا كان المستند الوجهة يحتوي على قائمة بهذا المعرف بالفعل. إذا كان الأمر كذلك ، فقد يكون هذا
			//يتسبب في تشغيل القائمتين معًا. قم بإنشاء نسخة من القائمة في المستند المصدر بدلاً من ذلك.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// توجد بالفعل قائمة تم نسخها حديثًا لهذا المعرف ، واسترجع القائمة المخزنة ،
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
	// قم بإلحاق المستند المصدر بنهاية المستند الوجهة.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة قائمة استخدام أنماط الوجهة باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع أنماط القائمة من المستند الوجهة.
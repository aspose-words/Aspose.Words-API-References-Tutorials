---
title: أدخل مستندًا عند الاستبدال
linktitle: أدخل مستندًا عند الاستبدال
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج مستند Word في مستند آخر بسلاسة باستخدام Aspose.Words for .NET من خلال دليلنا التفصيلي خطوة بخطوة. مثالي للمطورين الذين يتطلعون إلى تبسيط عملية معالجة المستندات.
type: docs
weight: 10
url: /ar/net/clone-and-combine-documents/insert-document-at-replace/
---
## مقدمة

مرحبًا، أيها الأساتذة المستنديون! هل وجدت نفسك غارقًا في البرمجة، محاولًا معرفة كيفية إدراج مستند Word في مستند آخر بسلاسة؟ لا تخف، لأننا سنغوص اليوم في عالم Aspose.Words for .NET لنجعل هذه المهمة في غاية السهولة. سنتعرف على دليل تفصيلي خطوة بخطوة حول كيفية استخدام هذه المكتبة القوية لإدراج المستندات في نقاط محددة أثناء عملية البحث والاستبدال. هل أنت مستعد لتصبح معالج Aspose.Words؟ دعونا نبدأ!

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، هناك بعض الأشياء التي يجب أن تكون لديك:

-  Visual Studio: تأكد من تثبيت Visual Studio على جهازك. إذا لم يكن لديك بعد، يمكنك تنزيله من[هنا](https://visualstudio.microsoft.com/).
-  Aspose.Words لـ .NET: ستحتاج إلى مكتبة Aspose.Words. يمكنك الحصول عليه من[موقع أسبوز](https://releases.aspose.com/words/net/).
- المعرفة الأساسية لـ C#: الفهم الأساسي لـ C# و.NET سيساعدك على متابعة هذا البرنامج التعليمي.

حسنًا، مع إبعاد هؤلاء عن الطريق، دعونا نتسخ أيدينا ببعض التعليمات البرمجية!

## استيراد مساحات الأسماء

أول الأشياء أولاً، نحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Words. هذا يشبه جمع كل أدواتك قبل بدء المشروع. قم بإضافة هذه التعليمات باستخدام التوجيهات الموجودة أعلى ملف C# الخاص بك:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

الآن بعد أن أصبح لدينا متطلباتنا الأساسية، دعونا نقسم العملية إلى خطوات صغيرة. كل خطوة حاسمة وسوف تقربنا من هدفنا.

## الخطوة 1: إعداد دليل المستندات

أولاً، نحتاج إلى تحديد الدليل الذي سيتم تخزين مستنداتنا فيه. هذا يشبه إعداد المسرح قبل الأداء الكبير.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار إلى الدليل الخاص بك. هذا هو المكان الذي ستعيش فيه مستنداتك وتتنفس.

## الخطوة 2: قم بتحميل المستند الرئيسي

بعد ذلك، نقوم بتحميل المستند الرئيسي الذي نريد إدراج مستند آخر فيه. فكر في هذا باعتباره مرحلتنا الرئيسية حيث سيحدث كل الإجراء.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

يقوم هذا الرمز بتحميل المستند الرئيسي من الدليل المحدد.

## الخطوة 3: قم بتعيين خيارات البحث والاستبدال

للعثور على الموقع المحدد الذي نريد إدراج المستند فيه، نستخدم وظيفة البحث والاستبدال. وهذا يشبه استخدام الخريطة للعثور على المكان المحدد لإضافتنا الجديدة.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

هنا، نقوم بتعيين الاتجاه إلى الخلف وتحديد معالج رد الاتصال المخصص الذي سنحدده بعد ذلك.

## الخطوة 4: تنفيذ عملية الاستبدال

الآن، نطلب من مستندنا الرئيسي أن يبحث عن نص عنصر نائب محدد ويستبدله بلا شيء، أثناء استخدام رد الاتصال المخصص لدينا لإدراج مستند آخر.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

ينفذ هذا الرمز عملية البحث والاستبدال، ثم يحفظ المستند المحدث.

## الخطوة 5: إنشاء معالج استبدال رد الاتصال المخصص

معالج رد الاتصال المخصص لدينا هو المكان الذي يحدث فيه السحر. سيحدد هذا المعالج كيفية تنفيذ عملية إدراج المستند أثناء عملية البحث والاستبدال.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // قم بإدراج مستند بعد الفقرة التي تحتوي على النص المطابق.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // قم بإزالة الفقرة التي تحتوي على النص المطابق.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

هنا، نقوم بتحميل المستند المراد إدراجه ثم نستدعي أسلوبًا مساعدًا لإجراء عملية الإدراج.

## الخطوة 6: تحديد طريقة إدراج المستند

الجزء الأخير من لغزنا هو الطريقة التي تقوم بالفعل بإدراج المستند في الموقع المحدد.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// قم بالمرور عبر جميع العقد على مستوى الكتلة في نص القسم،
		// ثم قم باستنساخ وإدراج كل عقدة ليست آخر فقرة فارغة في القسم.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

تهتم هذه الطريقة باستيراد العقد من المستند المراد إدراجه ووضعها في المكان الصحيح في المستند الرئيسي.

## خاتمة

وهنا لديك! دليل شامل لإدراج مستند في مستند آخر باستخدام Aspose.Words لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة أتمتة مهام تجميع المستندات ومعالجتها. سواء كنت تقوم بإنشاء نظام لإدارة المستندات أو تحتاج فقط إلى تبسيط سير عمل معالجة المستندات لديك، فإن Aspose.Words هو صديقك الموثوق.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية لمعالجة مستندات Word برمجيًا. يتيح لك إنشاء مستندات Word وتعديلها وتحويلها ومعالجتها بسهولة.

### هل يمكنني إدراج عدة مستندات في وقت واحد؟
نعم، يمكنك تعديل معالج رد الاتصال للتعامل مع عمليات الإدراج المتعددة عن طريق التكرار على مجموعة من المستندات.

### هل هناك نسخة تجريبية مجانية متاحة؟
 قطعاً! يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم لـ Aspose.Words؟
يمكنك الحصول على الدعم من خلال زيارة[منتدى Aspose.Words](https://forum.aspose.com/c/words/8).

### هل يمكنني الاحتفاظ بتنسيق المستند المدرج؟
 نعم`NodeImporter` تتيح لك الفئة تحديد كيفية التعامل مع التنسيق عند استيراد العقد من مستند إلى آخر.
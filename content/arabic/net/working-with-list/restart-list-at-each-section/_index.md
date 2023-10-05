---
title: إعادة تشغيل القائمة في كل قسم
linktitle: إعادة تشغيل القائمة في كل قسم
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إعادة تعيين قائمة مرقمة لكل قسم في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-list/restart-list-at-each-section/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنوضح لك كيفية إعادة تعيين قائمة مرقمة لكل قسم في مستند Word باستخدام Aspose.Words for .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء، تأكد من تثبيت Aspose.Words for .NET وتكوينه في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك بالفعل، قم بتنزيل المكتبة وتثبيتها من[Aspose.Releases]https://releases.aspose.com/words/net/.

## الخطوة 1: إنشاء المستند والقائمة

أولاً، قم بإنشاء مستند جديد وإضافة قائمة مرقمة افتراضية:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## الخطوة 2: إضافة عناصر إلى القائمة

 ثم استخدم أ`DocumentBuilder` لإضافة عناصر إلى القائمة. يمكنك استخدام حلقة لإضافة عناصر متعددة إلى القائمة:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

في هذا المثال، نقوم بإدراج فاصل مقطعي بعد عنصر القائمة الخامس عشر لتوضيح إعادة الترقيم.

## الخطوة 3: احفظ المستند المعدل

وأخيرا، احفظ الوثيقة المعدلة:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

لذا ! لقد نجحت في إعادة تعيين قائمة مرقمة لكل قسم في مستند Word باستخدام Aspose.Words لـ .NET.

### مثال على كود المصدر لإعادة ضبط القائمة في كل قسم

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله ليناسب احتياجاتك الخاصة.

### الأسئلة الشائعة

#### س: كيف يمكنني إعادة تشغيل القائمة في كل قسم في Aspose.Words؟

 ج: لإعادة تشغيل قائمة في كل قسم في Aspose.Words، تحتاج إلى إنشاء مثيل لـ`List` فئة وتعيين قائمة مرقمة لها. ثم يمكنك استخدام`List.IsRestartAtEachSection` الخاصية لتحديد أنه يجب إعادة تشغيل الترقيم في كل قسم. يمكنك ربط هذه القائمة بقسم واحد أو أكثر من مستندك بحيث يتم إعادة تشغيل الترقيم بشكل صحيح في كل قسم.

#### س: هل يمكنني تخصيص تنسيق ترقيم القوائم في Aspose.Words؟

ج: نعم، يمكنك تخصيص تنسيق ترقيم القوائم في Aspose.Words. ال`List` تقدم الطبقة العديد من الخصائص لهذا، مثل`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`، وما إلى ذلك. يمكنك استخدام هذه الخصائص لتعيين نوع القائمة (مرقمة، نقطية، وما إلى ذلك)، وتنسيق الترقيم (الأرقام العربية، والأرقام الرومانية، والحروف، وما إلى ذلك)، وخيارات تنسيق الترقيم الأخرى.

#### س: هل من الممكن إضافة مستويات إضافية إلى قائمة مرقمة في Aspose.Words؟

 ج: نعم، من الممكن إضافة مستويات إضافية إلى القائمة المرقمة في Aspose.Words. ال`ListLevel` يسمح لك class بتعيين خصائص التنسيق لكل مستوى من القائمة. يمكنك تعيين خيارات مثل البادئة، واللاحقة، والمحاذاة، والمسافة البادئة، وما إلى ذلك. ويتيح لك ذلك إنشاء قوائم ذات مستويات متعددة من التسلسل الهرمي.
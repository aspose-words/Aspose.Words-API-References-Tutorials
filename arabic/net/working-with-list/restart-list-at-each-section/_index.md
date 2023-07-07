---
title: قائمة إعادة التشغيل في كل قسم
linktitle: قائمة إعادة التشغيل في كل قسم
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إعادة تعيين قائمة مرقمة لكل قسم في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-list/restart-list-at-each-section/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوضح لك كيفية إعادة تعيين قائمة مرقمة لكل قسم في مستند Word باستخدام Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت Aspose.Words for .NET وتهيئته في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: إنشاء المستند والقائمة

أولاً ، أنشئ مستندًا جديدًا وأضف قائمة رقمية افتراضية:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## الخطوة 2: إضافة عناصر إلى القائمة

 ثم استخدم ملف`DocumentBuilder` لإضافة عناصر إلى القائمة. يمكنك استخدام حلقة لإضافة عناصر متعددة إلى القائمة:

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

في هذا المثال ، نقوم بإدراج فاصل مقطعي بعد عنصر القائمة الخامس عشر لتوضيح إعادة الترقيم.

## الخطوة 3: احفظ المستند المعدل

أخيرًا ، احفظ المستند المعدل:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

لذا ! لقد نجحت في إعادة تعيين قائمة مرقمة لكل قسم في مستند Word باستخدام Aspose.Words for .NET.

### مثال على كود المصدر لإعادة تعيين القائمة في كل قسم

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

### التعليمات

#### س: كيف يمكنني إعادة تشغيل قائمة في كل قسم في Aspose.Words؟

 ج: لإعادة تشغيل قائمة في كل قسم في Aspose.Words ، تحتاج إلى إنشاء مثيل لـ`List` فئة وتعيين قائمة مرقمة لها. ثم يمكنك استخدام ملف`List.IsRestartAtEachSection` لتحديد أن الترقيم يجب إعادة تشغيله في كل قسم. يمكنك إقران هذه القائمة بقسم واحد أو أكثر من المستند الخاص بك بحيث تتم إعادة تشغيل الترقيم بشكل صحيح في كل قسم.

#### س: هل يمكنني تخصيص تنسيق الترقيم للقوائم في Aspose.Words؟

 ج: نعم ، يمكنك تخصيص تنسيق الترقيم للقوائم في Aspose.Words. ال`List` تقدم فئة عدة خصائص لهذا ، مثل`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`، إلخ. يمكنك استخدام هذه الخصائص لتعيين نوع القائمة (مرقمة ، نقطية ، إلخ) ، تنسيق الترقيم (أرقام عربية ، أرقام رومانية ، أحرف ، إلخ) ، وخيارات تنسيق الترقيم الأخرى.

#### س: هل من الممكن إضافة مستويات إضافية إلى قائمة ذات تعداد رقمي في Aspose.Words؟

 ج: نعم ، من الممكن إضافة مستويات إضافية إلى قائمة ذات تعداد رقمي في Aspose.Words. ال`ListLevel` تسمح لك class بتعيين خصائص التنسيق لكل مستوى من القائمة. يمكنك تعيين خيارات مثل البادئة ، واللاحقة ، والمحاذاة ، والمسافة البادئة ، وما إلى ذلك. وهذا يسمح لك بإنشاء قوائم بمستويات متعددة من التسلسل الهرمي.
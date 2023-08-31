---
title: استبدال الارتباطات التشعبية
linktitle: استبدال الارتباطات التشعبية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: استبدل الارتباطات التشعبية في مستندات Word باستخدام Aspose.Words لـ .NET. إرشادات خطوة بخطوة لاستبدال الارتباطات التشعبية.
type: docs
weight: 10
url: /ar/net/working-with-fields/replace-hyperlinks/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# التالية لاستبدال الارتباطات التشعبية باستخدام Aspose.Words لوظيفة .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: قم بتعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 تأكد من تحديد المسار الصحيح لدليل المستندات الذي يحتوي على الملف`Hyperlinks.docx` ملف.

## الخطوة 2: قم بتحميل المستند الذي يحتوي على الارتباطات التشعبية

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 نحن هنا نقوم بإنشاء مثيل لـ`Document` فئة من الملف المحدد.

## الخطوة 3: تصفح الحقول للعثور على الارتباطات التشعبية

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // قد تكون بعض الارتباطات التشعبية محلية (روابط إلى إشارات مرجعية داخل المستند)، فنتجاهلها.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 تمر هذه الحلقة بجميع الحقول الموجودة في المستند بحثًا عن حقول النوع`FieldType.FieldHyperlink` . بمجرد العثور على حقل من هذا النوع، نتحقق مما إذا كان رابطًا محليًا عن طريق التحقق من`SubAddress` ملكية. إذا لم يكن الأمر كذلك، فإننا نستبدل عنوان الرابط بـ`"http://www.aspose.com"` والنتيجة مع`"Aspose - The .NET & Java Component Editor"`.

## الخطوة 4: احفظ المستند المعدل

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

وأخيرًا، نقوم بحفظ المستند المعدل مع الارتباطات التشعبية المستبدلة إلى ملف محدد.

### مثال على التعليمات البرمجية المصدر لاستبدال الارتباطات التشعبية بـ Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // قد تكون بعض الارتباطات التشعبية محلية (روابط إلى إشارات مرجعية داخل المستند)، فنتجاهلها.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

هذا هو نموذج التعليمات البرمجية المصدر لاستبدال الارتباطات التشعبية في مستند يستخدم Aspose.Words لـ .NET.

### الأسئلة الشائعة

#### س: كيف يمكنني استبدال الارتباطات التشعبية في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: لاستبدال الارتباطات التشعبية في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام`Document.Range.Replace`طريقة تحديد النص المطلوب البحث عنه والنص البديل. تأكد من استخدام الخيارات المناسبة لتعيين معلمات البحث والاستبدال.

#### س: هل من الممكن استبدال ارتباطات تشعبية معينة فقط في مستند Word بـ Aspose.Words لـ .NET؟

ج: نعم، من الممكن استبدال ارتباطات تشعبية معينة فقط في مستند Word بـ Aspose.Words لـ .NET. يمكنك تصفية الارتباطات التشعبية المراد استبدالها باستخدام معايير محددة، مثل عنوان URL للارتباط أو نص الارتباط أو أي خاصية أخرى ذات صلة. ومن ثم يمكنك تطبيق الاستبدال على الارتباطات التشعبية المطابقة فقط.

#### س: كيف يمكنني تجاهل الارتباطات التشعبية في الرؤوس أو التذييلات أو الحواشي السفلية عند الاستبدال بـ Aspose.Words لـ .NET؟

ج: لتجاهل الارتباطات التشعبية في الرؤوس أو التذييلات أو الحواشي السفلية عند الاستبدال بـ Aspose.Words لـ .NET، يمكنك استخدام خيارات البحث المتقدم وتحديد حدود البحث المناسبة. على سبيل المثال، يمكنك قصر البحث على الأقسام الرئيسية من المستند واستبعاد الرؤوس أو التذييلات أو الحواشي السفلية.

#### س: هل من الممكن استبدال الارتباطات التشعبية بروابط داخلية لأجزاء أخرى من المستند؟

 ج: نعم، من الممكن استبدال الارتباطات التشعبية بروابط داخلية لأجزاء أخرى من المستند باستخدام Aspose.Words لـ .NET. يمكنك استخدام نقاط الارتساء أو المعرفات النصية لإنشاء روابط داخلية ثم استبدالها باستخدام`Document.Range.Replace` الطريقة مع الخيارات المناسبة

#### س: هل يؤدي استبدال الارتباطات التشعبية بـ Aspose.Words لـ .NET إلى الحفاظ على خصائص الارتباط، مثل الألوان أو الأنماط؟

ج: نعم، عند استبدال الارتباطات التشعبية بـ Aspose.Words لـ .NET، يتم الاحتفاظ بخصائص الارتباط مثل الألوان أو الأنماط. يمكنك تحديد نفس خصائص التنسيق في النص البديل لتحقيق نتيجة متسقة.
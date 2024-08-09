---
title: أضف بادئة اسم فئة Css
linktitle: أضف بادئة اسم فئة Css
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة بادئة اسم فئة CSS عند حفظ مستندات Word بتنسيق HTML باستخدام Aspose.Words لـ .NET. تم تضمين دليل خطوة بخطوة ومقتطفات التعليمات البرمجية والأسئلة الشائعة.
type: docs
weight: 10
url: /ar/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## مقدمة

مرحباً! إذا كنت تغوص في عالم Aspose.Words for .NET، فأنت في مكان رائع. سنستكشف اليوم كيفية إضافة بادئة اسم فئة CSS عند حفظ مستند Word بتنسيق HTML باستخدام Aspose.Words لـ .NET. تعد هذه الميزة مفيدة للغاية عندما تريد تجنب تعارضات أسماء الفئات في ملفات HTML الخاصة بك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

-  Aspose.Words for .NET: إذا لم تقم بتثبيته بعد،[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
- بيئة التطوير: Visual Studio أو أي C# IDE آخر.
-  مستند Word: سنستخدم مستندًا اسمه`Rendering.docx`. ضعه في دليل المشروع الخاص بك.

## استيراد مساحات الأسماء

أولاً، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. أضف هذه في أعلى ملف التعليمات البرمجية الخاص بك:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

الآن، دعونا نتعمق في الدليل خطوة بخطوة!

## الخطوة 1: قم بإعداد مشروعك

قبل أن نتمكن من البدء بإضافة بادئة اسم فئة CSS، فلنقم بإعداد مشروعنا.

### الخطوة 1.1: إنشاء مشروع جديد

 قم بتشغيل Visual Studio الخاص بك وقم بإنشاء مشروع تطبيق Console جديد. سمها شيئًا جذابًا مثل`AsposeCssPrefixExample`.

### الخطوة 1.2: إضافة Aspose.Words لـ .NET

إذا لم تكن قد قمت بذلك بالفعل، قم بإضافة Aspose.Words for .NET إلى مشروعك عبر NuGet. ما عليك سوى فتح وحدة تحكم NuGet Package Manager وتشغيلها:

```bash
Install-Package Aspose.Words
```

عظيم! الآن، نحن جاهزون لبدء البرمجة.

## الخطوة 2: قم بتحميل المستند الخاص بك

أول شيء يتعين علينا القيام به هو تحميل مستند Word الذي نريد تحويله إلى HTML.

### الخطوة 2.1: تحديد مسار المستند

 قم بإعداد المسار إلى دليل المستندات الخاص بك. من أجل هذا البرنامج التعليمي، لنفترض أن المستند الخاص بك موجود في مجلد اسمه`Documents` ضمن دليل المشروع الخاص بك.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### الخطوة 2.2: قم بتحميل المستند

الآن، لنقم بتحميل المستند باستخدام Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تكوين خيارات حفظ HTML

بعد ذلك، نحتاج إلى تكوين خيارات حفظ HTML لتضمين بادئة اسم فئة CSS.

### الخطوة 3.1: إنشاء خيارات حفظ HTML

 إنشاء مثيل`HtmlSaveOptions` كائن وقم بتعيين نوع ورقة أنماط CSS عليه`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### الخطوة 3.2: تعيين بادئة اسم فئة CSS

 الآن، دعونا نضع`CssClassNamePrefix` الخاصية إلى البادئة التي تريدها. في هذا المثال سوف نستخدم`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## الخطوة 4: احفظ المستند بتنسيق HTML

وأخيرًا، فلنحفظ المستند كملف HTML مع خياراتنا التي تم تكوينها.


حدد مسار ملف HTML الناتج واحفظ المستند.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## الخطوة 5: التحقق من الإخراج

 بعد تشغيل مشروعك، انتقل إلى ملف`Documents` المجلد. يجب أن تجد ملف HTML اسمه`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . افتح هذا الملف في محرر نصوص أو متصفح للتحقق من أن فئات CSS لها البادئة`pfx_`.

## خاتمة

وهنا لديك! باتباع هذه الخطوات، تكون قد قمت بنجاح بإضافة بادئة اسم فئة CSS إلى مخرجات HTML الخاصة بك باستخدام Aspose.Words for .NET. يمكن أن تساعدك هذه الميزة البسيطة والقوية في الحفاظ على أنماط نظيفة وخالية من التعارضات في مستندات HTML الخاصة بك.

## الأسئلة الشائعة

### هل يمكنني استخدام بادئة مختلفة لكل عملية حفظ؟
 نعم، يمكنك تخصيص البادئة في كل مرة تقوم فيها بحفظ مستند عن طريق تغيير`CssClassNamePrefix` ملكية.

### هل تدعم هذه الطريقة CSS المضمنة؟
 ال`CssClassNamePrefix`الخاصية تعمل مع CSS خارجي. بالنسبة إلى CSS المضمنة، ستحتاج إلى أسلوب مختلف.

### كيف يمكنني تضمين خيارات حفظ HTML أخرى؟
 يمكنك تكوين خصائص مختلفة`HtmlSaveOptions` لتخصيص مخرجات HTML الخاصة بك. تحقق من[الوثائق](https://reference.aspose.com/words/net/) لمزيد من التفاصيل.

### هل من الممكن حفظ HTML في الدفق؟
 قطعاً! يمكنك حفظ المستند في دفق عن طريق تمرير كائن الدفق إلى ملف`Save` طريقة.

### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
 يمكنك الحصول على الدعم من[منتدى Aspose](https://forum.aspose.com/c/words/8).
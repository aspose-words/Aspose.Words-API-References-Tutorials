---
title: احصل على قائمة الخطوط المتاحة
linktitle: احصل على قائمة الخطوط المتاحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: اكتشف كيفية الحصول على قائمة بالخطوط المتوفرة باستخدام Aspose.Words for .NET في هذا البرنامج التعليمي المفصل خطوة بخطوة. تعزيز مهارات إدارة الخطوط الخاصة بك.
type: docs
weight: 10
url: /ar/net/working-with-fonts/get-list-of-available-fonts/
---
## مقدمة

هل وجدت نفسك تكافح من أجل إدارة الخطوط في مستندات Word الخاصة بك؟ إذا كنت أحد مطوري .NET، فإن Aspose.Words for .NET موجود هنا لإنقاذك! لا تساعدك هذه المكتبة القوية على إنشاء مستندات Word ومعالجتها برمجيًا فحسب، بل توفر أيضًا إمكانات واسعة لإدارة الخطوط. في هذا الدليل، سنوجهك عبر برنامج تعليمي خطوة بخطوة حول كيفية الحصول على قائمة بالخطوط المتاحة باستخدام Aspose.Words for .NET. سنقوم بتقسيمها إلى خطوات سهلة الهضم للتأكد من أنه يمكنك المتابعة بسهولة. لذلك، دعونا نتعمق ونجعل إدارة الخطوط أمرًا سهلاً!

## المتطلبات الأساسية

قبل أن نبدأ، هناك بعض الأشياء التي ستحتاج إليها:

-  Aspose.Words for .NET: تأكد من تثبيت مكتبة Aspose.Words for .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).
- Visual Studio: يستخدم هذا المثال Visual Studio كبيئة التطوير.
- .NET Framework: تأكد من تثبيت .NET Framework على جهازك.
- دليل المستندات: مسار الدليل حيث يتم تخزين المستندات الخاصة بك.

## استيراد مساحات الأسماء

أولاً، قم باستيراد مساحات الأسماء الضرورية إلى مشروعك:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## الخطوة 1: تهيئة إعدادات الخط

الخطوة الأولى هي تهيئة إعدادات الخط. سيسمح لك هذا بإدارة مصادر الخطوط لمستنداتك.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- إعدادات الخط: يتم استخدام هذه الفئة لتحديد إعدادات استبدال الخط ومصادر الخطوط.
- FontSources: نقوم بإنشاء قائمة بمصادر الخطوط الموجودة من إعدادات الخط الحالية.

## الخطوة 2: تحديد دليل المستندات

بعد ذلك، حدد المسار إلى دليل المستند الخاص بك. هذا هو المكان الذي سيبحث فيه Aspose.Words عن الخطوط.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: يحمل متغير السلسلة هذا المسار إلى الدليل الذي توجد به الخطوط الخاصة بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي

## الخطوة 3: إضافة مجلد الخط المخصص

الآن، قم بإضافة مصدر مجلد جديد لتوجيه Aspose.Words للبحث في هذا المجلد عن الخطوط.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: تمثل هذه الفئة مصدر خط المجلد. المعلمة الثانية (`true`) يشير إلى ما إذا كان سيتم البحث عن الخطوط بشكل متكرر في المجلدات الفرعية.

## الخطوة 4: تحديث مصادر الخطوط

أضف مجلد الخط المخصص إلى قائمة مصادر الخطوط الموجودة وقم بتحديث إعدادات الخط.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- FontSources.Add(folderFontSource): يضيف مجلد الخط المخصص إلى مصادر الخطوط الموجودة.
- updateFontSources: تحويل قائمة مصادر الخطوط إلى مصفوفة.

## الخطوة 5: استرداد الخطوط وعرضها

وأخيرًا، قم باسترجاع الخطوط المتوفرة وعرض تفاصيلها.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): استرداد قائمة الخطوط المتوفرة من مصدر الخط الأول في القائمة المحدثة.
-  معلومات الخط: مثال على`PhysicalFontInfo` تحتوي على تفاصيل حول كل خط.

## خاتمة

تهانينا! لقد نجحت في استرداد قائمة الخطوط المتوفرة باستخدام Aspose.Words لـ .NET. يرشدك هذا البرنامج التعليمي خلال كل خطوة، بدءًا من تهيئة إعدادات الخط وحتى عرض تفاصيل الخط. بفضل هذه المعرفة، يمكنك الآن إدارة الخطوط في مستندات Word الخاصة بك بسهولة. تذكر أن Aspose.Words for .NET هي أداة قوية يمكنها تحسين قدرات معالجة المستندات لديك بشكل كبير. لذا، تابع واستكشف المزيد من الميزات لجعل عملية التطوير الخاصة بك أكثر كفاءة.

## الأسئلة الشائعة

### هل يمكنني استخدام Aspose.Words لـ .NET مع أطر عمل .NET الأخرى؟
نعم، Aspose.Words for .NET متوافق مع أطر عمل .NET المختلفة بما في ذلك .NET Core و.NET 5+.

### كيف أقوم بتثبيت Aspose.Words لـ .NET؟
يمكنك تثبيته عبر NuGet Package Manager في Visual Studio من خلال البحث عن "Aspose.Words".

### هل من الممكن إضافة مجلدات خطوط مخصصة متعددة؟
 نعم، يمكنك إضافة عدة مجلدات خطوط مخصصة عن طريق إنشاء عدة مجلدات`FolderFontSource` المثيلات وإضافتها إلى قائمة مصادر الخطوط.

### هل يمكنني استرداد تفاصيل الخط من مصدر خط محدد؟
 نعم، يمكنك استرجاع تفاصيل الخط من أي مصدر خط عن طريق تحديد فهرس مصدر الخط في ملف`updatedFontSources` صفيف.

### هل يدعم Aspose.Words for .NET استبدال الخطوط؟
نعم، فهو يدعم استبدال الخط لضمان عرض النص بشكل صحيح حتى في حالة عدم توفر الخط الأصلي.
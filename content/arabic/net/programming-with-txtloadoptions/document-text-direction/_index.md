---
title: اتجاه نص الوثيقة
linktitle: اتجاه نص الوثيقة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين اتجاه نص المستند في Word باستخدام Aspose.Words لـ .NET باستخدام هذا الدليل التفصيلي خطوة بخطوة. مثالية للتعامل مع اللغات ذات الاتجاه من اليمين إلى اليسار.
type: docs
weight: 10
url: /ar/net/programming-with-txtloadoptions/document-text-direction/
---
## مقدمة

عند العمل مع مستندات Word، خاصة تلك التي تحتوي على لغات متعددة أو احتياجات تنسيق خاصة، يمكن أن يكون تحديد اتجاه النص أمرًا بالغ الأهمية. على سبيل المثال، عند التعامل مع اللغات التي تكتب من اليمين إلى اليسار مثل العبرية أو العربية، قد تحتاج إلى ضبط اتجاه النص وفقًا لذلك. في هذا الدليل، سنتعرف على كيفية تعيين اتجاه نص المستند باستخدام Aspose.Words for .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من أن لديك ما يلي:

-  Aspose.Words لـ .NET Library: تأكد من تثبيت Aspose.Words لـ .NET. يمكنك تنزيله من[موقع أسبوز](https://releases.aspose.com/words/net/).
- Visual Studio: بيئة تطوير لكتابة وتنفيذ تعليمات برمجية C#.
- المعرفة الأساسية بـ C#: الإلمام ببرمجة C# سيكون مفيدًا لأننا سنكتب بعض الأكواد البرمجية.

## استيراد مساحات الأسماء

للبدء، ستحتاج إلى استيراد مساحات الأسماء اللازمة للعمل مع Aspose.Words في مشروعك. وإليك كيف يمكنك القيام بذلك:

```csharp
using Aspose.Words;
using Aspose.Words.Loading;
```

توفر مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب اللازمة لمعالجة مستندات Word.

## الخطوة 1: تحديد المسار إلى دليل المستندات الخاص بك

أولاً، قم بإعداد المسار إلى حيث يوجد المستند الخاص بك. يعد هذا أمرًا بالغ الأهمية لتحميل الملفات وحفظها بشكل صحيح.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي حيث تم تخزين المستند الخاص بك.

## الخطوة 2: إنشاء TxtLoadOptions مع إعداد اتجاه المستند

 بعد ذلك، ستحتاج إلى إنشاء مثيل لـ`TxtLoadOptions` وتعيينها`DocumentDirection` ملكية. يوضح هذا لـ Aspose.Words كيفية التعامل مع اتجاه النص في المستند.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };
```

 في هذا المثال نستخدم`DocumentDirection.Auto` للسماح لـ Aspose.Words بتحديد الاتجاه تلقائيًا بناءً على المحتوى.

## الخطوة 3: قم بتحميل المستند

 الآن قم بتحميل المستند باستخدام`Document` الطبقة والمحددة سابقا`loadOptions`.

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 هنا،`"Hebrew text.txt"` هو اسم الملف النصي الخاص بك. تأكد من وجود هذا الملف في الدليل المحدد الخاص بك.

## الخطوة 4: الوصول إلى التنسيق ثنائي الاتجاه للفقرة والتحقق منه

للتأكد من ضبط اتجاه النص بشكل صحيح، قم بالوصول إلى الفقرة الأولى من المستند وتحقق من تنسيقها ثنائي الاتجاه.

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

تعتبر هذه الخطوة مفيدة لتصحيح الأخطاء والتحقق من تطبيق اتجاه نص المستند كما هو متوقع.

## الخطوة 5: احفظ المستند بالإعدادات الجديدة

وأخيرًا، احفظ المستند لتطبيق التغييرات والاستمرار فيها.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 هنا،`"WorkingWithTxtLoadOptions.DocumentTextDirection.docx"` هو اسم ملف الإخراج. تأكد من اختيار اسم يعكس التغييرات التي أجريتها.

## خاتمة

يعد تعيين اتجاه النص في مستندات Word عملية مباشرة مع Aspose.Words لـ .NET. باتباع هذه الخطوات، يمكنك بسهولة تكوين كيفية تعامل مستندك مع النص من اليمين إلى اليسار أو من اليسار إلى اليمين. سواء كنت تعمل مع مستندات متعددة اللغات أو تحتاج إلى تنسيق اتجاه النص للغات معينة، فإن Aspose.Words يوفر حلاً قويًا لتلبية احتياجاتك.

## الأسئلة الشائعة

###  ما هو`DocumentDirection` property used for?

 ال`DocumentDirection` الممتلكات في`TxtLoadOptions` يحدد اتجاه النص للمستند. يمكن ضبطه على`DocumentDirection.Auto`, `DocumentDirection.LeftToRight` ، أو`DocumentDirection.RightToLeft`.

### هل يمكنني ضبط اتجاه النص لفقرات محددة بدلاً من المستند بأكمله؟

 نعم، يمكنك ضبط اتجاه النص لفقرات معينة باستخدام`ParagraphFormat.Bidi` الملكية، ولكن`TxtLoadOptions.DocumentDirection` تحدد الخاصية الاتجاه الافتراضي للمستند بأكمله.

###  ما هي تنسيقات الملفات المدعومة للتحميل`TxtLoadOptions`?

`TxtLoadOptions` يُستخدم بشكل أساسي لتحميل الملفات النصية (.txt). بالنسبة لتنسيقات الملفات الأخرى، استخدم فئات مختلفة مثل`DocLoadOptions` أو`DocxLoadOptions`.

### كيف يمكنني التعامل مع المستندات ذات الاتجاهات النصية المختلطة؟

 بالنسبة للمستندات ذات الاتجاهات النصية المختلطة، قد تحتاج إلى التعامل مع التنسيق على أساس كل فقرة. استخدم`ParagraphFormat.Bidi` الخاصية لضبط اتجاه كل فقرة حسب الحاجة.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Words لـ .NET؟

 لمزيد من التفاصيل، راجع[Aspose.Words للتوثيق .NET](https://reference.aspose.com/words/net/) . يمكنك أيضًا استكشاف موارد إضافية مثل[رابط التحميل](https://releases.aspose.com/words/net/), [يشتري](https://purchase.aspose.com/buy), [تجربة مجانية](https://releases.aspose.com/), [ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) ، و[يدعم](https://forum.aspose.com/c/words/8).
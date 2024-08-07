---
title: تعيين مجلدات الخطوط
linktitle: تعيين مجلدات الخطوط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين مجلدات الخطوط المخصصة في Aspose.Words لـ .NET باستخدام هذا الدليل الشامل خطوة بخطوة. مثالي للمطورين الذين يتطلعون إلى تحسين خطوط المستندات.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-fonts-folders/
---
## مقدمة

مرحبًا يا من هناك! هل أنت مستعد للتعمق في عالم الخطوط المخصصة في Aspose.Words لـ .NET؟ دعونا نبدأ. سيرشدك هذا البرنامج التعليمي خلال عملية إعداد مجلدات الخطوط المخصصة، مما يضمن ظهور مستنداتك بالطريقة التي تريدها تمامًا. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيرشدك هذا الدليل خلال كل خطوة. لذلك، دعونا نجعل تلك الخطوط تبدو رائعة!

## المتطلبات الأساسية

قبل أن نبدأ، دعونا نتأكد من أن لديك كل ما تحتاجه:

-  Aspose.Words لـ .NET: يمكنك ذلك[تحميل](https://releases.aspose.com/words/net/) إذا لم تكن قد فعلت ذلك بالفعل.
- Visual Studio: أي إصدار سيعمل، ولكن الأحدث هو الأفضل دائمًا.
- مستند: سنستخدم مستند Word لهذا البرنامج التعليمي. يمكنك إنشاء واحدة خاصة بك أو استخدام واحدة موجودة.
- الخطوط المخصصة: جهز بعض الخطوط المخصصة. سنستخدم هذه لتوضيح كيفية تعيين مجلدات الخطوط.

## استيراد مساحات الأسماء

أول الأشياء أولاً، فلنستورد مساحات الأسماء الضرورية. يعد هذا ضروريًا للوصول إلى الفئات والأساليب التي نحتاجها من Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

بعد استيراد مساحات الأسماء هذه، أصبحنا جاهزين لبدء إعداد مجلدات الخطوط المخصصة لدينا.

## الخطوة 1: تحديد دليل المستندات الخاص بك

 لنبدأ بتحديد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي يتم فيه تخزين مستند Word الخاص بك. سوف نستخدم متغير يسمى`dataDir` لتخزين هذا المسار.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى الدليل الخاص بك. يعد هذا أمرًا بالغ الأهمية لأن Aspose.Words سيحتاج إلى معرفة مكان العثور على المستند الخاص بك.

## الخطوة 2: تعيين مصادر الخطوط

 بعد ذلك، نحتاج إلى إعداد مصادر الخطوط. هذا هو المكان الذي نخبر فيه Aspose.Words بمكان العثور على الخطوط المخصصة لدينا. نحن ذاهبون لاستخدام`FontSettings.DefaultInstance.SetFontsSources` طريقة لتحقيق ذلك.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
```

وإليك ما نقوم به:

- SystemFontSource: هذا يخبر Aspose.Words باستخدام الخطوط الافتراضية للنظام.
-  FolderFontSource: هذا هو المكان الذي نحدد فيه المجلد الذي يحتوي على الخطوط المخصصة لدينا. يستبدل`"C:\\MyFonts\\"` مع المسار إلى دليل الخطوط المخصصة الخاصة بك. ال`true` تشير المعلمة إلى أنه يجب أيضًا تضمين الدلائل الفرعية.

## الخطوة 3: قم بتحميل المستند الخاص بك

الآن بعد أن قمنا بإعداد مصادر الخطوط، حان الوقت لتحميل المستند الذي نريد العمل معه. سوف نستخدم`Document` فئة من Aspose.Words لهذا الغرض.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 تأكد من ذلك`"Rendering.docx"` هو اسم مستند Word الخاص بك. إذا كان للمستند اسم مختلف، فتأكد من تحديثه وفقًا لذلك.

## الخطوة 4: احفظ المستند الخاص بك بصيغة PDF

 أخيرًا، دعونا نحفظ مستندنا كملف PDF لرؤية الخطوط المخصصة أثناء العمل. سوف نستخدم`Save` طريقة`Document` فصل.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

سيؤدي هذا إلى حفظ المستند الخاص بك كملف PDF في الدليل المحدد، باستخدام الخطوط المخصصة التي قمنا بإعدادها مسبقًا.

## خاتمة

وهنا لديك! لقد قمت بنجاح بإعداد مجلدات الخطوط المخصصة في Aspose.Words لـ .NET وحفظت مستندك كملف PDF بهذه الخطوط المخصصة. رائع، أليس كذلك؟ تخصيص الخطوط يمكن أن يحدث فرقًا كبيرًا في مظهر مستنداتك، والآن أنت تعرف بالضبط كيفية القيام بذلك. ترميز سعيد!

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Words لـ .NET؟

 أنت تستطيع[تحميل](https://releases.aspose.com/words/net/) أحدث إصدار من Aspose.Words for .NET من الموقع.

### هل يمكنني استخدام مجلدات خطوط مخصصة متعددة؟

 نعم، يمكنك إضافة عدة`FolderFontSource` الحالات إلى`SetFontsSources`طريقة لاستخدام الخطوط من الدلائل المختلفة.

### هل من الضروري تضمين خطوط النظام؟

يعد تضمين خطوط النظام أمرًا اختياريًا ولكن يوصى به لضمان توفر جميع الخطوط القياسية.

### ما أنواع الملفات التي يدعمها Aspose.Words؟

يدعم Aspose.Words مجموعة واسعة من تنسيقات الملفات، بما في ذلك DOCX وDOC وPDF وTXT وHTML وغيرها الكثير.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words؟

 يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) من موقع Aspose الإلكتروني لتجربة الميزات الكاملة لـ Aspose.Words.
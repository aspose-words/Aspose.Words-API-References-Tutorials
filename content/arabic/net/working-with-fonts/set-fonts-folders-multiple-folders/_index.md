---
title: تعيين مجلدات الخطوط ومجلدات متعددة
linktitle: تعيين مجلدات الخطوط ومجلدات متعددة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين مجلدات خطوط متعددة في مستندات Word الخاصة بك باستخدام Aspose.Words لـ .NET. يضمن هذا الدليل المفصّل خطوة بخطوة أن تستخدم مستنداتك الخطوط الدقيقة التي تحتاجها.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-fonts-folders-multiple-folders/
---
## مقدمة

هل تساءلت يومًا عن كيفية إدارة مصادر الخطوط المتعددة في مستندات Word الخاصة بك؟ ربما لديك مجموعة من الخطوط المنتشرة في مجلدات مختلفة، وتحتاج إلى طريقة للتأكد من أن مستنداتك تستخدمها بسلاسة. حسنًا، أنت محظوظ! اليوم، سنتعمق في كيفية تعيين مجلدات الخطوط باستخدام Aspose.Words لـ .NET. سيأخذك هذا الدليل خطوة بخطوة خلال العملية، مما يضمن ظهور مستنداتك بالطريقة التي تريدها تمامًا.

## المتطلبات الأساسية

قبل أن نبدأ، دعونا نتأكد من أن لديك كل ما تحتاجه. إليك ما ستحتاج إلى متابعته:

-  Aspose.Words for .NET: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيل Aspose.Words for .NET وتثبيته. يمكنك الحصول عليه[هنا](https://releases.aspose.com/words/net/).
- بيئة التطوير: Visual Studio أو أي بيئة تطوير أخرى متوافقة مع .NET.
- المعرفة الأساسية بـ C#: القليل من الإلمام بـ C# سيساعدك على اتباع الأمثلة.
- ملفات الخطوط: تأكد من تخزين ملفات الخطوط الخاصة بك في الأدلة التي يمكنك الوصول إليها بسهولة.

## استيراد مساحات الأسماء

أول الأشياء أولاً، فلنستورد مساحات الأسماء الضرورية في مشروع C# الخاص بك. وهذا يضمن لك الوصول إلى جميع وظائف Aspose.Words التي ستحتاج إليها.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

باستخدام هذه المجموعة، دعنا نتعمق في الدليل خطوة بخطوة لتعيين مجلدات الخطوط في Aspose.Words لـ .NET.

## الخطوة 1: قم بتحميل المستند الخاص بك

حسنًا، لنبدأ بتحميل مستند Word الذي تريد العمل معه. تأكد من أن مسار المستند جاهز. في هذا المثال، سنستخدم مستندًا باسم "Rendering.docx".

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

هنا نقوم بتحميل المستند من الدليل المحدد. بسيطة بما فيه الكفاية، أليس كذلك؟

## الخطوة 2: إنشاء كائن FontSettings

 بعد ذلك، نحن بحاجة إلى إنشاء`FontSettings` هدف. سيسمح لنا هذا الكائن بإدارة مصادر الخطوط في وثيقتنا.

```csharp
FontSettings fontSettings = new FontSettings();
```

 هذا`FontSettings`سيساعدنا الكائن في تحديد مجلدات الخطوط التي يجب استخدامها.

## الخطوة 3: تعيين مجلدات الخطوط

الآن يأتي الجزء الحاسم – تعيين مجلدات الخطوط. هذا هو المكان الذي تحدد فيه الدلائل التي توجد بها الخطوط الخاصة بك. في هذا المثال، لدينا خطوط في "C:\MyFonts\" و"D:\Misc\Fonts\".

```csharp
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

المعلمة الثانية (`true` ) يشير إلى أن هذه المجلدات ستتجاوز أي مصادر خطوط افتراضية. إذا كنت تريد الاحتفاظ بمصادر خطوط النظام أيضًا، فيمكنك استخدام مجموعة من`GetFontSources`و`SetFontSources`.

## الخطوة 4: تطبيق إعدادات الخط على المستند

مع مجموعة مجلدات الخطوط، نحتاج إلى تطبيق هذه الإعدادات على مستندنا. وهذا يضمن أن المستند يستخدم الخطوط المحددة أثناء العرض.

```csharp
doc.FontSettings = fontSettings;
```

## الخطوة 5: احفظ المستند

أخيرًا، لنحفظ المستند. سنقوم بحفظه كملف PDF لرؤية الخطوط أثناء العمل.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

وهنا لديك! لقد قمت بنجاح بتعيين مجلدات خطوط متعددة للمستند الخاص بك.

## خاتمة

قد تبدو إدارة الخطوط في مستنداتك مهمة شاقة، ولكن مع Aspose.Words for .NET، أصبح الأمر سهلاً للغاية! باتباع هذه الخطوات البسيطة، يمكنك التأكد من أن مستنداتك تبدو احترافية وتستخدم الخطوط الدقيقة التي تحتاجها. سواء كنت تعمل على مشروع يتطلب علامة تجارية محددة أو تريد فقط مزيدًا من التحكم في مظهر مستندك، فإن تعيين مجلدات الخطوط يعد مهارة تستحق إتقانها.

## الأسئلة الشائعة

### هل يمكنني استخدام مسارات الشبكة لمجلدات الخطوط؟
نعم، يمكنك استخدام مسارات الشبكة لمجلدات الخطوط الخاصة بك. فقط تأكد من إمكانية الوصول إلى المسارات من التطبيق الخاص بك.

### ماذا يحدث إذا كان الخط مفقودًا في المجلدات المحددة؟
إذا كان الخط مفقودًا، فسيعود Aspose.Words إلى الخط الافتراضي المحدد أو يستخدم خطًا بديلاً.

### هل يمكنني إضافة مجلدات الخطوط دون تجاوز خطوط النظام؟
 قطعاً! يستخدم`FontSettings.GetFontSources` لاسترداد المصادر الموجودة ودمجها مع مجلداتك المخصصة باستخدام`FontSettings.SetFontSources`.

### هل هناك حد لعدد مجلدات الخطوط التي يمكنني إضافتها؟
لا يوجد حد صارم لعدد مجلدات الخطوط. ومع ذلك، ضع في اعتبارك الأداء، حيث أن زيادة المجلدات قد يؤدي إلى زيادة أوقات تحميل الخط.

### كيف يمكنني التحقق من الخطوط المستخدمة في المستند الخاص بي؟
 يمكنك استخدام`FontSettings.GetFontsSources` طريقة لاسترداد وفحص مصادر الخطوط المعينة حاليًا للمستند الخاص بك.
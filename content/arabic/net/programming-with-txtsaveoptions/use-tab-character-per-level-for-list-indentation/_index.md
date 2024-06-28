---
title: استخدم حرف الجدولة لكل مستوى للمسافة البادئة للقائمة
linktitle: استخدم حرف الجدولة لكل مستوى للمسافة البادئة للقائمة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام قوائم المسافات البادئة مع ميزة أحرف الجدولة في Aspose.Words for .NET. يمكنك توفير الوقت وتحسين سير عملك باستخدام هذه الميزة القوية.
type: docs
weight: 10
url: /ar/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

في هذا البرنامج التعليمي، سوف نستكشف التعليمات البرمجية المصدر لـ C# المتوفرة لميزة "استخدام حرف علامة تبويب واحد لكل مستوى للمسافة البادئة للقائمة" مع Aspose.Words for .NET. تسمح لك هذه الميزة بتطبيق أحرف الجدولة لوضع مسافة بادئة للقوائم على كل مستوى، مما يوفر قدرًا أكبر من المرونة والتحكم في مظهر مستنداتك.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: إنشاء المستند والمولد

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

في هذه الخطوة نقوم بإنشاء جديد`Document` الكائن وما يرتبط به`DocumentBuilder` هدف. ستسمح لنا هذه الكائنات بمعالجة وثيقتنا وإنشائها.

## الخطوة 3: إنشاء قائمة بثلاثة مستويات من المسافة البادئة

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

في هذه الخطوة، نقوم بتطبيق التنسيق الافتراضي لأرقام القائمة باستخدام`ApplyNumberDefault()` طريقة تنسيق القائمة. بعد ذلك، نضيف ثلاثة عناصر إلى قائمتنا باستخدام أداة إنشاء المستندات`Writeln()` و`Write()` طُرق. نحن نستخدم ال`ListIndent()` طريقة زيادة المسافة البادئة على كل مستوى.

## الخطوة 4: تكوين خيارات التسجيل

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 في هذه الخطوة، نقوم بتكوين الخيارات لحفظ المستند. نحن نخلق جديدا`TxtSaveOptions` الكائن وتعيين`ListIndentation.Count` الخاصية إلى 1 لتحديد عدد أحرف الجدولة لكل مستوى مسافة بادئة. قمنا أيضًا بتعيين`ListIndentation.Character` الخاصية إلى '\t' لتحديد أننا نريد استخدام أحرف الجدولة.

## الخطوة 5: احفظ المستند

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 في هذه الخطوة الأخيرة، نقوم بحفظ المستند باستخدام خيارات الحفظ المحددة. نحن نستخدم ال`Save()` طريقة تمرير المستند للمسار الكامل لملف الإخراج وخيارات الحفظ.


يمكنك الآن تشغيل التعليمات البرمجية المصدر لإنشاء مستند به مسافة بادئة للقائمة باستخدام أحرف الجدولة. سيتم حفظ ملف الإخراج في الدليل المحدد بالاسم "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt".

### مثال لمصدر التعليمات البرمجية لميزة استخدام حرف علامة تبويب واحد لكل مستوى لميزة المسافة البادئة للقائمة باستخدام Aspose.Words لـ .NET:

```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء قائمة بثلاثة مستويات من المسافة البادئة
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

الآن بعد أن انتهيت من إنشاء المستند الخاص بك مع المسافة البادئة للقائمة باستخدام أحرف الجدولة، يمكنك استخدام Markdown لتنسيق محتوى مقالتك. تأكد من استخدام علامات التنسيق المناسبة لتسليط الضوء على العناوين والعناوين الفرعية وكود المصدر المضمن.

### أسئلة مكررة

#### س: ما هي ميزة "استخدام حرف علامة تبويب واحد لكل مستوى للمسافة البادئة للقائمة" مع Aspose.Words for .NET؟
تسمح ميزة "استخدام حرف علامة تبويب واحد لكل مستوى للمسافة البادئة للقائمة" مع Aspose.Words لـ .NET بتطبيق أحرف الجدولة للمسافة البادئة للقائمة على كل مستوى. وهذا يوفر قدرًا أكبر من المرونة والتحكم في مظهر مستنداتك.

#### س: كيف يمكنني استخدام هذه الميزة مع Aspose.Words لـ .NET؟
لاستخدام هذه الميزة مع Aspose.Words for .NET، يمكنك اتباع الخطوات التالية:

قم بإعداد بيئة التطوير الخاصة بك عن طريق إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

 إنشاء جديد`Document` الكائن وما يرتبط به`DocumentBuilder` هدف.

 استخدم ال`DocumentBuilder` لإنشاء قائمة ذات مستويات متعددة من المسافة البادئة باستخدام الطرق`ApplyNumberDefault()` لتطبيق تنسيق رقم القائمة الافتراضي،`Writeln()` و`Write()` لإضافة عناصر إلى القائمة، و`ListIndent()`لزيادة المسافة البادئة على كل مستوى.

 قم بتكوين خيارات الحفظ عن طريق إنشاء ملف`TxtSaveOptions` الكائن وتعيين الخصائص`ListIndentation.Count` إلى عدد أحرف علامة التبويب لكل مستوى و`ListIndentation.Character` ل`'\t'` لاستخدام أحرف علامة التبويب.

 احفظ المستند باستخدام`Save()` طريقة المستند التي تحدد المسار الكامل لملف الإخراج وخيارات الحفظ.

#### س: هل من الممكن تخصيص عدد أحرف علامة التبويب لكل مستوى للمسافة البادئة للقائمة؟
 نعم، يمكنك تخصيص عدد أحرف علامة التبويب لكل مستوى للمسافة البادئة للقائمة عن طريق تغيير قيمة`ListIndentation.Count` الممتلكات في`TxtSaveOptions` فصل. يمكنك تحديد عدد أحرف الجدولة التي تريدها لكل مستوى من المسافة البادئة.

#### س: ما هي الأحرف الأخرى التي يمكنني استخدامها لتحديد المسافة البادئة للقائمة باستخدام Aspose.Words لـ .NET؟
 إلى جانب أحرف علامة التبويب، يمكنك أيضًا استخدام أحرف أخرى للمسافة البادئة للقائمة باستخدام Aspose.Words لـ .NET. يمكنك ضبط`ListIndentation.Character` الخاصية إلى أي حرف مرغوب، مثل المسافة (`' '`)، لتحديد القوائم.

#### س: هل يقدم Aspose.Words for .NET أي ميزات أخرى لإدارة القوائم؟
نعم، يوفر Aspose.Words for .NET العديد من الميزات لإدارة القوائم في مستندات Word. يمكنك إنشاء قوائم مرقمة أو نقطية، وتعيين مستويات المسافة البادئة، وتخصيص نمط القوائم، وإضافة عناصر القائمة، والمزيد.
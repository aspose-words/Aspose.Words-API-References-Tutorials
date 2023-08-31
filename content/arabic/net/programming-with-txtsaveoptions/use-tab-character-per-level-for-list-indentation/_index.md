---
title: استخدم حرف الجدولة لكل مستوى للمسافة البادئة للقائمة
linktitle: استخدم حرف الجدولة لكل مستوى للمسافة البادئة للقائمة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استخدام قوائم المسافات البادئة مع ميزة حروف الجدولة في Aspose.Words for .NET. وفر الوقت وحسّن سير عملك باستخدام هذه الميزة القوية.
type: docs
weight: 10
url: /ar/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

في هذا البرنامج التعليمي ، سوف نستكشف الكود المصدري C # المقدم لميزة "استخدام حرف جدولة واحد لكل مستوى من أجل المسافة البادئة للقائمة" مع Aspose.Words for .NET. تتيح لك هذه الميزة تطبيق أحرف الجدولة لوضع مسافة بادئة للقوائم في كل مستوى ، مما يوفر قدرًا أكبر من المرونة والتحكم في مظهر المستندات الخاصة بك.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة 2: إنشاء المستند والمولد

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 في هذه الخطوة ، نقوم بإنشاء ملف`Document` كائن وما يرتبط بها`DocumentBuilder` هدف. ستسمح لنا هذه الكائنات بمعالجة وإنشاء وثيقتنا.

## الخطوة 3: إنشاء قائمة بثلاثة مستويات من المسافة البادئة

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

في هذه الخطوة ، نطبق التنسيق الافتراضي لأرقام القائمة باستخدام امتداد`ApplyNumberDefault()` طريقة منسق القائمة. بعد ذلك ، نضيف ثلاثة عناصر إلى قائمتنا باستخدام أداة إنشاء المستندات`Writeln()` و`Write()` طُرق. نحن نستخدم ال`ListIndent()` طريقة لزيادة المسافة البادئة في كل مستوى.

## الخطوة 4: تكوين خيارات التسجيل

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 في هذه الخطوة ، نقوم بتهيئة الخيارات لحفظ المستند. نخلق ملف`TxtSaveOptions` كائن وتعيين`ListIndentation.Count` الخاصية إلى 1 لتحديد عدد أحرف الجدولة لكل مستوى مسافة بادئة. قمنا أيضًا بتعيين ملف`ListIndentation.Character` إلى "\ t" لتحديد أننا نريد استخدام أحرف الجدولة.

## الخطوة 5: احفظ المستند

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 في هذه الخطوة الأخيرة ، نقوم بحفظ المستند بخيارات الحفظ المحددة. نحن نستخدم ال`Save()` طريقة المستند التي تمر بالمسار الكامل لملف الإخراج وخيارات الحفظ.


يمكنك الآن تشغيل التعليمات البرمجية المصدر لإنشاء مستند به مسافة بادئة للقائمة باستخدام أحرف الجدولة. سيتم حفظ ملف الإخراج في الدليل المحدد باسم "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt".

### مثال على مصدر التعليمات البرمجية لميزة استخدام حرف جدولة واحد لكل مستوى لميزة المسافة البادئة للقائمة مع Aspose.Words for .NET:

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

الآن بعد أن انتهيت من إنشاء المستند مع المسافة البادئة للقائمة باستخدام أحرف الجدولة ، يمكنك استخدام Markdown لتنسيق محتوى مقالتك. تأكد من استخدام علامات التنسيق المناسبة لتمييز العناوين والعناوين الفرعية وشفرة المصدر المضمنة.

### أسئلة مكررة

#### س: ما هي ميزة "استخدام حرف جدولة واحد لكل مستوى من أجل المسافة البادئة للقائمة" مع Aspose.Words for .NET؟
تتيح ميزة "استخدام حرف جدولة واحدًا لكل مستوى المسافة البادئة للقائمة" مع Aspose.Words for .NET تطبيق أحرف جدولة لمسافة بادئة للقائمة في كل مستوى. يوفر هذا مزيدًا من المرونة والتحكم في مظهر المستندات الخاصة بك.

#### س: كيف يمكنني استخدام هذه الميزة مع Aspose.Words for .NET؟
لاستخدام هذه الميزة مع Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:

قم بإعداد بيئة التطوير الخاصة بك عن طريق إضافة المراجع اللازمة واستيراد مساحات الأسماء المناسبة.

 إنشاء ملف`Document` كائن وما يرتبط بها`DocumentBuilder` هدف.

 استخدم ال`DocumentBuilder` لإنشاء قائمة بمستويات متعددة من المسافة البادئة باستخدام الطرق`ApplyNumberDefault()` لتطبيق تنسيق رقم القائمة الافتراضي ،`Writeln()` و`Write()` لإضافة عناصر إلى القائمة ، و`ListIndent()`لزيادة المسافة البادئة في كل مستوى.

 تكوين خيارات الحفظ عن طريق إنشاء ملف`TxtSaveOptions` الكائن وتحديد الخصائص`ListIndentation.Count` إلى عدد أحرف الجدولة لكل مستوى و`ListIndentation.Character` ل`'\t'` لاستخدام أحرف الجدولة.

 احفظ المستند باستخدام ملف`Save()` طريقة المستند تحدد المسار الكامل لملف الإخراج وخيارات الحفظ.

#### س: هل من الممكن تخصيص عدد أحرف الجدولة لكل مستوى للمسافة البادئة للقائمة؟
 نعم ، يمكنك تخصيص عدد أحرف الجدولة لكل مستوى للمسافة البادئة للقائمة عن طريق تغيير قيمة`ListIndentation.Count` الممتلكات في`TxtSaveOptions` فصل. يمكنك تحديد عدد أحرف الجدولة التي تريدها لكل مستوى من مستويات المسافة البادئة.

#### س: ما هي الأحرف الأخرى التي يمكنني استخدامها للمسافة البادئة للقائمة مع Aspose.Words for .NET؟
 بالإضافة إلى أحرف الجدولة ، يمكنك أيضًا استخدام أحرف أخرى للمسافة البادئة للقائمة باستخدام Aspose.Words for .NET. يمكنك ضبط ملف`ListIndentation.Character` الخاصية لأي حرف مرغوب فيه ، مثل مسافة (`' '`) ، لعمل مسافة بادئة للقوائم.

#### س: هل تقدم Aspose.Words for .NET أية ميزات أخرى لإدارة القوائم؟
نعم ، يوفر Aspose.Words for .NET العديد من الميزات لإدارة القوائم في مستندات Word. يمكنك إنشاء قوائم ذات تعداد رقمي أو نقطي ، وتعيين مستويات المسافة البادئة ، وتخصيص نمط القوائم ، وإضافة عناصر قائمة ، والمزيد.
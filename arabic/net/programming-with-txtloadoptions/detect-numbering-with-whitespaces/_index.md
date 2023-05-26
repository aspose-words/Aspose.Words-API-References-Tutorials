---
title: كشف الترقيم مع المسافات
linktitle: كشف الترقيم مع المسافات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية اكتشاف أرقام القائمة مع وجود مسافات بيضاء في Aspose.Words for .NET. قم بتحسين بنية المستندات الخاصة بك بسهولة.
type: docs
weight: 10
url: /ar/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
في هذا البرنامج التعليمي ، سوف نستكشف الكود المصدري C # المقدم لميزة "اكتشاف الترقيم بمسافات بيضاء" مع Aspose.Words for .NET. تسمح لك هذه الميزة باكتشاف وإنشاء قوائم من مستند نصي يحتوي على أرقام قائمة متبوعة بمسافات بيضاء.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة 2: إنشاء مستند نصي

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

في هذه الخطوة ، نقوم بإنشاء سلسلة نصية تحاكي مستندًا نصيًا يحتوي على أرقام قائمة متبوعة بمسافات بيضاء. نستخدم محددات قائمة مختلفة مثل النقطة والقوس الأيمن ورمز التعداد النقطي والمسافات البيضاء.

## الخطوة 3: تكوين خيارات التحميل

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 في هذه الخطوة ، نقوم بتكوين خيارات تحميل المستند. نخلق ملف`TxtLoadOptions` كائن وتعيين`DetectNumberingWithWhitespaces` ملكية ل`true`. سيسمح هذا لـ Aspose.Words باكتشاف أرقام القائمة حتى لو تبعتها مسافات بيضاء.

## الخطوة 4: تحميل المستند وحفظه

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 في هذه الخطوة ، نقوم بتحميل المستند باستخدام السلسلة النصية المحددة وخيارات التحميل. نحن نستخدم`MemoryStream` لتحويل سلسلة النص إلى تدفق الذاكرة. ثم نقوم بحفظ المستند الناتج بتنسيق docx.

### نموذج لشفرة مصدر لميزة اكتشاف ترقيم المسافات البيضاء مع Aspose.Words for .NET.

```csharp

            
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// قم بإنشاء مستند نص عادي في شكل سلسلة بأجزاء يمكن تفسيرها على أنها قوائم.
// عند التحميل ، سيتم دائمًا اكتشاف القوائم الثلاث الأولى بواسطة Aspose.Words ،
// وسيتم إنشاء كائنات القائمة لهم بعد التحميل.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// القائمة الرابعة ، مع وجود مسافة بيضاء بين رقم القائمة ومحتويات عنصر القائمة ،
// سيتم اكتشافه كقائمة فقط إذا تم تعيين "DetectNumberingWithWhitespaces" في كائن LoadOptions على true ،
// لتجنب الفقرات التي تبدأ بأرقام يتم اكتشافها عن طريق الخطأ كقوائم.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// قم بتحميل المستند أثناء تطبيق LoadOptions كمعامل وتحقق من النتيجة.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

يمكنك الآن تشغيل الكود المصدري لتحميل المستند النصي الذي يحتوي على أرقام القوائم بمسافات بيضاء ، ثم إنشاء مستند docx مع القوائم المكتشفة. سيتم حفظ ملف الإخراج في الدليل المحدد باسم "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## خاتمة
في هذا البرنامج التعليمي ، استكشفنا ميزة اكتشاف ترقيم المسافات البيضاء في Aspose.Words for .NET. تعلمنا كيفية إنشاء قوائم من مستند نصي يحتوي على أرقام قائمة متبوعة بمسافات بيضاء.

هذه الميزة مفيدة للغاية لمعالجة المستندات التي تحتوي على أرقام القوائم المنسقة بطرق مختلفة. باستخدام خيارات التحميل المناسبة ، يمكن لـ Aspose.Words اكتشاف أرقام القائمة هذه ، حتى إذا كانت متبوعة بمسافات بيضاء ، وتحويلها إلى قوائم منظمة في المستند النهائي.

يمكن أن يؤدي استخدام هذه الميزة إلى توفير الوقت وتحسين كفاءة سير العمل. يمكنك بسهولة استخراج المعلومات من المستندات النصية وتحويلها إلى مستندات جيدة التنظيم باستخدام قوائم مناسبة.

تذكر أن تضع في اعتبارك خيارات التحميل ، مثل تكوين اكتشاف الاتصال بالمسافة البيضاء ، لتحقيق النتائج المرجوة.

يوفر Aspose.Words for .NET العديد من الميزات المتقدمة لمعالجة المستندات وإنشائها. من خلال استكشاف المزيد من الوثائق والأمثلة المقدمة من Aspose.Words ، ستتمكن من استغلال إمكانات هذه المكتبة القوية بشكل كامل.

لذلك ، لا تتردد في دمج اكتشاف ترقيم المسافات البيضاء في Aspose.Words لمشاريع .NET واستفد من مزاياها لإنشاء مستندات جيدة التنظيم وقابلة للقراءة.



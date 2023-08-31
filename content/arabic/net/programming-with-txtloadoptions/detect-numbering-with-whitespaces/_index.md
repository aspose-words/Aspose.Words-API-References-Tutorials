---
title: كشف الترقيم مع المسافات البيضاء
linktitle: كشف الترقيم مع المسافات البيضاء
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية اكتشاف أرقام القائمة ذات المسافات البيضاء في Aspose.Words لـ .NET. قم بتحسين بنية مستنداتك بسهولة.
type: docs
weight: 10
url: /ar/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
في هذا البرنامج التعليمي، سوف نستكشف كود مصدر C# المقدم لميزة "اكتشاف الترقيم بالمسافات البيضاء" مع Aspose.Words for .NET. تتيح لك هذه الميزة اكتشاف وإنشاء قوائم من مستند نصي يحتوي على أرقام قوائم متبوعة بمسافات بيضاء.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: إنشاء المستند النصي

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

في هذه الخطوة، نقوم بإنشاء سلسلة نصية تحاكي مستندًا نصيًا يحتوي على أرقام القائمة متبوعة بمسافات بيضاء. نحن نستخدم محددات قائمة مختلفة مثل النقطة، والقوس الأيمن، ورمز التعداد النقطي، والمسافات البيضاء.

## الخطوة 3: تكوين خيارات التحميل

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 في هذه الخطوة، نقوم بتكوين خيارات تحميل المستندات. نحن نخلق جديدا`TxtLoadOptions` الكائن وتعيين`DetectNumberingWithWhitespaces` الملكية ل`true`. سيسمح هذا لـ Aspose.Words باكتشاف أرقام القائمة حتى لو كانت متبوعة بمسافات بيضاء.

## الخطوة 4: تحميل المستند وحفظه

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 في هذه الخطوة، نقوم بتحميل المستند باستخدام السلسلة النصية المحددة وخيارات التحميل. نحن نستخدم`MemoryStream` لتحويل السلسلة النصية إلى دفق الذاكرة. ثم نقوم بحفظ المستند الناتج بتنسيق .docx.

### نموذج التعليمات البرمجية المصدر لميزة الكشف عن ترقيم المسافات البيضاء باستخدام Aspose.Words لـ .NET.

```csharp

            
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// قم بإنشاء مستند نص عادي على شكل سلسلة تحتوي على أجزاء يمكن تفسيرها على أنها قوائم.
// عند التحميل، سيتم دائمًا اكتشاف القوائم الثلاث الأولى بواسطة Aspose.Words،
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

// القائمة الرابعة، مع وجود مسافة بيضاء بين رقم القائمة ومحتويات عنصر القائمة،
// سيتم اكتشافه كقائمة فقط إذا تم تعيين "DetectNumberingWithWhitespaces" في كائن LoadOptions على القيمة true،
// لتجنب اكتشاف الفقرات التي تبدأ بأرقام كقوائم عن طريق الخطأ.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// قم بتحميل المستند أثناء تطبيق LoadOptions كمعلمة وتحقق من النتيجة.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتحميل المستند النصي الذي يحتوي على أرقام القوائم بمسافات بيضاء، ثم إنشاء مستند .docx بالقوائم المكتشفة. سيتم حفظ ملف الإخراج في الدليل المحدد بالاسم "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا ميزة الكشف عن ترقيم المسافات البيضاء في Aspose.Words لـ .NET. لقد تعلمنا كيفية إنشاء قوائم من مستند نصي يحتوي على أرقام القوائم متبوعة بمسافات بيضاء.

تعتبر هذه الميزة مفيدة للغاية لمعالجة المستندات التي تحتوي على أرقام القوائم المنسقة بطرق مختلفة. باستخدام خيارات التحميل المناسبة، يستطيع Aspose.Words اكتشاف أرقام القائمة هذه، حتى لو كانت متبوعة بمسافات بيضاء، وتحويلها إلى قوائم منظمة في المستند النهائي.

يمكن أن يؤدي استخدام هذه الميزة إلى توفير الوقت وتحسين كفاءة سير العمل لديك. يمكنك بسهولة استخراج المعلومات من المستندات النصية وتحويلها إلى مستندات جيدة التنظيم باستخدام قوائم مناسبة.

تذكر أن تأخذ في الاعتبار خيارات التحميل، مثل تكوين اكتشاف الاتصال بالمسافة البيضاء، لتحقيق النتائج المرجوة.

يوفر Aspose.Words for .NET العديد من الميزات المتقدمة لمعالجة المستندات وإنشائها. ومن خلال استكشاف المزيد من الوثائق والأمثلة المقدمة من Aspose.Words، ستتمكن من استغلال إمكانيات هذه المكتبة القوية بشكل كامل.

لذا، لا تتردد في دمج اكتشاف ترقيم المسافات البيضاء في مشروعات Aspose.Words الخاصة بـ .NET والاستفادة من فوائدها لإنشاء مستندات جيدة التنظيم وقابلة للقراءة.



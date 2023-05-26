---
title: التعامل مع خيارات المسافات
linktitle: التعامل مع خيارات المسافات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدارة المساحات في مستندات TXT الخاصة بك باستخدام Aspose.Words for .NET. قم بإزالة المسافات غير الضرورية وتحسين إمكانية القراءة.
type: docs
weight: 10
url: /sv/net/programming-with-txtloadoptions/handle-spaces-options/
---

في هذا البرنامج التعليمي ، سنستكشف كود المصدر C # المقدم لوظيفة "إدارة المساحات باستخدام خيارات تحميل TXT" مع Aspose.Words for .NET. تتيح لك هذه الميزة تحديد سلوك معالجة المسافات البيضاء عند تحميل مستند TXT.

## الخطوة الأولى: تهيئة البيئة

قبل أن تبدأ ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من أنك أضفت المراجع الضرورية واستوردت مساحات الأسماء المناسبة.

## الخطوة 2: إنشاء مستند نصي

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

في هذه الخطوة ، نقوم بإنشاء سلسلة نصية تحاكي مستندًا نصيًا يحتوي على أسطر بها مسافات بادئة وزائدة.

## الخطوة 3: تكوين خيارات التحميل

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

 في هذه الخطوة ، نقوم بتهيئة الخيارات لتحميل مستند TXT. نخلق ملف`TxtLoadOptions` كائن وتعيين`LeadingSpacesOptions` و`TrailingSpacesOptions` خصائص`TxtLeadingSpacesOptions.Trim` و`TxtTrailingSpacesOptions.Trim` على التوالى. هذا يخبر Aspose. Words بإزالة المسافات البادئة والزائدة من الأسطر عند تحميل المستند.

## الخطوة 4: تحميل المستند

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

 في هذه الخطوة ، نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير دفق الذاكرة الذي يحتوي على سلسلة نصية محددة وخيارات التحميل.

## الخطوة 5: احفظ المستند

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

 في هذه الخطوة الأخيرة ، نحفظ المستند الناتج بتنسيق docx. باستخدام الامتداد`Save` الطريقة وتمرير المسار إلى ملف الإخراج.

يمكنك الآن تشغيل الكود المصدري لتحميل المستند النصي عن طريق تحديد خيارات معالجة المسافات. سيتم حفظ المستند الناتج في الدليل المحدد باسم "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx".

### نموذج رمز مصدر لميزة إدارة المساحة مع خيارات تحميل TXT مع Aspose.Words for .NET*

```csharp

            
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا وظيفة إدارة المساحات باستخدام خيارات تحميل TXT في Aspose.Words for .NET. لقد تعلمنا كيفية تحديد سلوك التعامل مع المسافات البيضاء عند تحميل مستند TXT.

هذه الميزة مفيدة جدًا للتعامل مع المسافات غير الضرورية على يسار ويمين الأسطر في المستند. من خلال تكوين خيارات التحميل المناسبة ، يمكنك بسهولة إزالة هذه المساحات غير المرغوب فيها ، مما يساعد على جعل محتوى المستند أكثر وضوحًا وقابلية للقراءة.

يوفر Aspose.Words for .NET العديد من الميزات المتقدمة لمعالجة المستندات وإنشائها. تعد إدارة المساحات عند تحميل مستند TXT واحدة من العديد من الأدوات القوية التي تضعها تحت تصرفك.

 من المهم اختيار خيارات إدارة المساحة التي تناسب السيناريو الخاص بك بشكل أفضل. في هذا المثال ، استخدمنا الامتداد`Trim`خيارات لإزالة المسافات غير الضرورية من بداية ونهاية السطر. ومع ذلك ، لدى Aspose.Words أيضًا خيارات أخرى للاحتفاظ بالمسافات أو إزالتها تمامًا أو الاحتفاظ بها كما هي.

لا تنس تكييف هذه الخيارات وفقًا لاحتياجاتك الخاصة وهيكل مستندات TXT الخاصة بك.

باستخدام Aspose.Words for .NET ، يمكنك بسهولة معالجة المسافات البيضاء في مستنداتك ، وتحسين جودة التخطيط وقابلية قراءة المحتوى.

لذلك ، لا تتردد في دمج إدارة المسافات البيضاء مع خيارات تحميل TXT في Aspose.Words لمشاريع .NET واستفد من مزاياها لإنشاء مستندات جيدة التنسيق وسهلة القراءة.
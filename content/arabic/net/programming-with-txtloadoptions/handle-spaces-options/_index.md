---
title: التعامل مع خيارات المساحات
linktitle: التعامل مع خيارات المساحات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدارة المساحات في مستندات TXT الخاصة بك باستخدام Aspose.Words لـ .NET. إزالة المسافات غير الضرورية وتحسين إمكانية القراءة.
type: docs
weight: 10
url: /ar/net/programming-with-txtloadoptions/handle-spaces-options/
---

في هذا البرنامج التعليمي، سنستكشف كود مصدر C# المقدم لوظيفة "إدارة المساحات باستخدام خيارات تحميل TXT" مع Aspose.Words for .NET. تتيح لك هذه الميزة تحديد سلوك التعامل مع المسافات البيضاء عند تحميل مستند TXT.

## الخطوة 1: تهيئة البيئة

قبل أن تبدأ، تأكد من إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Words for .NET. تأكد من إضافة المراجع الضرورية واستيراد مساحات الأسماء المناسبة.

## الخطوة 2: إنشاء المستند النصي

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

في هذه الخطوة، نقوم بإنشاء سلسلة نصية تحاكي مستندًا نصيًا يحتوي على أسطر بمسافات بادئة وزائدة.

## الخطوة 3: تكوين خيارات التحميل

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

 في هذه الخطوة، نقوم بتكوين الخيارات لتحميل مستند TXT. نحن نخلق جديدا`TxtLoadOptions` الكائن وتعيين`LeadingSpacesOptions`و`TrailingSpacesOptions` خصائص ل`TxtLeadingSpacesOptions.Trim`و`TxtTrailingSpacesOptions.Trim` على التوالى. هذا يخبر Aspose.Words بإزالة المسافات البادئة والزائدة من الأسطر عند تحميل المستند.

## الخطوة 4: تحميل الوثيقة

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

 في هذه الخطوة نقوم بتحميل المستند باستخدام ملف`Document` الطريقة وتمرير دفق الذاكرة الذي يحتوي على السلسلة النصية المحددة وخيارات التحميل.

## الخطوة 5: احفظ المستند

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

 في هذه الخطوة الأخيرة، نقوم بحفظ المستند الناتج بتنسيق .docx باستخدام الملف`Save` الطريقة وتمرير المسار إلى ملف الإخراج.

يمكنك الآن تشغيل التعليمات البرمجية المصدر لتحميل المستند النصي عن طريق تحديد خيارات معالجة المسافات البيضاء. سيتم حفظ المستند الناتج في الدليل المحدد بالاسم "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx".

### نموذج التعليمات البرمجية المصدر لميزة إدارة المساحة مع خيارات تحميل TXT مع Aspose.Words لـ .NET*

```csharp

            
// المسار إلى دليل المستندات الخاص بك
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

في هذا البرنامج التعليمي، اكتشفنا وظيفة إدارة المساحات باستخدام خيارات تحميل TXT في Aspose.Words for .NET. لقد تعلمنا كيفية تحديد سلوك التعامل مع المسافات البيضاء عند تحميل مستند TXT.

هذه الميزة مفيدة جدًا للتعامل مع المسافات غير الضرورية الموجودة على يسار ويمين الأسطر في المستند. من خلال تكوين خيارات التحميل المناسبة، يمكنك بسهولة إزالة هذه المساحات غير المرغوب فيها، مما يساعد على جعل محتوى المستند أكثر وضوحًا وأكثر قابلية للقراءة.

يوفر Aspose.Words for .NET العديد من الميزات المتقدمة لمعالجة المستندات وإنشائها. تعد إدارة المساحات عند تحميل مستند TXT إحدى الأدوات القوية العديدة التي تضعها تحت تصرفك.

 من المهم اختيار خيارات إدارة المساحة التي تناسب السيناريو المحدد الخاص بك. في هذا المثال استخدمنا`Trim`خيارات لإزالة المسافات غير الضرورية من بداية ونهاية السطر. ومع ذلك، لدى Aspose.Words أيضًا خيارات أخرى للاحتفاظ بالمسافات، أو إزالتها تمامًا، أو الاحتفاظ بها كما هي.

لا تنس تكييف هذه الخيارات وفقًا لاحتياجاتك الخاصة وبنية مستندات TXT الخاصة بك.

باستخدام Aspose.Words for .NET، يمكنك بسهولة التعامل مع المسافات البيضاء في مستنداتك، مما يؤدي إلى تحسين جودة التخطيط وسهولة قراءة المحتوى.

لذا، لا تتردد في دمج إدارة المسافات البيضاء مع خيارات تحميل TXT في مشروعات Aspose.Words for .NET والاستفادة من مزاياها لإنشاء مستندات جيدة التنسيق وسهلة القراءة.
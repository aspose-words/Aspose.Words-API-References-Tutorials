---
title: قراءة الحماية فقط في مستند Word
linktitle: قراءة الحماية فقط في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية حماية مستندات Word المخصصة للقراءة فقط باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/document-protection/read-only-protection/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة الحماية للقراءة فقط في Aspose.Words for .NET. تسمح لك هذه الميزة بجعل مستند Word للقراءة فقط لمنع التعديل غير المصرح به. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وتطبيق الحماية

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: كتابة المحتوى إلى الوثيقة
استخدم كائن DocumentBuilder لكتابة المحتوى إلى المستند:

```csharp
builder.Write("Open document as read-only");
```

## الخطوة 3: قم بتعيين كلمة المرور وجعل المستند للقراءة فقط

قم بتعيين كلمة مرور للمستند باستخدام خاصية SetPassword() لكائن WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

تأكد من استبدال "MyPassword" بكلمة المرور الفعلية التي تريد استخدامها.

## الخطوة 4: تطبيق مستند للقراءة فقط

اجعل المستند للقراءة فقط عن طريق تعيين الخاصية ReadOnlyRecommending إلى true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## الخطوة 5: تطبيق الحماية للقراءة فقط وحفظ المستند

وأخيرًا، قم بتطبيق الحماية للقراءة فقط باستخدام طريقة Protect() لكائن Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند المحمي.

### مثال على التعليمات البرمجية المصدر لحماية القراءة فقط باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لحماية القراءة فقط باستخدام Aspose.Words لـ .NET:

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// أدخل كلمة مرور يصل طولها إلى 15 حرفًا.
doc.WriteProtection.SetPassword("MyPassword");

// جعل المستند للقراءة فقط.
doc.WriteProtection.ReadOnlyRecommended = true;

// تطبيق الحماية ضد الكتابة للقراءة فقط.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

باتباع هذه الخطوات، يمكنك بسهولة حماية مستنداتك

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا ميزة الحماية للقراءة فقط في Aspose.Words for .NET، والتي تتيح لك جعل مستندات Word للقراءة فقط لمنع التعديلات غير المصرح بها. باتباع الخطوات المتوفرة، يمكنك بسهولة تطبيق الحماية للقراءة فقط على مستنداتك وتعزيز أمانها. تساعد الحماية للقراءة فقط على ضمان سلامة ودقة محتوى المستند الخاص بك عن طريق تقييد إمكانيات التحرير. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية ومرنة للتعامل مع حماية المستندات ويدعم العديد من الميزات الأخرى لتخصيص مستندات Word وتأمينها.

### الأسئلة الشائعة لحماية القراءة فقط في مستند Word

#### س: ما هي الحماية للقراءة فقط في Aspose.Words لـ .NET؟

ج: حماية القراءة فقط في Aspose.Words for .NET هي ميزة تسمح لك بجعل مستند Word للقراءة فقط، مما يمنع التعديلات غير المصرح بها. عند تعيين مستند للقراءة فقط، يمكن للمستخدمين فتح المستند وعرضه، لكن لا يمكنهم إجراء أي تغييرات على محتواه.

#### س: كيف يمكنني تطبيق حماية القراءة فقط على مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لتطبيق الحماية للقراءة فقط على مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  إنشاء مثيل لـ`Document` فئة و أ`DocumentBuilder` هدف.
2.  استخدم ال`DocumentBuilder` لكتابة المحتوى إلى الوثيقة.
3.  قم بتعيين كلمة مرور للمستند باستخدام`SetPassword` طريقة`WriteProtection` هدف.
4.  تعيين`ReadOnlyRecommended` ملكية`WriteProtection` يعترض على`true` التوصية بفتح المستند للقراءة فقط.
5.  قم بتطبيق الحماية للقراءة فقط باستخدام`Protect` طريقة`Document` الكائن، مع تحديد`ProtectionType` مثل`ReadOnly`.
6.  احفظ المستند المحمي باستخدام`Save` طريقة`Document` هدف.

#### س: هل يمكنني إزالة الحماية للقراءة فقط من مستند Word باستخدام Aspose.Words لـ .NET؟

ج: نعم، يمكنك إزالة الحماية للقراءة فقط من مستند Word باستخدام Aspose.Words لـ .NET. للقيام بذلك، يمكنك استخدام`Unprotect` طريقة`Document` فئة، والتي تزيل أي حماية موجودة من المستند.

#### س: هل يمكنني تعيين كلمة مرور مختلفة للحماية للقراءة فقط في مستند Word؟

 ج: لا، حماية القراءة فقط في Aspose.Words for .NET لا تسمح لك بتعيين كلمة مرور منفصلة خصيصًا لحماية القراءة فقط. تم تعيين كلمة المرور باستخدام`SetPassword` طريقة`WriteProtection` ينطبق الكائن على الحماية الشاملة للمستندات، بما في ذلك الحماية للقراءة فقط والحماية للقراءة والكتابة.

#### س: هل يمكن للمستخدمين تجاوز حماية القراءة فقط في مستند Word؟

ج: تهدف الحماية للقراءة فقط في مستند Word إلى تثبيط ومنع التعديلات غير المقصودة أو غير المصرح بها. على الرغم من أنه يوفر مستوى من الحماية، إلا أنه يمكن تجاوزه من قبل المستخدمين ذوي المعرفة التقنية الكافية أو أذونات التحرير. ومع ذلك، تعمل الحماية للقراءة فقط كرادع وتساعد في الحفاظ على سلامة المستند.
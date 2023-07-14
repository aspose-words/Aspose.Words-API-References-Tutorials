---
title: قراءة الحماية فقط في مستند Word
linktitle: قراءة الحماية فقط في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية حماية مستندات Word للقراءة فقط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-protection/read-only-protection/
---
في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة الحماية للقراءة فقط في Aspose.Words for .NET. تتيح لك هذه الميزة جعل مستند Word للقراءة فقط لمنع التعديل غير المصرح به. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وتطبيق الحماية

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: اكتب المحتوى إلى المستند
استخدم كائن DocumentBuilder لكتابة محتوى إلى المستند:

```csharp
builder.Write("Open document as read-only");
```

## الخطوة 3: تعيين كلمة المرور وجعل المستند للقراءة فقط

قم بتعيين كلمة مرور للمستند باستخدام خاصية SetPassword () للكائن WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

تأكد من استبدال "MyPassword" بكلمة المرور الفعلية التي تريد استخدامها.

## الخطوة 4: تطبيق وثيقة للقراءة فقط

اجعل المستند للقراءة فقط عن طريق تعيين الخاصية ReadOnlyRecommended على true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## الخطوة 5: تطبيق الحماية للقراءة فقط وحفظ المستند

أخيرًا ، قم بتطبيق الحماية للقراءة فقط باستخدام طريقة Protect () لكائن المستند:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند المحمي.

### مثال على شفرة المصدر للحماية للقراءة فقط باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للحماية للقراءة فقط باستخدام Aspose.Words for .NET:

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// أدخل كلمة مرور يصل طولها إلى 15 حرفًا.
doc.WriteProtection.SetPassword("MyPassword");

// اجعل المستند للقراءة فقط.
doc.WriteProtection.ReadOnlyRecommended = true;

// تطبيق الحماية ضد الكتابة للقراءة فقط.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

باتباع هذه الخطوات ، يمكنك حماية مستنداتك بسهولة

## خاتمة

في هذا البرنامج التعليمي ، استكشفنا ميزة الحماية للقراءة فقط في Aspose.Words for .NET ، والتي تتيح لك جعل مستندات Word للقراءة فقط لمنع التعديلات غير المصرح بها. باتباع الخطوات المقدمة ، يمكنك بسهولة تطبيق الحماية للقراءة فقط على مستنداتك وتعزيز أمانها. تساعد الحماية للقراءة فقط على ضمان تكامل محتوى المستند ودقته من خلال تقييد إمكانيات التحرير. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية ومرنة للتعامل مع حماية المستندات وتدعم العديد من الميزات الأخرى لتخصيص مستندات Word الخاصة بك وتأمينها.

### الأسئلة الشائعة لحماية القراءة فقط في مستند Word

#### س: ما هي الحماية للقراءة فقط في Aspose.Words for .NET؟

ج: الحماية للقراءة فقط في Aspose.Words for .NET هي ميزة تسمح لك بجعل مستند Word للقراءة فقط ، مما يمنع التعديلات غير المصرح بها. عند تعيين مستند إلى للقراءة فقط ، يمكن للمستخدمين فتح المستند وعرضه ، لكن لا يمكنهم إجراء أي تغييرات على محتواه.

#### س: كيف يمكنني تطبيق الحماية للقراءة فقط على مستند Word باستخدام Aspose.Words for .NET؟

ج: لتطبيق الحماية للقراءة فقط على مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بإنشاء مثيل لـ`Document` فئة وأ`DocumentBuilder` هدف.
2.  استخدم ال`DocumentBuilder` لكتابة المحتوى إلى المستند.
3.  قم بتعيين كلمة مرور للمستند باستخدام ملف`SetPassword` طريقة`WriteProtection` هدف.
4.  تعيين`ReadOnlyRecommended`ممتلكات`WriteProtection` يعترض على`true` للتوصية بفتح المستند للقراءة فقط.
5.  قم بتطبيق الحماية للقراءة فقط باستخدام`Protect` طريقة`Document` الكائن ، مع تحديد`ProtectionType` مثل`ReadOnly`.
6.  احفظ المستند المحمي باستخدام امتداد`Save` طريقة`Document` هدف.

#### س: هل يمكنني إزالة الحماية للقراءة فقط من مستند Word باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك إزالة الحماية للقراءة فقط من مستند Word باستخدام Aspose.Words for .NET. للقيام بذلك ، يمكنك استخدام ملف`Unprotect` طريقة`Document` class ، والتي تزيل أي حماية موجودة من المستند.

#### س: هل يمكنني تعيين كلمة مرور مختلفة للحماية للقراءة فقط في مستند Word؟

 ج: لا ، لا تسمح لك الحماية للقراءة فقط في Aspose.Words for .NET بتعيين كلمة مرور منفصلة خصيصًا لحماية القراءة فقط. تم تعيين كلمة المرور باستخدام ملف`SetPassword` طريقة`WriteProtection` كائن ينطبق على حماية المستند الشاملة ، بما في ذلك الحماية للقراءة فقط والقراءة والكتابة.

#### س: هل يمكن للمستخدمين تجاوز الحماية للقراءة فقط في مستند Word؟

ج: تهدف الحماية للقراءة فقط في مستند Word إلى تثبيط ومنع التعديلات العرضية أو غير المصرح بها. في حين أنه يوفر مستوى من الحماية ، يمكن تجاوزه من قبل المستخدمين ذوي المعرفة التقنية الكافية أو أذونات التحرير. ومع ذلك ، تعمل الحماية للقراءة فقط كرادع وتساعد في الحفاظ على سلامة المستند.
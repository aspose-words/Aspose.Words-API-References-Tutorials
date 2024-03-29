---
title: إزالة قيود القراءة فقط
linktitle: إزالة قيود القراءة فقط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إزالة قيود القراءة فقط من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-protection/remove-read-only-restriction/
---
في هذا البرنامج التعليمي، سنرشدك خلال خطوات استخدام ميزة إزالة قيود القراءة فقط Aspose.Words لـ .NET. تتيح لك هذه الميزة إزالة قيود القراءة فقط من مستند Word لجعله قابلاً للتحرير. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وإعداد الحماية

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

قم بتعيين كلمة مرور للمستند باستخدام خاصية SetPassword() لكائن WriteProtection:

تأكد من استبدال "MyPassword" بكلمة المرور الفعلية التي استخدمتها لحماية المستند.

## الخطوة 2: إزالة قيود القراءة فقط

لإزالة قيود القراءة فقط، قم بتعيين الخاصية ReadOnlyRecommending إلى false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## الخطوة 3: تطبيق الحماية غير المقيدة

وأخيرًا، قم بتطبيق الحماية غير المقيدة باستخدام طريقة Protect() الخاصة بكائن المستند:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند دون قيود القراءة فقط.

### مثال على التعليمات البرمجية المصدر لإزالة قيود القراءة فقط باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل لإزالة قيود القراءة فقط باستخدام Aspose.Words لـ .NET:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// أدخل كلمة مرور يصل طولها إلى 15 حرفًا.
doc.WriteProtection.SetPassword("MyPassword");

//قم بإزالة خيار القراءة فقط.
doc.WriteProtection.ReadOnlyRecommended = false;

// تطبيق الحماية ضد الكتابة دون أي حماية.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

باتباع هذه الخطوات، يمكنك بسهولة إزالة قيود القراءة فقط من مستند Word باستخدام Aspose.Words for .NET.


## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إزالة قيود القراءة فقط من مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المتوفرة، يمكنك بسهولة إزالة القيود وجعل المستند قابلاً للتحرير مرة أخرى. يوفر Aspose.Words for .NET مجموعة شاملة من الميزات لإدارة حماية المستندات والقيود، مما يوفر لك المرونة والتحكم في إمكانات الأمان والتحرير لمستندات Word الخاصة بك.

### الأسئلة الشائعة

#### س: ما هو تقييد القراءة فقط في Aspose.Words لـ .NET؟

ج: يشير تقييد القراءة فقط في Aspose.Words for .NET إلى ميزة تسمح لك بتعيين مستند Word كمستند للقراءة فقط، مما يمنع المستخدمين من إجراء أي تعديلات على المحتوى أو التنسيق. يساعد هذا التقييد على حماية سلامة المستند ويضمن عدم تعديله عن طريق الخطأ أو بشكل ضار.

#### س: كيف يمكنني إزالة قيود القراءة فقط باستخدام Aspose.Words for .NET؟

ج: لإزالة قيود القراءة فقط من مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:
1.  إنشاء مثيل لـ`Document` فئة وتعيين كلمة مرور للمستند باستخدام`SetPassword` طريقة`WriteProtection` هدف.
2.  تعيين`ReadOnlyRecommended` ملكية`WriteProtection` يعترض على`false` لإزالة التوصية للقراءة فقط.
3.  قم بتطبيق حماية غير مقيدة على المستند باستخدام`Protect` طريقة`Document` كائن مع`NoProtection` نوع الحماية.
4.  احفظ المستند دون قيود القراءة فقط باستخدام الملف`Save` طريقة`Document` هدف.

#### س: هل يمكنني إزالة قيود القراءة فقط من مستند Word بدون كلمة مرور؟

ج: لا، لا يمكنك إزالة قيود القراءة فقط من مستند Word دون توفير كلمة المرور الصحيحة. تم تعيين تقييد القراءة فقط لأغراض أمنية، وإزالته بدون كلمة المرور قد يؤدي إلى تقويض غرض حماية سلامة المستند.

#### س: هل يمكنني إزالة قيود القراءة فقط من مستند Word باستخدام كلمة مرور خاطئة؟

ج: لا، لا يمكنك إزالة قيود القراءة فقط من مستند Word باستخدام كلمة مرور خاطئة. يجب توفير كلمة المرور الصحيحة لإزالة قيود القراءة فقط وجعل المستند قابلاً للتحرير مرة أخرى. وهذا يضمن أن المستخدمين المصرح لهم فقط الذين لديهم كلمة المرور الصحيحة يمكنهم تعديل المستند.

#### س: هل من الممكن إزالة أنواع أخرى من حماية المستندات باستخدام Aspose.Words لـ .NET؟

ج: نعم، يوفر Aspose.Words for .NET طرقًا متنوعة لإزالة أنواع أخرى من حماية المستندات، مثل حماية كلمة المرور أو حماية النماذج أو قيود تحرير المستندات. اعتمادًا على نوع الحماية المطبقة على المستند، يمكنك استخدام الأساليب والخصائص المقابلة التي يوفرها Aspose.Words لإزالة الحماية المحددة وجعل المستند قابلاً للتحرير.

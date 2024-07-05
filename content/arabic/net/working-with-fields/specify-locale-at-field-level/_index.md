---
title: تحديد اللغة على مستوى الحقل
linktitle: تحديد اللغة على مستوى الحقل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديد الترجمة على مستوى الحقل في مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/specify-locale-at-field-level/
---

فيما يلي دليل خطوة بخطوة لشرح كود مصدر C# التالي الذي يسمح بتحديد الترجمة على مستوى الحقل باستخدام ميزة Aspose.Words for .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: قم بتعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك حيث سيتم حفظ المستند المحرر.

## الخطوة 2: إنشاء منشئ المستندات

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 نحن هنا نقوم بإنشاء مثيل لـ`DocumentBuilder` فئة والتي سوف تسمح لنا بإضافة حقول إلى الوثيقة.

## الخطوة 3: أدخل حقل تاريخ مع موقع محدد

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 نستخدم منشئ المستندات لإدراج حقل من النوع`FieldType.FieldDate` في الوثيقة. من خلال تعيين`LocaleId`الملكية ل`1049`، نحدد الترجمة الروسية لهذا الحقل.

## الخطوة 4: احفظ المستند المعدل

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

وأخيرًا، نقوم بحفظ المستند المعدل بالموقع المحدد في ملف محدد.

### نموذج التعليمات البرمجية المصدر لتحديد الترجمة على مستوى الحقل باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

كان هذا مثالاً للتعليمات البرمجية المصدرية لتحديد الترجمة على مستوى الحقل في مستند باستخدام Aspose.Words لـ .NET. يمكنك استخدام هذا الرمز لإدراج حقول التاريخ بمواقع محددة في مستندات Word الخاصة بك.

### الأسئلة الشائعة

#### س: كيف يمكنني تحديد الإعدادات المحلية على مستوى الحقل في Aspose.Words لـ .NET؟

 ج: لتحديد اللغة على مستوى الحقل في Aspose.Words لـ .NET، يمكنك استخدام`FieldOptions` الطبقة و`FieldLocale` خاصية لتعيين اللغة المطلوبة. على سبيل المثال، يمكنك استخدام`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` لتحديد اللغة الفرنسية (فرنسا).

#### س: هل من الممكن تحديد لغة مختلفة لكل حقل في Aspose.Words لـ .NET؟

 ج: نعم، من الممكن تحديد لغة مختلفة لكل حقل في Aspose.Words لـ .NET. يمكنك استخدام ال`FieldOptions.FieldLocale` الخاصية قبل إنشاء أو تحديث حقل معين لتعيين لغة مختلفة له.

#### س: كيف يمكنني الحصول على اللغة المستخدمة حاليًا لحقل في Aspose.Words لـ .NET؟

 ج: للحصول على اللغة المستخدمة حاليًا لحقل في Aspose.Words لـ .NET، يمكنك استخدام الحقل`Field.LocaleId`ملكية. سيسمح لك هذا بالحصول على معرف اللغة المرتبط بالحقل.
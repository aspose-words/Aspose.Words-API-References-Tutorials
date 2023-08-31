---
title: حدد الإعدادات المحلية على مستوى الحقل
linktitle: حدد الإعدادات المحلية على مستوى الحقل
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تحديد الترجمة على مستوى الحقل في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/specify-locale-at-field-level/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح التعليمات البرمجية المصدر C # التالية التي تسمح بتحديد الترجمة على مستوى الحقل باستخدام ميزة Aspose.Words for .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: تعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك حيث سيتم حفظ المستند المحرر.

## الخطوة 2: إنشاء منشئ المستندات

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 نحن هنا بصدد إنشاء مثيل لـ`DocumentBuilder` فئة تسمح لنا بإضافة حقول إلى المستند.

## الخطوة 3: أدخل حقل التاريخ بموقع محدد

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 نستخدم منشئ المستندات لإدخال حقل من النوع`FieldType.FieldDate` في المستند. عن طريق تحديد`LocaleId` الملكية ل`1049`، نحدد الترجمة الروسية لهذا المجال.

## الخطوة 4: احفظ المستند المعدل

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

أخيرًا ، نحفظ المستند المعدل بالموقع المحدد في ملف محدد.

### نموذج لشفرة المصدر لتحديد الأقلمة على مستوى الحقل باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

كان هذا مثالًا على كود مصدر لتحديد الترجمة على مستوى الحقل في مستند باستخدام Aspose.Words for .NET. يمكنك استخدام هذا الرمز لإدراج حقول التاريخ بمواقع محددة في مستندات Word الخاصة بك.

### التعليمات

#### س: كيف يمكنني تحديد الإعدادات المحلية على مستوى الحقل في Aspose.Words for .NET؟

 ج: لتحديد اللغة على مستوى الحقل في Aspose.Words for .NET ، يمكنك استخدام`FieldOptions` الطبقة و`FieldLocale` خاصية لتعيين اللغة المطلوبة. على سبيل المثال ، يمكنك استخدام ملفات`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` لتحديد اللغة الفرنسية (فرنسا).

#### س: هل من الممكن تحديد موقع مختلف لكل حقل في Aspose.Words for .NET؟

 ج: نعم ، من الممكن تحديد موقع مختلف لكل حقل في Aspose.Words for .NET. يمكنك استخدام ال`FieldOptions.FieldLocale` الخاصية قبل إنشاء أو تحديث حقل معين لتعيين إعدادات محلية مختلفة له.

#### س: كيف يمكنني الحصول على الإعدادات المحلية المستخدمة حاليًا لحقل في Aspose.Words for .NET؟

 ج: للحصول على اللغة المستخدمة حاليًا لحقل في Aspose.Words for .NET ، يمكنك استخدام الحقول`Field.LocaleId` ملكية. سيسمح لك ذلك بالحصول على معرف الإعدادات المحلية المقترن بالحقل.
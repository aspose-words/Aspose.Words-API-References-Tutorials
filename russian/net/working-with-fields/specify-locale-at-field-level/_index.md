---
title: حدد الإعدادات المحلية على مستوى الحقل
linktitle: حدد الإعدادات المحلية على مستوى الحقل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديد الترجمة على مستوى الحقل في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/specify-locale-at-field-level/
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

 نستخدم منشئ المستندات لإدخال حقل من النوع`FieldType.FieldDate` في المستند. عن طريق تحديد`LocaleId` ملكية ل`1049`، نحدد الترجمة الروسية لهذا المجال.

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

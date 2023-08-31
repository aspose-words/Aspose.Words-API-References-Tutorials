---
title: إدراج كائن Ole في مستند Word كأيقونة
linktitle: إدراج كائن Ole في مستند Word كأيقونة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج كائن OLE في مستند Word كأيقونة باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه والتي توضح كيفية إدراج كائن OLE في مستند Word كأيقونة باستخدام Aspose.Words لـ .NET.

## الخطوة 1: استيراد المراجع اللازمة
قبل أن تبدأ، تأكد من استيراد المراجع اللازمة لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملفك المصدر.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## الخطوة 2: إنشاء مستند جديد ومولد المستندات
 في هذه الخطوة، سنقوم بإنشاء مستند جديد باستخدام الملف`Document` فئة ومنشئ المستندات باستخدام`DocumentBuilder` فصل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: قم بإدراج كائن OLE كرمز
 استخدم منشئ المستندات`InsertOleObjectAsIcon` طريقة لإدراج كائن OLE كرمز في المستند. حدد مسار ملف OLE وعلامة العرض ومسار الرمز واسم الكائن المضمن.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## الخطوة 4: احفظ المستند
 استخدم الوثيقة`Save` طريقة حفظ المستند في ملف .

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### مثال للتعليمة البرمجية المصدر لإدراج كائن OLE كأيقونة باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

هذا نموذج تعليمات برمجية كامل لإدراج كائن OLE كرمز مع Aspose.Words لـ .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

## خاتمة

في الختام، قمنا باستكشاف دليل خطوة بخطوة لإدراج كائن OLE كرمز في مستند Word باستخدام Aspose.Words for .NET.

باتباع هذه الخطوات، ستتمكن من إدراج كائن OLE كرمز في مستندات Word الخاصة بك بنجاح باستخدام Aspose.Words for .NET. تأكد من استيراد المراجع اللازمة واتبع التعليمات بعناية للحصول على النتائج المرجوة.

### الأسئلة الشائعة حول إدراج كائن ole في مستند Word كرمز

#### س. ما هي المراجع المطلوبة لإدراج كائن OLE كرمز في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: أنت بحاجة إلى استيراد المراجع التالية إلى مشروعك لاستخدام Aspose.Words لـ .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### س. كيفية إنشاء مستند جديد ومولد المستندات في Aspose.Words لـ .NET؟

 ج: يمكنك إنشاء مستند جديد باستخدام`Document` فئة ومنشئ المستندات باستخدام`DocumentBuilder`فصل. هنا مثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### س. كيفية إدراج كائن OLE كرمز في المستند؟

 ج: استخدم أداة إنشاء المستندات`InsertOleObjectAsIcon` طريقة لإدراج كائن OLE كرمز. حدد مسار ملف OLE وعلامة العرض ومسار الرمز واسم الكائن المضمن. هنا مثال :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### س. كيفية حفظ المستند مع إدراج كائن OLE كرمز؟

 ج: استخدم الوثيقة`Save`طريقة حفظ المستند في ملف . هنا مثال :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```
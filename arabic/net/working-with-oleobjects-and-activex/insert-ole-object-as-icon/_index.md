---
title: إدراج كائن Ole في مستند Word كرمز
linktitle: إدراج كائن Ole في مستند Word كرمز
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج كائن OLE في مستند Word كأيقونة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود مصدر C # أدناه والذي يوضح كيفية إدراج كائن OLE في مستند Word كأيقونة باستخدام Aspose.Words for .NET.

## الخطوة 1: استيراد المراجع الضرورية
قبل أن تبدأ ، تأكد من استيراد المراجع الضرورية لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملف المصدر الخاص بك.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## الخطوة 2: إنشاء مستند جديد ومولد مستندات
 في هذه الخطوة ، سننشئ مستندًا جديدًا باستخدام امتداد`Document` class ومُنشئ المستندات باستخدام امتداد`DocumentBuilder` فصل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل كائن OLE كرمز
 استخدم وثيقة منشئ`InsertOleObjectAsIcon` طريقة لإدراج كائن OLE كرمز في المستند. حدد مسار ملف OLE وعلامة العرض ومسار الرمز واسم الكائن المضمن.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## الخطوة 4: احفظ المستند
 استخدم ملف`Save` طريقة لحفظ المستند في ملف.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### مثال على شفرة المصدر لإدراج كائن OLE كرمز مع Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

هذا نموذج كود كامل لإدراج كائن OLE كأيقونة مع Aspose.Words for .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

## خاتمة

في الختام ، اكتشفنا دليلاً مفصلاً خطوة بخطوة لإدراج كائن OLE كأيقونة في مستند Word باستخدام Aspose.Words for .NET.

باتباع هذه الخطوات ، ستتمكن من إدراج كائن OLE بنجاح كأيقونة في مستندات Word باستخدام Aspose.Words for .NET. تأكد من استيراد المراجع اللازمة واتبع التعليمات بعناية للحصول على النتائج المرجوة.

### الأسئلة الشائعة حول إدراج كائن Oole في مستند Word كرمز

#### س: ما المراجع المطلوبة لإدراج كائن OLE كأيقونة في مستند Word باستخدام Aspose.Words for .NET؟

ج: أنت بحاجة إلى استيراد المراجع التالية إلى مشروعك لاستخدام Aspose.Words for .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### س. كيف يمكن إنشاء مستند جديد ومولد مستندات في Aspose.Words for .NET؟

 ج: يمكنك إنشاء مستند جديد باستخدام ملف`Document` class ومُنشئ المستندات باستخدام امتداد`DocumentBuilder`فصل. هنا مثال :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. كيفية إدراج كائن OLE كرمز في المستند؟

 ج: استخدم أداة إنشاء المستندات`InsertOleObjectAsIcon` طريقة لإدراج كائن OLE كرمز. حدد مسار ملف OLE وعلامة العرض ومسار الرمز واسم الكائن المضمن. هنا مثال :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. كيفية حفظ المستند مع إدراج كائن OLE كرمز؟

 ج: استخدم الوثيقة`Save`طريقة لحفظ المستند في ملف. هنا مثال :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```
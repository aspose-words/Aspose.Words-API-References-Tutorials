---
title: إدراج كائن Ole في مستند Word
linktitle: إدراج كائن Ole في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج كائن OLE في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه والتي توضح كيفية إدراج كائن OLE في مستند Word باستخدام Aspose.Words لـ .NET.

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

## الخطوة 3: قم بإدراج كائن OLE
 استخدم منشئ المستندات`InsertOleObject`طريقة لإدراج كائن OLE في المستند. حدد عنوان URL لكائن OLE ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى.

```csharp
builder. InsertOleObject("http://www.aspose.com"، "htmlfile"، true، true، null)؛
```

## الخطوة 4: احفظ المستند
 استخدم الوثيقة`Save` طريقة حفظ المستند في ملف .

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### مثال للتعليمة البرمجية المصدر لإدراج كائن OLE باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com"، "htmlfile"، true، true، null)؛

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

هذا نموذج تعليمة برمجية كاملة لإدراج كائن OLE باستخدام Aspose.Words لـ .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

## خاتمة

في الختام، يعد إدراج كائنات OLE في مستند Word ميزة قوية يقدمها Aspose.Words لـ .NET. باستخدام هذه المكتبة، يمكنك بسهولة تضمين كائنات OLE مثل ملفات HTML وجداول بيانات Excel وعروض PowerPoint التقديمية وما إلى ذلك في مستندات Word الخاصة بك.

في هذه المقالة، مررنا بدليل خطوة بخطوة لشرح الكود المصدري في لغة C# والذي يوضح كيفية إدراج كائن OLE في مستند Word. لقد قمنا بتغطية المراجع الضرورية، وإنشاء مستند جديد ومولد المستندات، والخطوات اللازمة لإدراج كائن OLE وحفظ المستند.

### الأسئلة المتداولة حول إدراج كائن OLE في مستند Word

#### س: ما هي بيانات الاعتماد التي أحتاج إلى استيرادها لاستخدام Aspose.Words لـ .NET؟

ج: لاستخدام Aspose.Words لـ .NET، تحتاج إلى استيراد المراجع التالية:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### س: كيفية إنشاء مستند جديد ومولد المستندات؟

 ج: يمكنك إنشاء مستند جديد باستخدام`Document` فئة ومنشئ المستندات باستخدام`DocumentBuilder` الصف، كما هو موضح أدناه:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### س: كيفية إدراج كائن OLE في المستند؟

 ج: استخدم`InsertOleObject` طريقة منشئ المستندات (`DocumentBuilder`) لإدراج كائن OLE في المستند. حدد عنوان URL لكائن OLE ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى. هنا مثال :

```csharp
builder. InsertOleObject("http://www.aspose.com"، "htmlfile"، true، true، null)؛
```

#### س: كيفية حفظ الوثيقة؟

 ج: استخدم الوثيقة`Save`طريقة حفظ المستند في ملف . هنا مثال :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### س: هل يمكنك تقديم مثال كامل لإدراج كائن OLE باستخدام Aspose.Words لـ .NET؟

ج: هنا نموذج تعليمة برمجية كاملة لإدراج كائن OLE باستخدام Aspose.Words لـ .NET. تأكد من استيراد المراجع اللازمة واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com"، "htmlfile"، true، true، null)؛

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

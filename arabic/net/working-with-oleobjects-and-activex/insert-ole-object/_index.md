---
title: إدراج كائن Ole في مستند Word
linktitle: إدراج كائن Ole في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج كائن OLE في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود مصدر C # أدناه والذي يوضح كيفية إدراج كائن OLE في مستند Word باستخدام Aspose.Words for .NET.

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

## الخطوة 3: أدخل كائن OLE
 استخدم وثيقة منشئ`InsertOleObject`طريقة لإدراج كائن OLE في المستند. حدد عنوان URL لكائن OLE ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى.

```csharp
builder. InsertOleObject("http://www.aspose.com "،" htmlfile "، true، true، null)؛
```

## الخطوة 4: احفظ المستند
 استخدم ملف`Save` طريقة لحفظ المستند في ملف.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### مثال على شفرة المصدر لإدراج كائن OLE مع Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com "،" htmlfile "، true، true، null)؛

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

هذا نموذج تعليمات برمجية كامل لإدراج كائن OLE مع Aspose.Words for .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

## خاتمة

في الختام ، يعد إدراج كائنات OLE في مستند Word ميزة قوية تقدمها Aspose.Words for .NET. باستخدام هذه المكتبة ، يمكنك بسهولة تضمين كائنات OLE مثل ملفات HTML وجداول بيانات Excel وعروض PowerPoint التقديمية وما إلى ذلك في مستندات Word الخاصة بك.

في هذه المقالة ، قمنا بالاطلاع على دليل خطوة بخطوة لشرح كود المصدر في C # الذي يوضح كيفية إدراج كائن OLE في مستند Word. قمنا بتغطية المراجع الضرورية ، وإنشاء مستند جديد ومولد مستندات ، وخطوات إدراج كائن OLE وحفظ المستند.

### الأسئلة المتداولة حول إدراج كائن OLE في مستند Word

#### س: ما هي أوراق الاعتماد التي أحتاجها لاستيرادها لاستخدام Aspose.Words for .NET؟

ج: لاستخدام Aspose.Words مع .NET ، يلزمك استيراد المراجع التالية:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### س: كيف يتم إنشاء مستند جديد ومولد مستندات؟

 ج: يمكنك إنشاء مستند جديد باستخدام ملف`Document` class ومُنشئ المستندات باستخدام امتداد`DocumentBuilder` الصف ، كما هو موضح أدناه:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### س: كيفية إدراج كائن OLE في المستند؟

 ج: استخدم ملف`InsertOleObject` طريقة منشئ الوثيقة (`DocumentBuilder`) لإدراج كائن OLE في المستند. حدد عنوان URL لكائن OLE ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى. هنا مثال :

```csharp
builder. InsertOleObject("http://www.aspose.com "،" htmlfile "، true، true، null)؛
```

#### س: كيف تحفظ المستند؟

 ج: استخدم الوثيقة`Save`طريقة لحفظ المستند في ملف. هنا مثال :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### س: هل يمكنك تقديم مثال كامل لإدخال كائن OLE باستخدام Aspose.Words for .NET؟

ج: إليك نموذج تعليمة برمجية كاملة لإدراج كائن OLE مع Aspose.Words for .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com "،" htmlfile "، true، true، null)؛

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

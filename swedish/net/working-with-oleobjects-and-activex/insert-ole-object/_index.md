---
title: إدراج كائن Ole
linktitle: إدراج كائن Ole
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج كائن OLE في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/insert-ole-object/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود مصدر C # أدناه والذي يوضح كيفية إدراج كائن OLE باستخدام Aspose.Words for .NET.

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
 استخدم وثيقة منشئ`InsertOleObject` طريقة لإدراج كائن OLE في المستند. حدد عنوان URL لكائن OLE ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى.

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

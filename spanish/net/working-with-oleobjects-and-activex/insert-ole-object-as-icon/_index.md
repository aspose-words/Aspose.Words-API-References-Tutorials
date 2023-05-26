---
title: إدراج كائن Ole كرمز
linktitle: إدراج كائن Ole كرمز
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج كائن OLE كرمز باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # أدناه والتي توضح كيفية إدراج كائن OLE كأيقونة باستخدام Aspose.Words for .NET.

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

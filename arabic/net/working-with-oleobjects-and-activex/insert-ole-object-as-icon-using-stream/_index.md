---
title: قم بإدراج كائن Ole كرمز باستخدام الدفق
linktitle: قم بإدراج كائن Ole كرمز باستخدام الدفق
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج كائن OLE كرمز باستخدام دفق باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

فيما يلي دليل خطوة بخطوة لشرح كود المصدر C # أدناه والذي يوضح كيفية إدراج كائن OLE كأيقونة باستخدام دفق مع Aspose.Words for .NET.

## الخطوة 1: استيراد المراجع الضرورية
قبل أن تبدأ ، تأكد من استيراد المراجع الضرورية لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملف المصدر الخاص بك.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## الخطوة 2: إنشاء مستند جديد ومولد مستندات
 في هذه الخطوة ، سننشئ مستندًا جديدًا باستخدام امتداد`Document` class ومُنشئ المستندات باستخدام امتداد`DocumentBuilder` فصل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل كائن OLE كرمز من دفق
 استخدم وثيقة منشئ`InsertOleObjectAsIcon` أسلوب لإدراج كائن OLE كرمز من دفق إلى المستند. حدد دفق البيانات ونوع الكائن ومسار الرمز واسم الكائن المضمن.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## الخطوة 4: احفظ المستند
 استخدم ملف`Save` طريقة لحفظ المستند في ملف.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### مثال على شفرة المصدر لإدراج كائن OLE كرمز باستخدام دفق مع Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

هذا نموذج رمز كامل لإدراج كائن OLE كرمز باستخدام دفق مع Aspose.Words for .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

## خاتمة

يوضح الدليل التفصيلي أعلاه كيفية إدراج كائن OLE كأيقونة في مستند Word باستخدام تدفق مع Aspose.Words for .NET. باتباع الخطوات الموضحة ، ستتمكن من دمج هذه الوظيفة في مشروعك. تأكد من استيراد المراجع الضرورية ، وإنشاء مستند جديد ومولد مستندات ، وإدراج كائن OLE كرمز من الدفق ، ثم حفظ المستند. استخدم نموذج التعليمات البرمجية المقدم كنقطة بداية وقم بتخصيصه وفقًا لاحتياجاتك.

### التعليمات

#### س: كيف يمكن استيراد المراجع الضرورية لاستخدام Aspose.Words مع .NET؟

A. لاستيراد المراجع الضرورية ، يجب اتباع الخطوات التالية:

 أضف ما يلي`using` البيانات أعلى ملف المصدر الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
تأكد من إضافة مكتبة Aspose.Words إلى مشروعك.

#### س. كيف يمكن إنشاء مستند جديد ومنشئ مستندات باستخدام Aspose.Words for .NET؟

A. لإنشاء مستند ومستند جديد ، يمكنك اتباع الخطوات التالية:

 استخدم ال`Document` فئة لإنشاء مستند جديد:

```csharp
Document doc = new Document();
```
 استخدم ال`DocumentBuilder` فئة لإنشاء منشئ مستندات مرتبط بالمستند الذي تم إنشاؤه مسبقًا:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### س: كيف يمكن إدراج كائن OLE كأيقونة من دفق باستخدام Aspose.Words for .NET؟

A. لإدراج كائن OLE كرمز من دفق ، يمكنك اتباع الخطوات التالية:

 استخدم ال`InsertOleObjectAsIcon` طريقة منشئ المستندات لإدراج كائن OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### س: كيف تحفظ المستند في ملف؟

A.  لحفظ المستند في ملف ، يمكنك استخدام ملحق`Save` طريقة المستند التي تحدد مسار الوجهة:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q. كيف يمكنني تضمين التعليمات البرمجية لإدراج كائن OLE كرمز من دفق في مشروعي؟

A. لتضمين التعليمات البرمجية لإدراج كائن OLE كرمز من دفق في مشروعك ، اتبع الخطوات التالية:
- استيراد المراجع اللازمة عن طريق إضافة المناسب`using` صياغات.
-  قم بإنشاء مستند جديد ومنشئ مستندات باستخدام امتداد`Document` و`DocumentBuilder` الطبقات.
- استخدم التعليمات البرمجية لإدراج كائن OLE كرمز من دفق.
-  احفظ المستند باستخدام ملف`Save` الطريقة مع مسار الوجهة المناسب.

باتباع هذه الخطوات ، ستتمكن من إدراج كائن OLE بنجاح كأيقونة من دفق باستخدام Aspose.Words for .NET. تأكد من اتباع التعليمات واستيراد المراجع اللازمة للحصول على النتائج المرجوة.
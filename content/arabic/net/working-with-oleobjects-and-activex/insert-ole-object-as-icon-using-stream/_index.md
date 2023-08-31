---
title: إدراج كائن Ole كرمز باستخدام الدفق
linktitle: إدراج كائن Ole كرمز باستخدام الدفق
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج كائن OLE كرمز باستخدام دفق مع Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه والتي توضح كيفية إدراج كائن OLE كرمز باستخدام دفق مع Aspose.Words لـ .NET.

## الخطوة 1: استيراد المراجع اللازمة
قبل أن تبدأ، تأكد من استيراد المراجع اللازمة لاستخدام Aspose.Words for .NET في مشروعك. يتضمن ذلك استيراد مكتبة Aspose.Words وإضافة مساحات الأسماء المطلوبة إلى ملفك المصدر.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## الخطوة 2: إنشاء مستند جديد ومولد المستندات
 في هذه الخطوة، سنقوم بإنشاء مستند جديد باستخدام الملف`Document` فئة ومنشئ المستندات باستخدام`DocumentBuilder` فصل.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: قم بإدراج كائن OLE كرمز من الدفق
 استخدم منشئ المستندات`InsertOleObjectAsIcon` طريقة لإدراج كائن OLE كرمز من دفق في المستند. حدد دفق البيانات ونوع الكائن ومسار الرمز واسم الكائن المضمن.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## الخطوة 4: احفظ المستند
 استخدم الوثيقة`Save` طريقة حفظ المستند في ملف .

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### مثال للتعليمة البرمجية المصدر لإدراج كائن OLE كأيقونة باستخدام دفق مع Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

هذا نموذج تعليمات برمجية كامل لإدراج كائن OLE كرمز باستخدام دفق مع Aspose.Words لـ .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

## خاتمة

يشرح الدليل التفصيلي أعلاه كيفية إدراج كائن OLE كرمز في مستند Word باستخدام التدفق مع Aspose.Words لـ .NET. باتباع الخطوات الموضحة، ستتمكن من دمج هذه الوظيفة في مشروعك. تأكد من استيراد المراجع الضرورية، وإنشاء مستند جديد ومولد المستندات، وإدراج كائن OLE كرمز من الدفق، ثم احفظ المستند. استخدم نموذج التعليمات البرمجية المقدم كنقطة بداية وقم بتخصيصه حسب احتياجاتك.

### الأسئلة الشائعة

#### س. كيفية استيراد المراجع الضرورية لاستخدام Aspose.Words لـ .NET؟

A. لاستيراد المراجع اللازمة، عليك اتباع الخطوات التالية:

 أضف ما يلي`using` البيانات الموجودة أعلى الملف المصدر الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
تأكد من إضافة مكتبة Aspose.Words إلى مشروعك.

#### س. كيفية إنشاء مستند جديد ومنشئ المستندات باستخدام Aspose.Words لـ .NET؟

A. لإنشاء مستند جديد ومولد المستندات، يمكنك اتباع الخطوات التالية:

 استخدم ال`Document` فئة لإنشاء مستند جديد:

```csharp
Document doc = new Document();
```
 استخدم ال`DocumentBuilder` فئة لإنشاء منشئ المستندات المرتبط بالمستند الذي تم إنشاؤه مسبقًا:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### س. كيفية إدراج كائن OLE كرمز من دفق باستخدام Aspose.Words لـ .NET؟

A. لإدراج كائن OLE كرمز من دفق، يمكنك اتباع الخطوات التالية:

 استخدم ال`InsertOleObjectAsIcon` طريقة منشئ المستندات لإدراج كائن OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### س: كيفية حفظ المستند في ملف؟

A.  لحفظ المستند في ملف، يمكنك استخدام`Save` طريقة الوثيقة التي تحدد مسار الوجهة:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q. كيف يمكنني تضمين التعليمات البرمجية لإدراج كائن OLE كرمز من دفق في المشروع الخاص بي؟

A. لتضمين التعليمات البرمجية الخاصة بإدراج كائن OLE كرمز من دفق في مشروعك، اتبع الخطوات التالية:
- قم باستيراد المراجع اللازمة عن طريق إضافة المراجع المناسبة`using` صياغات.
-  قم بإنشاء مستند جديد ومنشئ المستندات باستخدام`Document` و`DocumentBuilder` الطبقات.
- استخدم التعليمات البرمجية لإدراج كائن OLE كرمز من الدفق.
-  احفظ المستند باستخدام`Save` الطريقة مع مسار الوجهة المناسب.

باتباع هذه الخطوات، ستتمكن من إدراج كائن OLE بنجاح كرمز من دفق باستخدام Aspose.Words for .NET. تأكد من اتباع التعليمات واستيراد المراجع اللازمة للحصول على النتائج المرجوة.
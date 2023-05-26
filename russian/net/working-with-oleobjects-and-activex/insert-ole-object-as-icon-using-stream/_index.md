---
title: قم بإدراج كائن Ole كرمز باستخدام الدفق
linktitle: قم بإدراج كائن Ole كرمز باستخدام الدفق
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج كائن OLE كرمز باستخدام دفق باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
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
---
title: إدراج كائن Ole في Word باستخدام حزمة Ole
linktitle: إدراج كائن Ole في Word باستخدام حزمة Ole
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج كائن OLE مع حزمة OLE في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه والتي توضح كيفية إدراج كائن OLE في Word باستخدام حزمة OLE باستخدام Aspose.Words for .NET.

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

## الخطوة 3: قم بإدراج كائن OLE مع حزمة OLE
 استخدم منشئ المستندات`InsertOleObject` طريقة لإدراج كائن OLE مع حزمة OLE في المستند. حدد دفق البيانات ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## الخطوة 4: احفظ المستند
 استخدم الوثيقة`Save` طريقة حفظ المستند في ملف .

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### نموذج التعليمات البرمجية المصدر لإدراج كائن OLE مع حزمة OLE مع Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

هذا نموذج تعليمات برمجية كامل لإدراج كائن OLE مع حزمة OLE مع Aspose.Words لـ .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.

## خاتمة

في الختام، لقد مررنا بدليل خطوة بخطوة لإدراج كائن OLE في مستند Word باستخدام حزمة OLE باستخدام Aspose.Words for .NET.

باتباع هذه الخطوات، ستتمكن من إدراج كائنات OLE مع حزم OLE بنجاح في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET. تأكد من استيراد المراجع اللازمة واتبع التعليمات بعناية للحصول على النتائج المرجوة.

### الأسئلة الشائعة حول إدراج كائن ole في Word باستخدام حزمة ole

#### س: ما هي بيانات الاعتماد التي أحتاج إلى استيرادها لاستخدام Aspose.Words لـ .NET؟

ج: لاستخدام Aspose.Words لـ .NET، تحتاج إلى استيراد المراجع التالية:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### س: كيفية إنشاء مستند جديد ومولد المستندات؟

 ج: يمكنك إنشاء مستند جديد باستخدام`Document` فئة ومنشئ المستندات باستخدام`DocumentBuilder` الصف، كما هو موضح أدناه:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### س: كيفية إدراج كائن OLE مع حزمة OLE في المستند؟

 ج: استخدم`InsertOleObject`طريقة منشئ المستندات (`DocumentBuilder`) لإدراج كائن OLE مع حزمة OLE في المستند. حدد دفق البيانات ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى. هنا مثال :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### س: كيفية حفظ الوثيقة؟

 ج: استخدم الوثيقة`Save` طريقة حفظ المستند في ملف . هنا مثال :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### س: هل يمكنك تقديم مثال كامل لإدراج كائن OLE مع حزمة OLE مع Aspose.Words for .NET؟

ج: إليك نموذج التعليمات البرمجية الكامل لإدراج كائن OLE مع حزمة OLE باستخدام Aspose.Words لـ .NET. تأكد من استيراد المراجع اللازمة واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

بهذا نختتم برنامجنا التعليمي حول إدراج كائن OLE مع حزمة OLE في مستند Word باستخدام Aspose.Words for .NET. لا تتردد في استيراد المراجع اللازمة واتبع الخطوات الموضحة لدمج هذا الرمز في مشروعك. إذا كان لديك أي أسئلة أخرى، فلا تتردد في الاتصال بنا.
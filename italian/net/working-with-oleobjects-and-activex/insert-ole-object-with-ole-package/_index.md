---
title: قم بإدراج كائن Ole مع حزمة Ole
linktitle: قم بإدراج كائن Ole مع حزمة Ole
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج كائن OLE مع حزمة OLE في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود مصدر C # أدناه والذي يوضح كيفية إدراج كائن OLE مع حزمة OLE باستخدام Aspose.Words for .NET.

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

## الخطوة 3: إدراج كائن OLE مع حزمة OLE
 استخدم أداة إنشاء المستندات`InsertOleObject` أسلوب لإدراج كائن OLE مع حزمة OLE في المستند. حدد دفق البيانات ونوع الكائن وخيارات العرض والإعدادات الضرورية الأخرى.

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
 استخدم ملف`Save` طريقة لحفظ المستند في ملف.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### نموذج التعليمات البرمجية المصدر لإدراج كائن OLE مع حزمة OLE مع Aspose.Words for .NET

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

هذا نموذج رمز كامل لإدخال كائن OLE مع حزمة OLE مع Aspose.Words for .NET. تأكد من استيراد المراجع الضرورية واتبع الخطوات الموضحة مسبقًا لدمج هذا الرمز في مشروعك.
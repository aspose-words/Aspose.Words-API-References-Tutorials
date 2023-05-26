---
title: استبدل الارتباطات التشعبية
linktitle: استبدل الارتباطات التشعبية
second_title: Aspose.Words لمراجع .NET API
description: استبدل الارتباطات التشعبية في مستندات Word باستخدام Aspose.Words for .NET. إرشادات خطوة بخطوة لاستبدال الارتباطات التشعبية.
type: docs
weight: 10
url: /fr/net/working-with-fields/replace-hyperlinks/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح التعليمات البرمجية المصدر C # التالية لاستبدال الارتباطات التشعبية باستخدام Aspose.Words لوظائف .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: تعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 تأكد من تحديد المسار الصحيح إلى دليل المستندات الذي يحتوي على ملحق`Hyperlinks.docx` ملف.

## الخطوة 2: قم بتحميل المستند الذي يحتوي على الارتباطات التشعبية

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 نحن هنا بصدد إنشاء مثيل لـ`Document` فئة من الملف المحدد.

## الخطوة 3: تصفح الحقول للعثور على الارتباطات التشعبية

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // قد تكون بعض الارتباطات التشعبية محلية (روابط للإشارات المرجعية داخل المستند) ، ونحن نتجاهلها.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com "؛
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 تمر هذه الحلقة عبر جميع الحقول في المستند بحثًا عن حقول النوع`FieldType.FieldHyperlink` . بمجرد العثور على حقل من هذا النوع ، نتحقق مما إذا كان رابطًا محليًا عن طريق التحقق من`SubAddress` ملكية. إذا لم يكن كذلك ، فإننا نستبدل عنوان الارتباط بـ`"http://www.aspose.com"`والنتيجة مع`"Aspose - The .NET & Java Component Editor"`.

## الخطوة 4: احفظ المستند المعدل

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

أخيرًا ، نحفظ المستند المعدل بالارتباطات التشعبية المستبدلة في ملف محدد.

### مثال على شفرة المصدر لاستبدال الارتباطات التشعبية بـ Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // قد تكون بعض الارتباطات التشعبية محلية (روابط للإشارات المرجعية داخل المستند) ، ونحن نتجاهلها.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com "؛
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

هذا نموذج لشفرة مصدر لاستبدال الارتباطات التشعبية في مستند باستخدام Aspose.Words for .NET.
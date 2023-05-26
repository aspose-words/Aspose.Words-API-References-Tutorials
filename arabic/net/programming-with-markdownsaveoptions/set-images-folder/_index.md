---
title: تعيين مجلد الصور
linktitle: تعيين مجلد الصور
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين مجلد الصور عند التصدير إلى Markdown باستخدام Aspose.Words for .NET. تخصيص موضع الصور من أجل تنظيم وتكامل أفضل.
type: docs
weight: 10
url: /ar/net/programming-with-markdownsaveoptions/set-images-folder/
---

فيما يلي دليل خطوة بخطوة لشرح الكود المصدري C # التالي والذي يساعد على تعيين مجلد الصور لخيارات تصدير Markdown باستخدام مكتبة Aspose.Words لـ .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: تعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك حيث يوجد المستند الذي يحتوي على الصور.

## الخطوة 2: قم بتحميل المستند الذي يحتوي على الصور

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

نقوم بتحميل المستند المحدد الذي يحتوي على الصور التي نريد تصديرها باستخدام خيارات Markdown.

## الخطوة 3: قم بتعيين مجلد الصور لخيارات تصدير Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 نقوم بإنشاء مثيل`MarkdownSaveOptions` وقم بتعيين المسار إلى مجلد الصور باستخدام ملف`ImagesFolder` ملكية. تأكد من تحديد المسار الصحيح للمجلد حيث تريد حفظ الصور المصدرة.

## الخطوة 4: احفظ المستند باستخدام خيارات تصدير Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

نقوم بحفظ المستند في تدفق الذاكرة باستخدام خيارات تصدير Markdown المحددة. يمكنك بعد ذلك استخدام التدفق لإجراء عمليات أخرى ، مثل حفظ محتوى Markdown في ملف.

### مثال على كود المصدر لتعيين مجلد الصور لـ MarkdownSaveOptions مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

يوضح رمز المصدر هذا كيفية تحميل مستند يحتوي على صور ثم تعيين مجلد الصور لخيارات تصدير Markdown. باستخدام الخيارات المحددة ، يتم حفظ المستند بعد ذلك في تدفق الذاكرة. يتيح لك هذا تخصيص موقع مجلد الصور عند تصدير محتوى Markdown.
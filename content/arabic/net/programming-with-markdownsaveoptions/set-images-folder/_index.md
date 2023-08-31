---
title: تعيين مجلد الصور
linktitle: تعيين مجلد الصور
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين مجلد الصور عند التصدير إلى Markdown باستخدام Aspose.Words لـ .NET. قم بتخصيص موضع الصور لتحسين التنظيم والتكامل.
type: docs
weight: 10
url: /ar/net/programming-with-markdownsaveoptions/set-images-folder/
---

فيما يلي دليل خطوة بخطوة لشرح كود مصدر C# التالي والذي يساعد في تعيين مجلد الصور لخيارات تصدير Markdown باستخدام مكتبة Aspose.Words لـ .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: قم بتعيين مسار دليل المستند

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

 نقوم بإنشاء مثيل لـ`MarkdownSaveOptions` وقم بتعيين المسار إلى مجلد الصور باستخدام`ImagesFolder` ملكية. تأكد من تحديد المسار الصحيح للمجلد الذي تريد حفظ الصور المصدرة فيه.

## الخطوة 4: احفظ المستند باستخدام خيارات تصدير Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

نقوم بحفظ المستند في تدفق الذاكرة باستخدام خيارات تصدير Markdown المحددة. يمكنك بعد ذلك استخدام التدفق لإجراء عمليات أخرى، مثل حفظ محتوى Markdown في ملف.

### مثال على التعليمات البرمجية المصدر لتعيين مجلد الصور لـ MarkdownSaveOptions باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

يوضح كود المصدر هذا كيفية تحميل مستند يحتوي على صور ثم تعيين مجلد الصور لخيارات تصدير Markdown. باستخدام الخيارات المحددة، يتم بعد ذلك حفظ المستند في تدفق الذاكرة. يتيح لك هذا تخصيص موقع مجلد الصور عند تصدير محتوى Markdown.
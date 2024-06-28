---
title: تعيين مجلد الخطوط
linktitle: تعيين مجلد الخطوط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين دليل الخطوط في Aspose.Words لـ .NET والتأكد من توفر الخطوط المستخدمة في مستنداتك.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-fonts-folder/
---
سنوضح لك في هذا البرنامج التعليمي كيفية تعيين دليل الخطوط في Aspose.Words لـ .NET. سوف تتعلم كيفية تحديد الدليل الذي يحتوي على الخطوط المستخدمة في مستند Word الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
ابدأ بتعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تعيين دليل الخطوط
 إنشاء مثيل لـ`FontSettings` الصف واستخدام`SetFontsFolder` طريقة لتحديد الدليل الذي يحتوي على الخطوط. يستبدل`"Fonts"` مع اسم دليل الخطوط الفعلي.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## الخطوة 3: قم بتحميل المستند بإعدادات الخط
 استخدم ال`LoadOptions` فئة لتحديد إعدادات الخط في`FontSettings` خيار. ثم استخدم`Document` class لتحميل المستند باستخدام هذه الخيارات.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### نموذج التعليمات البرمجية المصدر لمجلد Set Fonts باستخدام Aspose.Words لـ .NET 

```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## خاتمة
تهنئة ! أنت تعرف الآن كيفية تعيين دليل الخطوط في Aspose.Words لـ .NET. يمكنك استخدام هذه الميزة للتأكد من توفر الخطوط المستخدمة في المستند الخاص بك ولضمان الاتساق في عرض الخطوط.

### الأسئلة الشائعة

#### س: كيف يمكنني تعيين مجلد خط مخصص في Aspose.Words؟

 ج: لتعيين مجلد خطوط مخصص في Aspose.Words، يمكنك استخدام ملف`FontsFolder` الطبقة و`SetFontsFolders` طريقة تحديد المسار إلى المجلد الذي يحتوي على الخطوط الخاصة بك.

#### س: هل يمكنني تعيين مجلدات خطوط متعددة في Aspose.Words؟

 ج: نعم، يمكنك تعيين مجلدات خطوط متعددة في Aspose.Words عن طريق استدعاء`SetFontsFolders` الطريقة عدة مرات باستخدام مسارات مجلدات الخطوط المختلفة التي تريد استخدامها.

#### س: ماذا يحدث إذا كان الخط المستخدم في المستند غير موجود في مجلدات الخطوط المحددة؟

ج: إذا لم يكن الخط المستخدم في المستند موجودًا في مجلدات الخطوط المحددة في Aspose.Words، فسيتم استخدام خط بديل بدلاً من ذلك. وهذا يضمن أن النص الموجود في المستند سيتم عرضه دائمًا بشكل صحيح، حتى إذا لم يكن الخط الأصلي متاحًا.

#### س: هل تتمتع مجلدات الخطوط المحددة في Aspose.Words بالأولوية على الخطوط المثبتة على النظام؟

ج: نعم، مجلدات الخطوط المحددة في Aspose.Words لها الأسبقية على الخطوط المثبتة على النظام. وهذا يعني أنه في حالة وجود خط يحمل نفس الاسم في مجلدات الخطوط المحددة وفي خطوط النظام، فسيتم استخدام الإصدار الموجود في مجلد الخطوط عند معالجة مستندات Word.
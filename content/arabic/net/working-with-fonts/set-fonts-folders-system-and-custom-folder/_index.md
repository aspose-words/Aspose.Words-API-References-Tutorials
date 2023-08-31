---
title: ضبط نظام مجلدات الخطوط والمجلد المخصص
linktitle: ضبط نظام مجلدات الخطوط والمجلد المخصص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد مجلدات النظام والخطوط المخصصة عند عرض مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتعيين مجلدات خطوط النظام ومجلد مخصص عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي، ستعرف كيفية تحديد مجلدات الخطوط المتعددة، بما في ذلك مجلد النظام والمجلد المخصص، لاستخدامها عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو الموقع الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند لعرضه
 ثم يمكنك تحميل المستند لعرضه باستخدام ملف`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: قم بتعيين مجلدات النظام والخطوط المخصصة
 يمكنك الآن تعيين مجلدات خطوط النظام ومجلد مخصص باستخدام المجلد`FontSettings` الطبقة و`SetFontsSources()` طريقة. أولاً، تحتاج إلى استرداد قائمة مصادر الخطوط المعتمدة على البيئة باستخدام`GetFontsSources()` وتخزينها في القائمة. ثم يمكنك إنشاء مثيل جديد لـ`FolderFontSource` تحديد المسار إلى المجلد المخصص الذي يحتوي على الخطوط الخاصة بك. أضف هذا المثيل إلى قائمة مصادر الخطوط الموجودة. وأخيرا، استخدم`SetFontsSources()` لتحديث مصادر الخطوط بالقائمة الجديدة.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## الخطوة 4: تطبيق إعدادات الخط
 بعد ذلك، تحتاج إلى تطبيق إعدادات الخط على المستند الخاص بك باستخدام`FontSettings` ملكية`Document` فصل.

```csharp
doc.FontSettings = fontSettings;
```

## الخطوة 5: احفظ المستند المقدم
وأخيرا، يمكنك حفظ المستند المقدم إلى ملف عن طريق

   باستخدام`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### نموذج التعليمات البرمجية المصدر لنظام تعيين الخطوط والمجلدات والمجلدات المخصصة باستخدام Aspose.Words لـ .NET 

```csharp
//المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// استرداد مجموعة مصادر الخطوط المعتمدة على البيئة والتي يتم البحث عنها بشكل افتراضي.
// على سبيل المثال، سيحتوي هذا على مصدر "Windows\Fonts\" على أجهزة Windows.
// نضيف هذه المصفوفة إلى قائمة جديدة لتسهيل إضافة إدخالات الخطوط أو إزالتها.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// قم بإضافة مصدر مجلد جديد والذي سيوجه Aspose.Words للبحث في المجلد التالي عن الخطوط.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// أضف المجلد المخصص الذي يحتوي على خطوطنا إلى قائمة مصادر الخطوط الموجودة.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعيين مجلدات خطوط النظام ومجلد مخصص عند عرض مستند باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل التفصيلي، يمكنك بسهولة تحديد مجلدات خطوط متعددة، بما في ذلك مجلد النظام والمجلد المخصص، لاستخدامها عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات باستخدام الخطوط الموجودة في مستنداتك. باستخدام هذه المعرفة، يمكنك التحكم في مصادر الخطوط المستخدمة وتخصيصها عند عرض مستنداتك وفقًا لاحتياجاتك المحددة.

### الأسئلة الشائعة

#### س: كيف يمكنني ضبط مجلدات خطوط النظام في Aspose.Words؟

ج: لتعيين مجلدات خطوط النظام في Aspose.Words، ليس عليك القيام بأي شيء. يستخدم Aspose.Words خطوط النظام المثبتة على نظام التشغيل الخاص بك تلقائيًا.

#### س: كيف يمكنني تعيين مجلدات الخطوط المخصصة في Aspose.Words؟

 ج: لتعيين مجلدات الخطوط المخصصة في Aspose.Words، يمكنك استخدام`SetFontsFolders` طريقة`Fonts` فئة تحدد مواقع مجلدات الخطوط المخصصة.

#### س: هل يمكنني تحديد عدة مجلدات خطوط مخصصة في Aspose.Words؟

 ج: نعم، يمكنك تحديد عدة مجلدات خطوط مخصصة في Aspose.Words باستخدام الملف`SetFontsFolders` طريقة`Fonts` فئة مع قائمة مواقع المجلدات.

#### س: كيف يمكنني التحقق من مجلدات الخطوط المحددة في Aspose.Words؟

 للتحقق من مجلدات الخطوط المحددة في Aspose.Words، يمكنك استخدام الملف`GetFolders` طريقة`Fonts` class للحصول على قائمة مجلدات الخطوط التي تم تكوينها.

#### س: هل خطوط المجلدات المخصصة لها الأولوية على خطوط النظام في Aspose.Words؟

ج: نعم، خطوط المجلدات المخصصة لها الأولوية على خطوط النظام في Aspose.Words. في حالة وجود خط في كل من المجلدات المخصصة وخطوط النظام، فسيستخدم Aspose.Words الإصدار من المجلد المخصص.
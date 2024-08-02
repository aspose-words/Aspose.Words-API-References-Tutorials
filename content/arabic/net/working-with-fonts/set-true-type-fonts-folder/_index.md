---
title: قم بتعيين مجلد خطوط النوع الحقيقي
linktitle: قم بتعيين مجلد خطوط النوع الحقيقي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإعداد مجلد خطوط النوع الحقيقي عند عرض مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-true-type-fonts-folder/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لتعيين مجلد خطوط النوع الحقيقي عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية تحديد مجلد مخصص يحتوي على خطوط True Type لاستخدامه عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو الموقع الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند لعرضه
 بعد ذلك، تحتاج إلى تحميل المستند لعرضه باستخدام ملف`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تعيين مجلد خطوط النوع الحقيقي
يمكنك الآن تحديد مجلد الخطوط من النوع الحقيقي لاستخدامه عند العرض عن طريق إنشاء مثيل لـ`FontSettings` الصف واستخدام`SetFontsFolder()` طريقة ضبط مجلد الخطوط يمكنك تحديد مجلد مخصص يحتوي على خطوط True Type الخاصة بك. المعلمة الثانية ل`SetFontsFolder()` يشير إلى ما إذا كنت تريد البحث في المجلدات الفرعية للمجلد المحدد أيضًا.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## الخطوة 4: احفظ المستند المقدم
 وأخيرًا، يمكنك حفظ المستند الذي تم عرضه في ملف باستخدام الملف`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Set True Type Fonts Folder باستخدام Aspose.Words لـ .NET 

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// لاحظ أن هذا الإعداد سيتجاوز أي مصادر خطوط افتراضية يتم البحث عنها بشكل افتراضي. الآن سيتم البحث عن هذه المجلدات فقط
// الخطوط عند تقديم الخطوط أو تضمينها. لإضافة مصدر خط إضافي مع الاحتفاظ بمصادر خطوط النظام، استخدم كلاً من FontSettings.GetFontSources و
// FontSettings.SetFontSources بدلاً من ذلك
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// ضبط إعدادات الخط
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية تعيين مجلد الخطوط من النوع الحقيقي عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل خطوة بخطوة، يمكنك بسهولة تحديد مجلد مخصص يحتوي على خطوط True Type لاستخدامه عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الكلمات باستخدام الخطوط الموجودة في مستنداتك. باستخدام هذه المعرفة، يمكنك التحكم في الخطوط المستخدمة وتخصيصها عند عرض مستنداتك وفقًا لاحتياجاتك المحددة.

### الأسئلة الشائعة

#### س: كيف يمكنني تكوين مجلد خطوط TrueType في Aspose.Words؟

 ج: لتكوين مجلد خطوط TrueType في Aspose.Words، يمكنك استخدام`SetTrueTypeFontsFolder` طريقة`Fonts` فئة تحدد موقع المجلد الذي يحتوي على خطوط TrueType.

#### س: ما أنواع الخطوط التي تعتبر خطوط TrueType؟

ج: خطوط TrueType هي تنسيق خطوط شائع. يتم استخدامها غالبًا في مستندات Word ولها ملحق ملف .ttf أو .ttc.

#### س: هل يمكنني تحديد مجلدات خطوط TrueType متعددة في Aspose.Words؟

ج: نعم، يمكنك تحديد مجلدات خطوط TrueType متعددة في Aspose.Words باستخدام الملف`SetTrueTypeFontsFolder` طريقة`Fonts` فئة مع قائمة مواقع المجلدات.

#### س: كيف يمكنني التحقق من مجلد خطوط TrueType الذي تم تكوينه في Aspose.Words؟

 ج: للتحقق من مجلد خطوط TrueType الذي تم تكوينه في Aspose.Words، يمكنك استخدام الملف`GetTrueTypeFontsFolder` طريقة`Fonts` للحصول على موقع مجلد TrueType Fonts الذي تم تكوينه.

#### س: لماذا من المهم تكوين مجلد خطوط TrueType في Aspose.Words؟

ج: يعد إعداد مجلد خطوط TrueType في Aspose.Words أمرًا مهمًا لأنه يساعد Aspose.Words في تحديد الخطوط المطلوبة عند معالجة مستندات Word. وهذا يضمن الاتساق في تنسيق المستند ومظهره، حتى عبر الأنظمة المختلفة.
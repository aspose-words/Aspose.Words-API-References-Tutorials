---
title: تعيين مجلد خطوط النوع الحقيقي
linktitle: تعيين مجلد خطوط النوع الحقيقي
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لإعداد مجلد خطوط الكتابة الصحيحة عند تقديم مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-true-type-fonts-folder/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين مجلد خطوط الكتابة الحقيقية عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد مجلد مخصص يحتوي على خطوط True Type لاستخدامه عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند للعرض
 بعد ذلك ، تحتاج إلى تحميل المستند لتقديمه باستخدام امتداد`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تعيين مجلد خطوط True Type
يمكنك الآن تحديد مجلد خطوط الكتابة الحقيقية لاستخدامها عند التقديم عن طريق إنشاء مثيل لملف`FontSettings` الطبقة واستخدام`SetFontsFolder()` طريقة لتعيين مجلد الخطوط. يمكنك تحديد مجلد مخصص يحتوي على خطوط True Type الخاصة بك. المعلمة الثانية ل`SetFontsFolder()` يشير إلى ما إذا كنت تريد البحث في المجلدات الفرعية للمجلد المحدد أيضًا.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## الخطوة 4: احفظ المستند المقدم
 أخيرًا ، يمكنك حفظ المستند الذي تم تقديمه في ملف باستخدام امتداد`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Set True Type Fonts Folder باستخدام Aspose.Words for .NET 

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// لاحظ أن هذا الإعداد سيتجاوز أي مصادر افتراضية للخطوط يتم البحث عنها افتراضيًا. الآن سيتم البحث عن هذه المجلدات فقط
// الخطوط عند تقديم الخطوط أو دمجها. لإضافة مصدر خط إضافي مع الاحتفاظ بمصادر خطوط النظام ، استخدم كلاً من FontSettings.GetFontSources و
// FontSettings.SetFontSources بدلاً من ذلك
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// ضبط إعدادات الخط
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين مجلد خطوط الكتابة الحقيقية عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تحديد مجلد مخصص يحتوي على خطوط True Type لاستخدامها عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة للعمل مع الخطوط في مستنداتك. باستخدام هذه المعرفة ، يمكنك التحكم في الخطوط المستخدمة وتخصيصها عند تقديم مستنداتك وفقًا لاحتياجاتك الخاصة.

### التعليمات

#### س: كيف يمكنني تكوين مجلد خطوط TrueType في Aspose.Words؟

 ج: لتهيئة مجلد خطوط TrueType في Aspose.Words ، يمكنك استخدام ملف`SetTrueTypeFontsFolder` طريقة`Fonts` فئة تحدد موقع المجلد الذي يحتوي على خطوط تروتايب.

#### س: ما أنواع الخطوط التي تعتبر خطوط TrueType؟

ج: خطوط TrueType هي تنسيق خط شائع. غالبًا ما يتم استخدامها في مستندات Word ولها امتداد ملف ttf. أو ttc.

#### س: هل يمكنني تحديد عدة مجلدات خطوط TrueType في Aspose.Words؟

ج: نعم ، يمكنك تحديد عدة مجلدات لخط TrueType في Aspose`SetTrueTypeFontsFolder` طريقة`Fonts` فئة مع قائمة بمواقع المجلدات.

#### س: كيف يمكنني التحقق من مجلد خطوط TrueType الذي تم تكوينه في Aspose.Words؟

 ج: للتحقق من مجلد خطوط TrueType الذي تم تكوينه في Aspose.Words ، يمكنك استخدام ملف`GetTrueTypeFontsFolder` طريقة`Fonts` للحصول على موقع مجلد خطوط TrueType الذي تم تكوينه.

#### س: ما سبب أهمية تكوين مجلد خطوط TrueType في Aspose.Words؟

ج: يعد إعداد مجلد خطوط TrueType في Aspose.Words أمرًا مهمًا لأنه يساعد Aspose.Words بتحديد موقع الخطوط المطلوبة عند معالجة مستندات Word. يضمن ذلك التناسق في تنسيق المستند ومظهره ، حتى عبر الأنظمة المختلفة.
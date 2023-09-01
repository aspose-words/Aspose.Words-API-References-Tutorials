---
title: احصل على الاستبدال بدون اللواحق
linktitle: احصل على الاستبدال بدون اللواحق
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: في هذا البرنامج التعليمي، تعرف على كيفية الحصول على تجاوزات بدون لاحقات في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/get-substitution-without-suffixes/
---

سنوضح لك في هذا البرنامج التعليمي كيفية الحصول على التجاوزات بدون اللواحق في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. تُستخدم البدائل التي لا تحتوي على لاحقات لحل مشكلات استبدال الخط عند عرض المستندات أو طباعتها. سنأخذك خطوة بخطوة لمساعدتك على فهم التعليمات البرمجية وتنفيذها في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
 أولاً، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وتكوين البدائل بدون لاحقات
 بعد ذلك، سنقوم بتحميل المستند باستخدام ملف`Document` فئة وتكوين بدائل بدون لاحقات باستخدام`DocumentSubstitutionWarnings` فصل. سنقوم أيضًا بإضافة مصدر الخط عن طريق تحديد مجلد يحتوي على الخطوط.

```csharp
// قم بتحميل المستند وقم بتكوين البدائل بدون لاحقات
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## الخطوة 3: احفظ المستند
وأخيرًا، سنقوم بحفظ المستند مع تطبيق التجاوزات بدون لاحقة.

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### نموذج التعليمات البرمجية المصدر للحصول على الاستبدال بدون لاحقات باستخدام Aspose.Words لـ .NET 
```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## خاتمة
في هذا البرنامج التعليمي، رأينا كيفية الحصول على التجاوزات بدون اللواحق في مستند Word باستخدام Aspose.Words لـ .NET. تعتبر الاستبدالات بدون اللواحق مفيدة في حل مشكلات استبدال الخط. لا تتردد في استخدام هذه الميزة لتحسين عرض وطباعة المستندات الخاصة بك.

### الأسئلة الشائعة

#### س: لماذا يقوم Aspose.Words بإضافة لاحقات لبدائل الخطوط؟

ج: يقوم Aspose.Words بإضافة لاحقات إلى بدائل الخطوط لتجنب التعارضات بين الخطوط الأصلية والخطوط البديلة. ويساعد هذا على ضمان أقصى قدر من التوافق عند تحويل المستندات ومعالجتها.

#### س: كيف يمكنني استرداد بدائل الخطوط بدون لاحقات في Aspose.Words؟

 ج: لاسترداد بدائل الخطوط بدون اللواحق في Aspose.Words، يمكنك استخدام`FontSubstitutionSettings` الطبقة و`RemoveSuffixes` ملكية. تعيين هذه الخاصية إلى`true` سيحصل على بدائل الخطوط بدون اللواحق المضافة.

#### س: هل من الممكن تعطيل إضافة لاحقات لبدائل الخطوط في Aspose.Words؟

ج: لا، ليس من الممكن تعطيل إضافة لاحقات لبدائل الخطوط في Aspose.Words. تتم إضافة اللواحق بشكل افتراضي لضمان توافق الوثيقة واتساقها.

#### س: كيف يمكنني تصفية اللواحق غير المرغوب فيها في بدائل الخطوط في Aspose.Words؟

 ج: لتصفية اللواحق غير المرغوب فيها في بدائل الخطوط في Aspose.Words، يمكنك استخدام تقنيات معالجة السلسلة، مثل استخدام`Replace` أو`Substring` طرق لإزالة لاحقات معينة لا تريد تضمينها.
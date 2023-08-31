---
title: احصل على استبدال بدون لاحقات
linktitle: احصل على استبدال بدون لاحقات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: في هذا البرنامج التعليمي ، تعرف على كيفية الحصول على تجاوزات غير لاحقة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/get-substitution-without-suffixes/
---

في هذا البرنامج التعليمي ، سوف نوضح لك كيفية الحصول على التجاوزات بدون اللواحق في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. تُستخدم البدائل بدون لاحقات لحل مشاكل استبدال الخط عند عرض المستندات أو طباعتها. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وتكوين الاستبدالات بدون لاحقات
 بعد ذلك ، سنقوم بتحميل المستند باستخدام ملف`Document` فئة وتكوين بدائل غير لاحقة باستخدام`DocumentSubstitutionWarnings` فصل. سنضيف أيضًا مصدر خط عن طريق تحديد مجلد يحتوي على الخطوط.

```csharp
// قم بتحميل المستند وتكوين الاستبدالات بدون لاحقات
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
أخيرًا ، سنحفظ المستند مع تطبيق التجاوزات بدون لاحقة.

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### عينة من التعليمات البرمجية المصدر للحصول على استبدال بدون لاحقات باستخدام Aspose.Words for .NET 
```csharp

//المسار إلى دليل المستند الخاص بك
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
في هذا البرنامج التعليمي ، رأينا كيفية الحصول على الإلغاءات بدون اللواحق في مستند Word باستخدام Aspose.Words for .NET. الاستبدالات بدون لاحقات مفيدة لحل مشاكل استبدال الخط. لا تتردد في استخدام هذه الميزة لتحسين عرض وطباعة مستنداتك.

### التعليمات

#### س: لماذا يضيف Aspose.Words لاحقات لاستبدال الخطوط؟

ج: يضيف Aspose.Words لاحقات لاستبدال الخطوط لتجنب التعارض بين الخطوط الأصلية والخطوط المستبدلة. يساعد ذلك في ضمان أقصى قدر من التوافق عند تحويل المستندات ومعالجتها.

#### س: كيف يمكنني استرجاع استبدالات الخطوط بدون لاحقات في Aspose.Words؟

 ج: لاسترداد استبدالات الخط بدون لاحقات في Aspose.Words ، يمكنك استخدام`FontSubstitutionSettings` الطبقة و`RemoveSuffixes` ملكية. تعيين هذه الخاصية إلى`true` سيحصل على استبدالات الخط بدون اللواحق المضافة.

#### س: هل من الممكن تعطيل إضافة اللواحق لاستبدال الخطوط في Aspose.Words؟

ج: لا ، ليس من الممكن تعطيل إضافة اللواحق لاستبدال الخطوط في Aspose.Words. تتم إضافة اللواحق افتراضيًا لضمان توافق المستندات واتساقها.

#### س: كيف يمكنني تصفية اللواحق غير المرغوب فيها في استبدالات الخطوط في Aspose.Words؟

 ج: لتصفية اللواحق غير المرغوب فيها في استبدالات الخطوط في Aspose.Words ، يمكنك استخدام تقنيات معالجة السلاسل ، مثل استخدام`Replace` أو`Substring` طرق لإزالة لاحقات معينة لا تريد تضمينها.
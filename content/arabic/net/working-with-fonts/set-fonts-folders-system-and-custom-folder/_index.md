---
title: ضبط نظام مجلدات الخطوط والمجلد المخصص
linktitle: ضبط نظام مجلدات الخطوط والمجلد المخصص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين مجلدات النظام والخطوط المخصصة في مستندات Word باستخدام Aspose.Words لـ .NET، مما يضمن عرض مستنداتك بشكل صحيح عبر بيئات مختلفة.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## مقدمة

تخيل أنك تقوم بصياغة مستند بنمط خط فريد، ثم تكتشف أن الخطوط لا يتم عرضها بشكل صحيح على جهاز آخر. محبط ، أليس كذلك؟ هذا هو المكان الذي يلعب فيه تكوين مجلدات الخطوط. باستخدام Aspose.Words for .NET، يمكنك تحديد مجلدات النظام والخطوط المخصصة لضمان ظهور مستنداتك دائمًا على النحو المنشود. دعونا نتعمق في كيفية تحقيق ذلك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

-  Aspose.Words for .NET Library: إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيله[هنا](https://releases.aspose.com/words/net/).
- بيئة التطوير: بيئة تطوير متكاملة (IDE) مثل Visual Studio.
- المعرفة الأساسية بـ C#: الإلمام بـ C# سيساعدك على متابعة أمثلة التعليمات البرمجية.

## استيراد مساحات الأسماء

أولاً، قم باستيراد مساحات الأسماء الضرورية في مشروعك:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

الآن، دعونا نقسم العملية إلى خطوات بسيطة.

## الخطوة 1: قم بتحميل المستند

 للبدء، قم بتحميل مستند Word الخاص بك إلى Aspose.Words`Document` هدف. سيكون هذا المستند هو المستند الذي تريد تعيين مجلدات الخطوط فيه.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 2: تهيئة إعدادات الخط

 إنشاء مثيل جديد ل`FontSettings`. سيسمح لك هذا الكائن بإدارة مصادر الخطوط.

```csharp
FontSettings fontSettings = new FontSettings();
```

## الخطوة 3: استرداد مصادر خطوط النظام

استرداد مصادر خطوط النظام الافتراضية. على جهاز يعمل بنظام التشغيل Windows، يتضمن هذا عادةً الملف "Windows\Fonts\"الدليل.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## الخطوة 4: إضافة مجلد خط مخصص

قم بإضافة مجلد مخصص يحتوي على الخطوط الإضافية الخاصة بك. يعد هذا مفيدًا إذا كان لديك خطوط معينة غير مثبتة في دليل خطوط النظام.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## الخطوة 5: تحديث مصادر الخطوط

 قم بتحويل قائمة مصادر الخطوط مرة أخرى إلى مصفوفة وقم بتعيينها على`FontSettings` هدف.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## الخطوة 6: تطبيق إعدادات الخط على المستند

 أخيرًا، قم بتطبيق التكوين`FontSettings` إلى المستند الخاص بك وحفظه بالتنسيق الذي تريده، مثل PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## خاتمة

وهنا لديك! باتباع هذه الخطوات، يمكنك التأكد من أن مستندات Word الخاصة بك تستخدم الخطوط الصحيحة، سواء كانت خطوط نظام أو خطوط مخصصة مخزنة في دليل محدد. يساعد هذا الإعداد في الحفاظ على سلامة مظهر مستندك عبر بيئات مختلفة.

## الأسئلة الشائعة

### ماذا يحدث إذا كان الخط مفقودًا في مجلدات النظام والمجلدات المخصصة؟

سيستخدم Aspose.Words خطًا افتراضيًا لاستبدال الخط المفقود، مما يضمن بقاء المستند قابلاً للقراءة.

### هل يمكنني إضافة عدة مجلدات خطوط مخصصة؟

 نعم، يمكنك إضافة عدة مجلدات خطوط مخصصة عن طريق تكرار عملية الإنشاء`FolderFontSource` الكائنات وإضافتها إلى قائمة مصادر الخطوط.

### هل من الممكن استخدام مسارات الشبكة لمجلدات الخطوط المخصصة؟

 نعم، يمكنك تحديد مسار الشبكة في`FolderFontSource` منشئ.

### ما هي تنسيقات الملفات التي يدعمها Aspose.Words لحفظ المستندات؟

يدعم Aspose.Words العديد من التنسيقات، بما في ذلك DOCX وPDF وHTML والمزيد.

### كيف أتعامل مع إشعارات استبدال الخط؟

 يمكنك التعامل مع إشعارات استبدال الخط باستخدام`FontSettings` الطبقة`FontSubstitutionWarning`حدث.
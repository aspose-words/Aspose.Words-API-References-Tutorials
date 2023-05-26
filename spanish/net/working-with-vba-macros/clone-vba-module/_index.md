---
title: وحدة استنساخ Vba
linktitle: وحدة استنساخ Vba
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية استنساخ وحدة VBA من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/working-with-vba-macros/clone-vba-module/
---

في هذا البرنامج التعليمي ، سنخبرك بكيفية استنساخ وحدة VBA من مستند Word باستخدام وحدات ماكرو باستخدام مكتبة Aspose.Words لـ .NET. يسمح لك استنساخ وحدة VBA النمطية بإعادة استخدام أو نسخ كود VBA من مستند مصدر إلى مستند آخر. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك
- مستند Word يحتوي على مشروع VBA مع الوحدة النمطية التي تريد استنساخها

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل مستند المصدر
بعد ذلك ، سنقوم بتحميل مستند Word المصدر ، والذي يحتوي على مشروع VBA والوحدة التي نريد استنساخها.

```csharp
// قم بتحميل المستند المصدر
Document doc = new Document(dataDir + "VBA project.docm");
```

## الخطوة 3: قم بإنشاء مستند جديد باستخدام مشروع VBA واستنساخ الوحدة النمطية
سننشئ مستندًا جديدًا بمشروع VBA فارغ وننسخ الوحدة المحددة من المستند المصدر.

```csharp
// قم بإنشاء مستند جديد بمشروع VBA فارغ
Document destDoc = new Document { VbaProject = new VbaProject() };

// استنساخ الوحدة
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## الخطوة 4: احفظ المستند الوجهة
أخيرًا ، سنحفظ المستند الوجهة مع وحدة VBA المستنسخة في ملف.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### نموذج لشفرة مصدر لـ Clone Vba Module باستخدام Aspose.Words for .NET 
```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية استنساخ وحدة VBA من مستند Word باستخدام وحدات ماكرو باستخدام Aspose.Words for .NET. يسمح لك نسخ وحدات VBA النمطية بإعادة استخدام تعليمات VBA البرمجية بسهولة من مستند مصدر واحد في مستند آخر. لا تتردد في استخدام هذه الميزة لتنظيم وإدارة وحدات الماكرو الخاصة بك في مستندات مختلفة.

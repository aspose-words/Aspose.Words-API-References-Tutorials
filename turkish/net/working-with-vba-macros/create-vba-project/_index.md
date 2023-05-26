---
title: قم بإنشاء مشروع Vba
linktitle: قم بإنشاء مشروع Vba
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية إنشاء مشروع VBA في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-vba-macros/create-vba-project/
---

في هذا البرنامج التعليمي ، سنخبرك بكيفية إنشاء مشروع VBA في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يتيح لك إنشاء مشروع VBA إضافة رمز VBA مخصص إلى مستند Word الخاص بك. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

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

## الخطوة 2: قم بإنشاء مستند ومشروع VBA جديدين
 بعد ذلك ، سننشئ مستندًا جديدًا عن طريق إنشاء مثيل لملف`Document` فئة ومشروع VBA فارغ عن طريق إنشاء مثيل`VbaProject` فصل.

```csharp
// قم بإنشاء مستند جديد
Document doc = new Document();

// قم بإنشاء مشروع VBA جديد
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## الخطوة 3: إنشاء وحدة نمطية جديدة وتحديد شفرة مصدر الماكرو
 سننشئ وحدة نمطية جديدة عن طريق إنشاء مثيل لملف`VbaModule` فئة وتحديد اسم الماكرو ونوع (وحدة إجرائية) وكود المصدر.

```csharp
// قم بإنشاء وحدة جديدة
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// أضف الوحدة النمطية إلى مشروع VBA
doc.VbaProject.Modules.Add(module);
```

## الخطوة 4: احفظ المستند
أخيرًا ، سنحفظ المستند مع مشروع VBA الذي تم إنشاؤه في ملف.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### نموذج التعليمات البرمجية المصدر لـ Create Vba Project باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// إنشاء وحدة نمطية جديدة وتحديد شفرة مصدر الماكرو.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// أضف وحدة إلى مشروع VBA.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية إنشاء مشروع VBA في مستند Word باستخدام Aspose.Words for .NET. يتيح لك إنشاء مشروع VBA إضافة رمز VBA وتخصيصه في مستند Word الخاص بك. لا تتردد في استخدام هذه الميزة لأتمتة المهام أو إضافة وظائف مخصصة إلى مستندات Word الخاصة بك.

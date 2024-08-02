---
title: استخدام أجزاء المهام الخاصة بملحق الويب
linktitle: استخدام أجزاء المهام الخاصة بملحق الويب
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إضافة أجزاء مهام ملحق الويب وتكوينها في مستندات Word باستخدام Aspose.Words لـ .NET في هذا البرنامج التعليمي التفصيلي خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-webextension/using-web-extension-task-panes/
---
## مقدمة

مرحبًا بك في هذا البرنامج التعليمي المتعمق حول استخدام أجزاء مهام ملحق الويب في مستند Word باستخدام Aspose.Words for .NET. إذا كنت ترغب في تحسين مستندات Word الخاصة بك باستخدام أجزاء المهام التفاعلية، فأنت في المكان الصحيح. سيرشدك هذا الدليل خلال كل خطوة لتحقيق ذلك بسلاسة.

## المتطلبات الأساسية

قبل أن نتعمق، دعونا نتأكد من أن لديك كل ما تحتاجه:

-  Aspose.Words لـ .NET: يمكنك تنزيله[هنا](https://releases.aspose.com/words/net/).
- بيئة تطوير .NET: Visual Studio أو أي بيئة تطوير متكاملة أخرى تفضلها.
- المعرفة الأساسية بـ C#: سيساعدك هذا على متابعة أمثلة التعليمات البرمجية.
-  ترخيص Aspose.Words: يمكنك شراء واحدة[هنا](https://purchase.aspose.com/buy) أو الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).

## استيراد مساحات الأسماء

قبل أن نبدأ بالبرمجة، تأكد من استيراد مساحات الأسماء التالية في مشروعك:

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## دليل خطوة بخطوة

الآن، دعونا نقسم العملية إلى خطوات سهلة المتابعة.

### الخطوة 1: إعداد دليل المستندات الخاص بك

أول الأشياء أولاً، نحتاج إلى إعداد المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي سيتم فيه حفظ مستند Word الخاص بك.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى مجلد المستندات الخاص بك.

### الخطوة 2: إنشاء مستند جديد

بعد ذلك، سنقوم بإنشاء مستند Word جديد باستخدام Aspose.Words.

```csharp
Document doc = new Document();
```

 يقوم هذا السطر بتهيئة مثيل جديد لـ`Document` فئة تمثل مستند Word.

### الخطوة 3: إضافة جزء المهام

الآن، سنقوم بإضافة جزء المهام إلى وثيقتنا. تعد أجزاء المهام مفيدة لتوفير وظائف وأدوات إضافية داخل مستند Word.

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

 هنا نقوم بإنشاء جديد`TaskPane` كائن وإضافته إلى المستند`WebExtensionTaskPanes` مجموعة.

### الخطوة 4: تكوين جزء المهام

لجعل جزء المهام مرئيًا وتعيين خصائصه، نستخدم الكود التالي:

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState` يحدد المكان الذي سيظهر فيه جزء المهام. في هذه الحالة، هو على اليمين.
- `IsVisible` يضمن أن جزء المهام مرئي.
- `Width` يضبط عرض جزء المهام.

### الخطوة 5: إعداد مرجع ملحق الويب

بعد ذلك، قمنا بإعداد مرجع ملحق الويب الذي يتضمن المعرف والإصدار ونوع المتجر والمتجر.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`هو معرف فريد لامتداد الويب.
- `Version` يحدد إصدار الامتداد.
- `StoreType` يشير إلى نوع المتجر (في هذه الحالة، OMEX).
- `Store` يحدد رمز اللغة/الثقافة الخاص بالمتجر.

### الخطوة 6: إضافة خصائص إلى ملحق الويب

يمكنك إضافة خصائص إلى ملحق الويب الخاص بك لتحديد سلوكه أو محتواه.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

 هنا نضيف خاصية اسمها`mailchimpCampaign`.

### الخطوة 7: ربط ملحق الويب

وأخيرًا، نضيف روابط إلى ملحق الويب الخاص بنا. تتيح لك الروابط ربط الامتداد بأجزاء معينة من المستند.

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545` هو اسم الربط.
- `WebExtensionBindingType.Text` يشير إلى أن الربط من نوع النص.
- `194740422` هو معرف جزء المستند الذي يرتبط به الامتداد.

### الخطوة 8: حفظ المستند

بعد إعداد كل شيء، احفظ مستندك.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

يحفظ هذا السطر المستند في الدليل المحدد باسم الملف المحدد.

### الخطوة 9: تحميل وعرض معلومات جزء المهام

للتحقق من معلومات جزء المهام وعرضها، نقوم بتحميل المستند ونكرره عبر أجزاء المهام.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

يقوم هذا الرمز بتحميل المستند وطباعة معرف الموفر والإصدار والكتالوج لكل جزء مهام في وحدة التحكم.

## خاتمة

وهذا كل شيء! لقد قمت بنجاح بإضافة وتكوين جزء مهام ملحق الويب في مستند Word باستخدام Aspose.Words for .NET. يمكن لهذه الميزة القوية تحسين مستندات Word الخاصة بك بشكل كبير من خلال توفير وظائف إضافية مباشرة داخل المستند. 

## الأسئلة الشائعة

### ما هو جزء المهام في Word؟
جزء المهام هو عنصر واجهة يوفر أدوات ووظائف إضافية داخل مستند Word، مما يعزز تفاعل المستخدم وإنتاجيته.

### هل يمكنني تخصيص مظهر جزء المهام؟
 نعم، يمكنك تخصيص مظهر جزء المهام عن طريق تعيين خصائص مثل`DockState`, `IsVisible` ، و`Width`.

### ما هي خصائص ملحق الويب؟
خصائص ملحق الويب هي خصائص مخصصة يمكنك إضافتها إلى ملحق الويب لتحديد سلوكه أو محتواه.

### كيف يمكنني ربط ملحق الويب بجزء من المستند؟
 يمكنك ربط ملحق الويب بجزء من المستند باستخدام ملف`WebExtensionBinding` الفئة، مع تحديد نوع الربط ومعرف الهدف.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Words لـ .NET؟
 يمكنك العثور على وثائق مفصلة[هنا](https://reference.aspose.com/words/net/).
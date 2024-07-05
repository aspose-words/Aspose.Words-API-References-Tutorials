---
title: احصل على الاستبدال بدون اللواحق
linktitle: احصل على الاستبدال بدون اللواحق
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدارة استبدال الخطوط بدون اللواحق في Aspose.Words لـ .NET. اتبع دليلنا خطوة بخطوة للتأكد من أن مستنداتك تبدو مثالية في كل مرة.
type: docs
weight: 10
url: /ar/net/working-with-fonts/get-substitution-without-suffixes/
---

مرحبًا بك في هذا الدليل الشامل حول إدارة استبدال الخطوط باستخدام Aspose.Words لـ .NET. إذا كنت تعاني من عدم ظهور الخطوط بشكل صحيح في مستنداتك، فقد وصلت إلى المكان الصحيح. سيأخذك هذا البرنامج التعليمي عبر عملية خطوة بخطوة للتعامل مع استبدال الخطوط دون اللواحق بكفاءة. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بـ C#: إن فهم برمجة C# سيجعل من السهل متابعة الخطوات وتنفيذها.
-  Aspose.Words for .NET Library: قم بتنزيل المكتبة وتثبيتها من ملف[رابط التحميل](https://releases.aspose.com/words/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير مثل Visual Studio لكتابة التعليمات البرمجية وتشغيلها.
-  مستند نموذجي: مستند نموذجي (على سبيل المثال،`Rendering.docx`) للعمل خلال هذا البرنامج التعليمي.

## استيراد مساحات الأسماء

أولاً، نحتاج إلى استيراد مساحات الأسماء الضرورية للوصول إلى الفئات والأساليب التي توفرها Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## الخطوة 1: تحديد دليل المستندات

للبدء، حدد الدليل الذي يوجد به المستند الخاص بك. يساعد هذا في تحديد موقع المستند الذي تريد العمل عليه.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إعداد معالج تحذير الاستبدال

بعد ذلك، نحتاج إلى إعداد معالج تحذير يُعلمنا عند حدوث استبدال الخط أثناء معالجة المستند. يعد هذا أمرًا بالغ الأهمية للتعرف على أي مشكلات تتعلق بالخطوط والتعامل معها.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## الخطوة 3: إضافة مصادر الخطوط المخصصة

في هذه الخطوة، سنضيف مصادر خطوط مخصصة لضمان قدرة Aspose.Words على تحديد الخطوط الصحيحة واستخدامها. يعد هذا مفيدًا بشكل خاص إذا كان لديك خطوط معينة مخزنة في أدلة مخصصة.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

في هذا الكود:
-  نقوم باسترداد مصادر الخطوط الحالية وإضافة جديدة`FolderFontSource` الإشارة إلى دليل الخطوط المخصص لدينا (`C:\\MyFonts\\`).
- نقوم بعد ذلك بتحديث مصادر الخطوط بهذه القائمة الجديدة.

## الخطوة 4: احفظ المستند

وأخيرًا، احفظ المستند بعد تطبيق إعدادات استبدال الخط. بالنسبة لهذا البرنامج التعليمي، سنقوم بحفظه بصيغة PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## الخطوة 5: إنشاء فئة معالج التحذير

 للتعامل مع التحذيرات بشكل فعال، قم بإنشاء فئة مخصصة تنفذ`IWarningCallback` واجهه المستخدم. ستقوم هذه الفئة بالتقاط وتسجيل أي تحذيرات لاستبدال الخط.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

في هذا الصف:
-  ال`Warning` تلتقط الطريقة التحذيرات المتعلقة باستبدال الخط.
-  ال`FontWarnings` تقوم المجموعة بتخزين هذه التحذيرات لمزيد من الفحص أو التسجيل.

## خاتمة

لقد أتقنت الآن عملية التعامل مع استبدال الخطوط بدون اللواحق باستخدام Aspose.Words for .NET. ستضمن هذه المعرفة أن تحافظ مستنداتك على مظهرها المقصود، بغض النظر عن الخطوط المتوفرة على النظام. استمر في تجربة الإعدادات والمصادر المختلفة للاستفادة الكاملة من قوة Aspose.Words.

## الأسئلة الشائعة

### س1: كيف يمكنني استخدام الخطوط من عدة دلائل مخصصة؟

 يمكنك إضافة متعددة`FolderFontSource` الحالات إلى`fontSources`قائمة وتحديث مصادر الخطوط وفقا لذلك.

### س2: أين يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Words لـ .NET؟

 يمكنك تنزيل نسخة تجريبية مجانية من[Aspose صفحة تجريبية مجانية](https://releases.aspose.com/).

###  س3: هل يمكنني التعامل مع أنواع متعددة من التحذيرات باستخدام`IWarningCallback`?

 نعم`IWarningCallback` تتيح لك الواجهة التعامل مع أنواع مختلفة من التحذيرات، وليس فقط استبدال الخطوط.

### س4: أين يمكنني الحصول على الدعم لـ Aspose.Words؟

 للحصول على الدعم، قم بزيارة[منتدى دعم Aspose.Words](https://forum.aspose.com/c/words/8).

### س5: هل يمكن شراء ترخيص مؤقت؟

 نعم يمكنك الحصول على ترخيص مؤقت من[صفحة الترخيص المؤقتة](https://purchase.aspose.com/temporary-license/).
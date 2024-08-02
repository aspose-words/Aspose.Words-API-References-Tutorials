---
title: رد اتصال الواصلة
linktitle: رد اتصال الواصلة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرّف على كيفية تنفيذ رد اتصال الواصلة في Aspose.Words لـ .NET لتحسين تنسيق المستند باستخدام هذا الدليل الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/working-with-hyphenation/hyphenation-callback/
---

## مقدمة

مرحبًا يا من هناك! هل وجدت نفسك متورطًا في تعقيدات تنسيق النص، خاصة عند التعامل مع اللغات التي تتطلب الواصلة؟ انت لست وحدك. الواصلة، على الرغم من أهميتها لتخطيط النص بشكل صحيح، إلا أنها يمكن أن تسبب بعض الصداع. لكن خمن ماذا؟ لقد حصلت Aspose.Words for .NET على ظهرك. تسمح لك هذه المكتبة القوية بإدارة تنسيق النص بسلاسة، بما في ذلك التعامل مع الواصلة من خلال آلية رد الاتصال. مفتون؟ دعنا نتعمق في التفاصيل الدقيقة لكيفية تنفيذ رد اتصال الواصلة باستخدام Aspose.Words for .NET.

## المتطلبات الأساسية

قبل أن نتعامل مع التعليمات البرمجية، دعونا نتأكد من حصولك على كل ما تحتاجه:

1.  Aspose.Words for .NET: تأكد من أن لديك المكتبة. أنت تستطيع[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
2. IDE: بيئة تطوير مثل Visual Studio.
3. المعرفة الأساسية بـ C#: فهم C# و.NET Framework.
4. قواميس الواصلة: قواميس الواصلة للغات التي تخطط لاستخدامها.
5.  ترخيص Aspose: ترخيص Aspose صالح. يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) إذا لم يكن لديك واحدة.

## استيراد مساحات الأسماء

أول الأشياء أولاً، فلنستورد مساحات الأسماء الضرورية. وهذا يضمن أن الكود الخاص بنا يمكنه الوصول إلى جميع الفئات والأساليب التي نحتاجها من Aspose.Words.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## الخطوة 1: قم بتسجيل رد اتصال الواصلة

للبدء، نحتاج إلى تسجيل رد الاتصال بالواصلة. هذا هو المكان الذي نطلب فيه من Aspose.Words استخدام منطق الواصلة المخصص لدينا.

```csharp
try
{
    // تسجيل رد اتصال الواصلة.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 نحن هنا نقوم بإنشاء مثيل لرد الاتصال المخصص الخاص بنا ونخصصه له`Hyphenation.Callback`.

## الخطوة 2: تحديد مسار المستند

بعد ذلك، نحتاج إلى تحديد الدليل الذي يتم تخزين مستنداتنا فيه. يعد هذا أمرًا بالغ الأهمية لأننا سنقوم بتحميل المستندات وحفظها من هذا المسار.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى المستندات الخاصة بك.

## الخطوة 3: قم بتحميل المستند

الآن، لنقم بتحميل المستند الذي يتطلب الواصلة.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

 نحن هنا نقوم بتحميل مستند نصي باللغة الألمانية. يمكنك استبدال`"German text.docx"` مع اسم ملف المستند الخاص بك.

## الخطوة 4: احفظ المستند

بعد تحميل المستند، نقوم بحفظه في ملف جديد، مع تطبيق رد اتصال الواصلة في هذه العملية.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

يحفظ هذا السطر المستند كملف PDF مع تطبيق الواصلة.

## الخطوة 5: التعامل مع استثناء قاموس الواصلة المفقود

في بعض الأحيان، قد تواجه مشكلة تتمثل في فقدان قاموس الواصلة. دعونا التعامل مع ذلك.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

في هذه الكتلة، نكتشف الاستثناء المحدد المتعلق بالقواميس المفقودة ونطبع الرسالة.

## الخطوة 6: تنفيذ فئة رد اتصال الواصلة المخصصة

 الآن، دعونا ننفذ`CustomHyphenationCallback` فئة تتعامل مع طلب قواميس الواصلة.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // تسجيل القاموس للغة المطلوبة.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 في هذا الفصل،`RequestDictionary` يتم استدعاء الطريقة عند الحاجة إلى قاموس الواصلة. يقوم بفحص اللغة وتسجيل القاموس المناسب.

## خاتمة

وهناك لديك! لقد تعلمت للتو كيفية تنفيذ رد اتصال بالواصلة في Aspose.Words لـ .NET. باتباع هذه الخطوات، يمكنك التأكد من تنسيق مستنداتك بشكل جميل، بغض النظر عن اللغة. سواء كنت تتعامل مع اللغة الإنجليزية أو الألمانية أو أي لغة أخرى، تتيح لك هذه الطريقة التعامل مع الواصلة دون عناء.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء المستندات وتعديلها وتحويلها برمجيًا.

### ما أهمية الواصلة في تنسيق المستندات؟
تعمل الواصلة على تحسين تخطيط النص عن طريق فصل الكلمات في الأماكن المناسبة، مما يضمن مستندًا أكثر قابلية للقراءة وجذابًا بصريًا.

### هل يمكنني استخدام Aspose.Words مجانًا؟
 يقدم Aspose.Words نسخة تجريبية مجانية. يمكنك الحصول عليه[هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على قاموس الواصلة؟
يمكنك تنزيل قواميس الواصلة من مصادر مختلفة عبر الإنترنت أو إنشاء قواميس خاصة بك إذا لزم الأمر.

### ماذا يحدث إذا كان قاموس الواصلة مفقودًا؟
 إذا كان القاموس مفقودًا، فإن`RequestDictionary` تطرح الطريقة استثناءً، والذي يمكنك التعامل معه لإعلام المستخدم أو تقديم بديل.
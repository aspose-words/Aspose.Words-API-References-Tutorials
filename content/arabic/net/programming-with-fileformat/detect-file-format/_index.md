---
title: كشف تنسيق ملف المستند
linktitle: كشف تنسيق ملف المستند
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية اكتشاف تنسيقات ملفات المستندات باستخدام Aspose.Words لـ .NET باستخدام هذا الدليل الشامل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-fileformat/detect-file-format/
---
## مقدمة

في العالم الرقمي اليوم، تعد إدارة تنسيقات المستندات المختلفة بكفاءة أمرًا بالغ الأهمية. سواء كنت تتعامل مع Word أو PDF أو HTML أو تنسيقات أخرى، فإن القدرة على اكتشاف هذه الملفات ومعالجتها بشكل صحيح يمكن أن توفر عليك الكثير من الوقت والجهد. في هذا البرنامج التعليمي، سنستكشف كيفية اكتشاف تنسيقات ملفات المستندات باستخدام Aspose.Words لـ .NET. سيرشدك هذا الدليل إلى كل ما تحتاج إلى معرفته، بدءًا من المتطلبات الأساسية وحتى الدليل المفصل خطوة بخطوة.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه:

-  Aspose.Words for .NET: يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/) . تأكد من أن لديك ترخيصًا صالحًا. إذا لم يكن الأمر كذلك، يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/).
- Visual Studio: أي إصدار حديث سيعمل بشكل جيد.
- .NET Framework: تأكد من تثبيت الإصدار الصحيح.

## استيراد مساحات الأسماء

للبدء، ستحتاج إلى استيراد مساحات الأسماء الضرورية في مشروعك:

```csharp
using Aspose.Words;
using Aspose.Words.FileFormats;
using Aspose.Words.FileFormats.Util;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
```

دعونا نقسم المثال إلى خطوات متعددة لتسهيل متابعته.

## الخطوة 1: إعداد الدلائل

أولاً، نحتاج إلى إعداد أدلة حيث سيتم فرز الملفات بناءً على تنسيقها.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// قم بإنشاء الدلائل إذا لم تكن موجودة بالفعل.
if (!Directory.Exists(supportedDir))
    Directory.CreateDirectory(supportedDir);
if (!Directory.Exists(unknownDir))
    Directory.CreateDirectory(unknownDir);
if (!Directory.Exists(encryptedDir))
    Directory.CreateDirectory(encryptedDir);
if (!Directory.Exists(pre97Dir))
    Directory.CreateDirectory(pre97Dir);
```

## الخطوة 2: الحصول على قائمة الملفات

بعد ذلك، سنحصل على قائمة بالملفات من الدليل، باستثناء أي مستندات تالفة.

```csharp
IEnumerable<string> fileList = Directory.GetFiles(dataDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## الخطوة 3: الكشف عن تنسيقات الملفات

الآن، نراجع كل ملف ونكتشف تنسيقه باستخدام Aspose.Words.

```csharp
foreach (string fileName in fileList)
{
    string nameOnly = Path.GetFileName(fileName);

    Console.Write(nameOnly);

    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

    // عرض نوع الوثيقة
    switch (info.LoadFormat)
    {
        case LoadFormat.Doc:
            Console.WriteLine("\tMicrosoft Word 97-2003 document.");
            break;
        case LoadFormat.Dot:
            Console.WriteLine("\tMicrosoft Word 97-2003 template.");
            break;
        case LoadFormat.Docx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
            break;
        case LoadFormat.Docm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
            break;
        case LoadFormat.Dotx:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
            break;
        case LoadFormat.Dotm:
            Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
            break;
        case LoadFormat.FlatOpc:
            Console.WriteLine("\tFlat OPC document.");
            break;
        case LoadFormat.Rtf:
            Console.WriteLine("\tRTF format.");
            break;
        case LoadFormat.WordML:
            Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
            break;
        case LoadFormat.Html:
            Console.WriteLine("\tHTML format.");
            break;
        case LoadFormat.Mhtml:
            Console.WriteLine("\tMHTML (Web archive) format.");
            break;
        case LoadFormat.Odt:
            Console.WriteLine("\tOpenDocument Text.");
            break;
        case LoadFormat.Ott:
            Console.WriteLine("\tOpenDocument Text Template.");
            break;
        case LoadFormat.DocPreWord60:
            Console.WriteLine("\tMS Word 6 or Word 95 format.");
            break;
        case LoadFormat.Unknown:
            Console.WriteLine("\tUnknown format.");
            break;
    }

    if (info.IsEncrypted)
    {
        Console.WriteLine("\tAn encrypted document.");
        File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
    }
    else
    {
        switch (info.LoadFormat)
        {
            case LoadFormat.DocPreWord60:
                File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
                break;
            case LoadFormat.Unknown:
                File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
                break;
            default:
                File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
                break;
        }
    }
}
```

## خاتمة

يعد اكتشاف تنسيقات ملفات المستندات باستخدام Aspose.Words لـ .NET عملية مباشرة. من خلال إعداد الأدلة الخاصة بك، والحصول على قائمة الملفات الخاصة بك، واستخدام Aspose.Words للكشف عن تنسيقات الملفات، يمكنك تنظيم مستنداتك وإدارتها بكفاءة. لا يوفر هذا الأسلوب الوقت فحسب، بل يضمن أيضًا التعامل مع تنسيقات المستندات المختلفة بشكل صحيح.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية للعمل مع مستندات Word برمجيًا. يسمح للمطورين بإنشاء وتعديل وتحويل المستندات بتنسيقات مختلفة.

### هل يستطيع Aspose.Words اكتشاف المستندات المشفرة؟
نعم، يمكن لـ Aspose.Words اكتشاف ما إذا كان المستند مشفرًا ويمكنك التعامل مع هذه المستندات وفقًا لذلك.

### ما هي التنسيقات التي يمكن لـ Aspose.Words اكتشافها؟
يمكن لـ Aspose.Words اكتشاف مجموعة واسعة من التنسيقات بما في ذلك DOC وDOCX وRTF وHTML وMHTML وODT وغيرها الكثير.

### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Words؟
 يمكنك الحصول على ترخيص مؤقت من[Aspose الشراء](https://purchase.aspose.com/temporary-license/) صفحة.

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Words؟
 يمكن العثور على وثائق Aspose.Words[هنا](https://reference.aspose.com/words/net/).

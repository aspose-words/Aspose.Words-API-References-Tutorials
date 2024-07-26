---
title: نوع التحكم المفضل في مستند Word
linktitle: نوع التحكم المفضل في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقل نموذج مربع التحرير والسرد في مستند Word باستخدام Aspose.Words لـ .NET. اتبع هذا الدليل التفصيلي خطوة بخطوة للتكامل السلس لمحتوى HTML.
type: docs
weight: 10
url: /ar/net/programming-with-htmlloadoptions/preferred-control-type/
---
## مقدمة

نحن نتعمق في برنامج تعليمي مثير حول كيفية العمل مع خيارات تحميل HTML في Aspose.Words لـ .NET، مع التركيز بشكل خاص على تعيين نوع التحكم المفضل عند إدراج حقل نموذج مربع التحرير والسرد في مستند Word. سيساعدك هذا الدليل التفصيلي خطوة بخطوة على فهم كيفية التعامل مع محتوى HTML وعرضه بشكل فعال داخل مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

## المتطلبات الأساسية

قبل أن ننتقل إلى الكود، هناك بعض الأشياء التي يجب أن تكون لديك:

1.  Aspose.Words for .NET: تأكد من تثبيت مكتبة Aspose.Words for .NET. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/words/net/).
2. بيئة التطوير: يجب أن يكون لديك بيئة تطوير، مثل Visual Studio.
3. المعرفة الأساسية بـ C#: الفهم الأساسي لبرمجة C# ضروري للمتابعة مع البرنامج التعليمي.
4. محتوى HTML: المعرفة الأساسية بـ HTML مفيدة لأننا سنتعامل مع محتوى HTML في هذا المثال.

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية للبدء:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Words;
using Aspose.Words.Loading;
```

الآن، دعونا نقسم المثال إلى خطوات متعددة لضمان الوضوح والفهم.

## الخطوة 1: قم بإعداد محتوى HTML الخاص بك

أولاً، نحتاج إلى تحديد محتوى HTML الذي نريد إدراجه في مستند Word. إليك مقتطف HTML الذي سنستخدمه:

```csharp
const string html = @"
    <html>
        <select name='ComboBox' size='1'>
            <option value='val1'>item1</option>
            <option value='val2'></option>                        
        </select>
    </html>
";
```

يحتوي HTML هذا على مربع تحرير وسرد بسيط يحتوي على خيارين. سنقوم بتحميل ملف HTML هذا في مستند Word ونحدد كيفية عرضه.

## الخطوة 2: تحديد دليل المستندات

بعد ذلك، حدد الدليل الذي سيتم حفظ مستند Word الخاص بك فيه. يساعد هذا في تنظيم ملفاتك والحفاظ على إدارة المسار نظيفة.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي الذي تريد حفظ مستند Word الخاص بك فيه.

## الخطوة 3: تكوين خيارات تحميل HTML

 هنا، نقوم بتكوين خيارات تحميل HTML، مع التركيز بشكل خاص على`PreferredControlType`ملكية. يحدد هذا كيفية عرض مربع التحرير والسرد في مستند Word.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

 عن طريق الإعداد`PreferredControlType` ل`HtmlControlType.StructuredDocumentTag`، نضمن أن يتم عرض مربع التحرير والسرد كعلامة مستند منظمة (SDT) في مستند Word.

## الخطوة 4: قم بتحميل محتوى HTML في المستند

باستخدام خيارات التحميل التي تم تكوينها، نقوم بتحميل محتوى HTML في مستند Word جديد.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

هنا، نقوم بتحويل سلسلة HTML إلى مصفوفة بايت ونحملها في المستند باستخدام تدفق الذاكرة. يضمن ذلك تفسير محتوى HTML وعرضه بشكل صحيح بواسطة Aspose.Words.

## الخطوة 5: احفظ المستند

وأخيرًا، احفظ المستند في الدليل المحدد بتنسيق DOCX.

```csharp
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

يؤدي هذا إلى حفظ مستند Word باستخدام عنصر تحكم مربع التحرير والسرد المعروض في الموقع المحدد.

## خاتمة

وهناك لديك! لقد نجحنا في إدراج حقل نموذج مربع التحرير والسرد في مستند Word باستخدام Aspose.Words لـ .NET من خلال الاستفادة من خيارات تحميل HTML. من المفترض أن يساعدك هذا الدليل المفصّل خطوة بخطوة على فهم العملية وتطبيقها على مشاريعك. سواء كنت تقوم بأتمتة إنشاء المستندات أو التعامل مع محتوى HTML، يوفر Aspose.Words for .NET أدوات قوية لتحقيق أهدافك.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
Aspose.Words for .NET هي مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Word وتحريرها وتحويلها وعرضها برمجيًا.

### هل يمكنني استخدام أنواع أخرى من عناصر تحكم HTML مع Aspose.Words لـ .NET؟
نعم، يدعم Aspose.Words for .NET أنواعًا مختلفة من عناصر تحكم HTML. يمكنك تخصيص كيفية عرض عناصر التحكم المختلفة في مستند Word.

### كيف يمكنني التعامل مع محتوى HTML المعقد في Aspose.Words لـ .NET؟
 يوفر Aspose.Words for .NET دعمًا شاملاً لـ HTML، بما في ذلك العناصر المعقدة. تأكد من تكوين`HtmlLoadOptions`بشكل مناسب للتعامل مع محتوى HTML المحدد الخاص بك.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
 يمكنك العثور على وثائق وأمثلة مفصلة على[Aspose.Words لصفحة وثائق .NET](https://reference.aspose.com/words/net/).

### هل تتوفر نسخة تجريبية مجانية من Aspose.Words لـ .NET؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[موقع أسبوز](https://releases.aspose.com/).

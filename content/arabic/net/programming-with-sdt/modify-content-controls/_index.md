---
title: تعديل عناصر التحكم في المحتوى
linktitle: تعديل عناصر التحكم في المحتوى
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعديل علامات المستندات المنظمة في Word باستخدام Aspose.Words لـ .NET. قم بتحديث النص والقوائم المنسدلة والصور خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/modify-content-controls/
---
## مقدمة

إذا سبق لك العمل مع مستندات Word وتحتاج إلى تعديل عناصر التحكم في المحتوى المنظم - مثل النص العادي أو القوائم المنسدلة أو الصور - باستخدام Aspose.Words for .NET، فأنت في المكان الصحيح! تعد علامات المستندات المنظمة (SDTs) أدوات قوية تجعل أتمتة المستندات أسهل وأكثر مرونة. في هذا البرنامج التعليمي، سنتعمق في كيفية تعديل معايير SDT هذه لتناسب احتياجاتك. سواء كنت تقوم بتحديث النص، أو تغيير تحديدات القائمة المنسدلة، أو تبديل الصور، فسيرشدك هذا الدليل خلال العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل أن ننتقل إلى التفاصيل الجوهرية لتعديل عناصر التحكم في المحتوى، تأكد من أن لديك ما يلي:

1.  تثبيت Aspose.Words لـ .NET: تأكد من تثبيت مكتبة Aspose.Words. إذا لم يكن الأمر كذلك، يمكنك[قم بتنزيله هنا](https://releases.aspose.com/words/net/).

2. المعرفة الأساسية بـ C#: يفترض هذا البرنامج التعليمي أنك على دراية بمفاهيم برمجة C# الأساسية.

3. بيئة تطوير .NET: يجب أن يكون لديك IDE مثل Visual Studio الذي تم إعداده لتشغيل تطبيقات .NET.

4. مستند نموذجي: سنستخدم نموذج مستند Word مع أنواع مختلفة من SDTs. يمكنك استخدام المثال الموجود في المثال أو إنشاء النموذج الخاص بك.

5.  الوصول إلى وثائق Aspose: لمزيد من المعلومات التفصيلية، قم بمراجعة[وثائق Aspose.Words](https://reference.aspose.com/words/net/).

## استيراد مساحات الأسماء

لبدء العمل مع Aspose.Words، تحتاج إلى استيراد مساحات الأسماء ذات الصلة إلى مشروع C# الخاص بك. إليك كيفية القيام بذلك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

ستمنحك مساحات الأسماء هذه إمكانية الوصول إلى الفئات والأساليب اللازمة لمعالجة علامات المستندات المنظمة في مستندات Word الخاصة بك.

## الخطوة 1: قم بإعداد مسار المستند الخاص بك

 قبل إجراء أية تغييرات، تحتاج إلى تحديد المسار إلى المستند الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي حيث تم تخزين المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## الخطوة 2: قم بالتكرار عبر علامات المستندات المنظمة

 لتعديل SDTs، تحتاج أولاً إلى تكرار جميع SDTs في المستند. ويتم ذلك باستخدام`GetChildNodes` طريقة للحصول على كافة العقد من النوع`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // تعديل المعاملة الخاصة والتفضيلية بناءً على نوعها
}
```

## الخطوة 3: تعديل SDTs للنص العادي

إذا كان SDT عبارة عن نوع نص عادي، فيمكنك استبدال محتواه. أولاً، قم بمسح المحتوى الموجود، ثم قم بإضافة نص جديد.

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 التفسير: هنا،`RemoveAllChildren()`يمسح المحتوى الحالي للمعاملة الخاصة والتفضيلية (SDT). ثم نقوم بإنشاء جديد`Paragraph`و`Run` كائن لإدراج النص الجديد.

## الخطوة 4: تعديل القائمة المنسدلة SDTs

 بالنسبة للقائمة المنسدلة SDTs، يمكنك تغيير العنصر المحدد عن طريق الوصول إلى`ListItems` مجموعة. وهنا نختار العنصر الثالث في القائمة.

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

Explanation: يقوم مقتطف الكود هذا بتحديد العنصر الموجود في الفهرس 2 (العنصر الثالث) من القائمة المنسدلة. اضبط الفهرس بناءً على احتياجاتك.

## الخطوة 5: تعديل الصورة SDTs

لتحديث صورة داخل صورة SDT، يمكنك استبدال الصورة الموجودة بصورة جديدة.

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 توضيح: يقوم هذا الكود بالتحقق مما إذا كان الشكل يحتوي على صورة ثم يستبدلها بصورة جديدة موجودة في`ImagesDir`.

## الخطوة 6: احفظ المستند المعدل

بعد إجراء جميع التغييرات اللازمة، احفظ المستند المعدل باسم جديد للحفاظ على المستند الأصلي كما هو.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

Explanation: يؤدي هذا إلى حفظ الوثيقة باسم ملف جديد بحيث يمكنك تمييزها بسهولة عن الأصل.

## خاتمة

يعد تعديل عناصر التحكم في المحتوى في مستند Word باستخدام Aspose.Words for .NET أمرًا مباشرًا بمجرد فهم الخطوات المتضمنة. سواء كنت تقوم بتحديث النص، أو تغيير تحديدات القائمة المنسدلة، أو تبديل الصور، فإن Aspose.Words يوفر واجهة برمجة تطبيقات قوية لهذه المهام. باتباع هذا البرنامج التعليمي، يمكنك إدارة عناصر التحكم في المحتوى المنظم لمستندك وتخصيصها بشكل فعال، مما يجعل مستنداتك أكثر ديناميكية ومخصصة لتلبية احتياجاتك.

## الأسئلة الشائعة

1. ما هي علامة الوثيقة المنظمة (SDT)؟

تعد أدوات SDT عناصر في مستندات Word تساعد في إدارة محتوى المستند وتنسيقه، مثل مربعات النص أو القوائم المنسدلة أو الصور.

2. كيف يمكنني إضافة عنصر قائمة منسدلة جديد إلى SDT؟

 لإضافة عنصر جديد، استخدم`ListItems` الملكية وإلحاق جديد`SdtListItem` إلى المجموعة.

3. هل يمكنني استخدام Aspose.Words لإزالة SDTs من المستند؟

نعم، يمكنك إزالة SDTs عن طريق الوصول إلى عقد المستند وحذف SDT المطلوبة.

4. كيف أتعامل مع SDTs المتداخلة ضمن عناصر أخرى؟

 استخدم ال`GetChildNodes` طريقة مع المعلمات المناسبة للوصول إلى SDTs المتداخلة.

5. ماذا علي أن أفعل إذا كانت المعاملة الخاصة والتفضيلية (SDT) التي أحتاج إلى تعديلها غير مرئية في المستند؟

تأكد من أن المعاملة الخاصة والتفضيلية ليست مخفية أو محمية. تحقق من إعدادات المستند وتأكد من أن الكود الخاص بك يستهدف نوع SDT بشكل صحيح.


### مثال للتعليمة البرمجية المصدر لتعديل عناصر التحكم في المحتوى باستخدام Aspose.Words لـ .NET 

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
	switch (sdt.SdtType)
	{
		case SdtType.PlainText:
		{
			sdt.RemoveAllChildren();
			Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
			Run run = new Run(doc, "new text goes here");
			para.AppendChild(run);
			break;
		}
		case SdtType.DropDownList:
		{
			SdtListItem secondItem = sdt.ListItems[2];
			sdt.ListItems.SelectedValue = secondItem;
			break;
		}
		case SdtType.Picture:
		{
			Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
			if (shape.HasImage)
			{
				shape.ImageData.SetImage(ImagesDir + "Watermark.png");
			}
			break;
		}
	}
}
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

هذا كل شيء! لقد نجحت في تعديل أنواع مختلفة من عناصر التحكم في المحتوى في مستند Word الخاص بك باستخدام Aspose.Words لـ .NET.
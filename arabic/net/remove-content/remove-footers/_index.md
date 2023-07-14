---
title: إزالة التذييلات في مستند Word
linktitle: إزالة التذييلات في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إزالة التذييلات في مستندات Word بسهولة باستخدام Aspose.Words for .NET. اتبع دليلنا المفصل خطوة بخطوة للتعامل الفعال مع ملفات DOCX.
type: docs
weight: 10
url: /ar/net/remove-content/remove-footers/
---
عندما يتعلق الأمر بمعالجة الكلمات باستخدام مستندات Word في تطبيق .NET الخاص بك ، فإن Aspose.Words أداة قوية ومتعددة الاستخدامات يمكنها مساعدتك في معالجة ملفات DOCX بسهولة. في هذه المقالة ، سوف نستكشف ميزة معينة في Aspose.Words: إزالة التذييلات.

## فهم Aspose.Words لـ .NET

Aspose.Words for .NET مكتبة فصول قوية لإنشاء وتعديل وتحويل ومعالجة مستندات Word في تطبيقات .NET. يقدم مجموعة واسعة من الميزات بما في ذلك إدارة الرؤوس والتذييلات والصور وتنسيق النص والمزيد.

## الغرض من إزالة التذييلات في Aspose. Words

قد تكون هناك حالات تريد فيها إزالة التذييلات من مستند Word. قد يرجع ذلك إلى أسباب مختلفة ، مثل الحاجة إلى حذف المعلومات الحساسة ، أو لتكييف المستند لاستخدام آخر أو ببساطة لإزالة العناصر غير المرغوب فيها. يجعل Aspose.Words هذه المهمة أسهل بكثير من خلال إعطائك طريقة سهلة وفعالة لإزالة التذييلات من مستنداتك.

## الخطوة 1: قم بتعيين مسار دليل المستند

قبل أن تبدأ ، تأكد من تعيين دليل المستند الخاص بك في متغير "dataDir". سيسمح لك هذا بتحديد الموقع الدقيق حيث يوجد ملف DOCX الخاص بك.

```csharp
string dataDir = "PATH_TO_YOUR_DOCUMENT_DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

تتمثل الخطوة الأولى في تحميل المستند في كائن من نوع Document. سيسمح لك ذلك بالوصول إلى محتويات المستند ومعالجتها.

```csharp
Document doc = new Document(dataDir + "Name_of_document.docx");
```

تأكد من استبدال "Name_of_document.docx" بالاسم الفعلي للمستند الخاص بك.

## الخطوة 3: كرر من خلال الأقسام

يمكن أن يحتوي مستند Word على أقسام متعددة ، ويمكن أن يكون لكل قسم تذييلاته الخاصة. يجب أن نذهب من خلال كل قسم من المستند للوصول إلى التذييلات.

```csharp
foreach (Section section in doc)
{
     // رمز لإزالة التذييلات
}
```

## الخطوة 4: إزالة التذييلات

الآن وقد انتقلنا إلى قسم معين ، يمكننا إزالة التذييلات من هذا القسم. في Aspose.Words ، هناك أنواع مختلفة من التذييلات المحتملة ، مثل "FooterFirst" (للصفحة الأولى) و "FooterPrimary" (للصفحات الفردية) و "FooterEven" (للصفحات الزوجية). نحتاج إلى التحقق من كل هذه الأنواع من التذييلات وإزالتها.

```csharp
HeaderFooter footer = section.HeadersFooters[HeaderFooterType.Footer

First];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterEven];
footer?.Remove();
```

## الخطوة 5: احفظ المستند المعدل

بمجرد الانتهاء من إزالة التذييلات ، يمكننا حفظ المستند المحرر في ملف منفصل.

```csharp
doc.Save(dataDir + "Name_of_modified_document.docx");
```

لا تنس تحديد اسم وموقع الملف المعدل في "Name_of_modified_document.docx".

### نموذج التعليمات البرمجية المصدر لإزالة التذييلات باستخدام Aspose.Words for .NET 
```csharp

//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Header and footer types.docx");

foreach (Section section in doc)
{
	// ما يصل إلى ثلاثة تذييلات مختلفة ممكنة في قسم (للصفحات الأولى ، الزوجية والفردية)
	// نتحقق منها ونحذفها جميعًا.
	HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
	footer?.Remove();

	// التذييل الأساسي هو التذييل المستخدم للصفحات الفردية.
	footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
	footer?.Remove();

	footer = section.HeadersFooters[HeaderFooterType.FooterEven];
	footer?.Remove();
}

doc.Save(dataDir + "RemoveContent.RemoveFooters.docx");
            
        
```

## خاتمة

في هذه المقالة ، اكتشفنا كيفية إزالة التذييلات من مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة معالجة مستنداتك وإزالة التذييلات غير المرغوب فيها. تقدم Aspose.Words حلاً فعالاً وملائماً لمعالجة الكلمات باستخدام مستندات Word في تطبيق .NET الخاص بك.

## التعليمات

#### س: لماذا يجب علي استخدام Aspose.Words لإزالة التذييلات في مستند Word؟

ج: Aspose.Words مكتبة فصول قوية ومتعددة الاستخدامات لمعالجة مستندات Word في تطبيقات .NET. باستخدام Aspose.Words ، يمكنك بسهولة إزالة التذييلات من مستندات Word الخاصة بك. يمكن أن يكون هذا مفيدًا لعدة أسباب ، مثل حذف المعلومات الحساسة أو تكييف المستند لاستخدام آخر أو ببساطة التخلص من العناصر غير المرغوب فيها. يجعل Aspose.Words هذه المهمة أسهل من خلال تزويدك بطريقة سهلة وفعالة لإزالة التذييلات من مستنداتك.

#### س: كيف يمكنني تحميل مستند في Aspose.Words لـ .NET؟

ج: لإزالة التذييلات من مستند Word ، يجب أولاً تحميل المستند في الذاكرة باستخدام طريقة Load () الخاصة بـ Aspose.Words. إليك نموذج التعليمات البرمجية لتحميل مستند من دليل محدد:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "Name_of_document.docx");
```

تأكد من استبدال "Name_of_document.docx" بالاسم الفعلي للمستند الخاص بك.

#### س: كيفية إزالة التذييلات في مستند باستخدام Aspose.Words؟

ج: لإزالة التذييلات ، تحتاج إلى استعراض أقسام المستند والتحقق من كل نوع تذييل محتمل. هناك أنواع مختلفة من التذييلات في Aspose.Words ، مثل "FooterFirst" (للصفحة الأولى) و "FooterPrimary" (للصفحات الفردية) و "FooterEven" (للصفحات الزوجية). تحتاج إلى التحقق من كل هذه الأنواع من التذييلات وإزالتها. إليك نموذج التعليمات البرمجية:

```csharp
HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterEven];
footer?.Remove();
```

#### س: كيف تحفظ المستند المحرر في Aspose.Words for .NET؟

ج: بمجرد الانتهاء من إزالة التذييلات ، يمكنك حفظ المستند المعدل في ملف منفصل باستخدام طريقة Save (). حدد اسم وموقع الملف المعدل. إليك نموذج التعليمات البرمجية:

```csharp
doc.Save(dataDir + "Name_of_modified_document.docx");
```

تذكر تحديد الاسم والموقع الفعلي للملف المعدل.
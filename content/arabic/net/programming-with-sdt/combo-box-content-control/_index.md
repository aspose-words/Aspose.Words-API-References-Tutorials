---
title: التحكم في محتوى مربع التحرير والسرد
linktitle: التحكم في محتوى مربع التحرير والسرد
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء عنصر تحكم في محتوى مربع التحرير والسرد في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/combo-box-content-control/
---

يشرح هذا البرنامج التعليمي كيفية إنشاء عنصر تحكم في محتوى مربع التحرير والسرد في مستند Word باستخدام Aspose.Words لـ .NET. تسمح عناصر التحكم في محتوى مربع التحرير والسرد للمستخدمين بتحديد عنصر من القائمة المنسدلة.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وStructuredDocumentTag
 إنشاء مثيل جديد لـ`Document` فئة و أ`StructuredDocumentTag` لتمثيل عنصر تحكم محتوى مربع التحرير والسرد. تحديد`SdtType.ComboBox` كنوع و`MarkupLevel.Block` كمستوى العلامات لإنشاء مربع تحرير وسرد على مستوى الكتلة.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## الخطوة 3: إضافة عناصر إلى مربع التحرير والسرد
 إضافة عناصر إلى مربع التحرير والسرد باستخدام`ListItems` ملكية`StructuredDocumentTag` . يتم تمثيل كل عنصر بواسطة`SdtListItem` كائن، والذي يأخذ نص العرض وقيمة. في هذا المثال، نضيف ثلاثة عناصر إلى مربع التحرير والسرد.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## الخطوة 4: إلحاق StructuredDocumentTag بالمستند
 قم بإلحاق عنصر تحكم محتوى مربع التحرير والسرد بالنص الأساسي للمستند باستخدام`AppendChild` طريقة نص القسم الأول من الوثيقة.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## الخطوة 5: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### مثال على التعليمات البرمجية المصدر للتحكم في محتوى Combo Box باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

هذا كل شيء! لقد نجحت في إنشاء عنصر تحكم محتوى Combo Box في مستند Word الخاص بك باستخدام Aspose.Words for .NET.
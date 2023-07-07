---
title: التحكم في محتوى صندوق التحرير والسرد
linktitle: التحكم في محتوى صندوق التحرير والسرد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء عنصر تحكم محتوى Combo Box في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/combo-box-content-control/
---

يشرح هذا البرنامج التعليمي كيفية إنشاء عنصر تحكم محتوى Combo Box في مستند Word باستخدام Aspose.Words for .NET. تتيح عناصر التحكم في محتوى مربع التحرير والسرد للمستخدمين تحديد عنصر من القائمة المنسدلة.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستند الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند و StructuredDocumentTag
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`StructuredDocumentTag` لتمثيل عنصر تحكم محتوى مربع التحرير والسرد. حدد`SdtType.ComboBox` كنوع و`MarkupLevel.Block` كمستوى الترميز لإنشاء مربع تحرير وسرد على مستوى الكتلة.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## الخطوة 3: أضف عناصر إلى صندوق التحرير والسرد
 أضف عناصر إلى مربع التحرير والسرد باستخدام ملف`ListItems` ممتلكات`StructuredDocumentTag` يتم تمثيل كل عنصر بامتداد`SdtListItem` كائن ، والذي يأخذ نص عرض وقيمة. في هذا المثال ، نضيف ثلاثة عناصر إلى مربع التحرير والسرد.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## الخطوة 4: إلحاق StructuredDocumentTag بالمستند
 قم بإلحاق عنصر تحكم محتوى مربع التحرير والسرد بنص المستند باستخدام`AppendChild` طريقة نص القسم الأول من المستند.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## الخطوة 5: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### مثال على شفرة المصدر للتحكم في محتوى صندوق التحرير والسرد باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

هذا كل شيء! لقد نجحت في إنشاء عنصر تحكم محتوى Combo Box في مستند Word باستخدام Aspose.Words for .NET.
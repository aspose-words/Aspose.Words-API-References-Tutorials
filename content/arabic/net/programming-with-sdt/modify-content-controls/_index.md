---
title: تعديل عناصر التحكم في المحتوى
linktitle: تعديل عناصر التحكم في المحتوى
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعديل النص والقوائم المنسدلة والصور ضمن عناصر التحكم في المحتوى في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/modify-content-controls/
---

يشرح هذا البرنامج التعليمي كيفية تعديل أنواع مختلفة من عناصر التحكم في المحتوى في مستند Word باستخدام Aspose.Words لـ .NET. يمكنك تحديث النص أو القيمة المحددة لقائمة منسدلة أو استبدال صورة ضمن عناصر التحكم في المحتوى.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وتكرار عناصر التحكم في المحتوى
 قم بتحميل مستند Word باستخدام`Document` منشئ، وتمرير المسار إلى الوثيقة كمعلمة. قم بالتكرار على جميع علامات المستند المنظمة في المستند باستخدام ملف`foreach` حلقة.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // تنفيذ الإجراءات بناءً على نوع التحكم في المحتوى
}
```

## الخطوة 3: تعديل التحكم في محتوى النص العادي
 لعناصر التحكم في المحتوى من النوع`SdtType.PlainText`وإزالة جميع العناصر الفرعية الموجودة وإنشاء فقرة جديدة وإلحاق مسار بالنص المطلوب.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## الخطوة 4: تعديل التحكم في محتوى القائمة المنسدلة
 لعناصر التحكم في المحتوى من النوع`SdtType.DropDownList` ، قم بتحديث القيمة المحددة عن طريق تعيينها على قيمة محددة`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## الخطوة 5: تعديل التحكم في محتوى الصورة
 لعناصر التحكم في المحتوى من النوع`SdtType.Picture`، قم باسترداد الشكل الموجود داخل عنصر تحكم المحتوى واستبدال صورته بصورة جديدة.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## الخطوة 6: احفظ المستند المعدل
 احفظ المستند المعدل في الدليل المحدد باستخدام الملف`Save`طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

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
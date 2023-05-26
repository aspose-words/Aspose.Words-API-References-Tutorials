---
title: تعديل عناصر التحكم في المحتوى
linktitle: تعديل عناصر التحكم في المحتوى
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعديل النص والقوائم المنسدلة والصور ضمن عناصر التحكم في المحتوى في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/modify-content-controls/
---

يشرح هذا البرنامج التعليمي كيفية تعديل الأنواع المختلفة من عناصر التحكم في المحتوى في مستند Word باستخدام Aspose.Words for .NET. يمكنك تحديث النص أو القيمة المحددة لقائمة منسدلة أو استبدال صورة ضمن عناصر التحكم في المحتوى.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستند الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: تحميل المستند وتكرار عناصر التحكم في المحتوى
 قم بتحميل مستند Word باستخدام ملف`Document`مُنشئ ، تمرير المسار إلى المستند كمعامل. كرر على جميع علامات المستند المهيكلة في المستند باستخدام ملف`foreach` حلقة.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // نفذ الإجراءات بناءً على نوع التحكم في المحتوى
}
```

## الخطوة 3: تعديل التحكم في محتوى النص العادي
 لعناصر تحكم المحتوى من النوع`SdtType.PlainText`، قم بإزالة جميع العناصر الفرعية الموجودة ، وقم بإنشاء فقرة جديدة ، وقم بإلحاق تشغيل بالنص المطلوب.

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
 لعناصر تحكم المحتوى من النوع`SdtType.DropDownList` ، قم بتحديث القيمة المحددة عن طريق تعيينها على ملف`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## الخطوة 5: تعديل برنامج التحكم في محتوى الصورة
 لعناصر تحكم المحتوى من النوع`SdtType.Picture`واسترداد الشكل داخل عنصر تحكم المحتوى واستبدال صورته بأخرى جديدة.

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
 احفظ المستند المعدل إلى الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### مثال على شفرة المصدر لتعديل عناصر التحكم في المحتوى باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
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

هذا كل شيء! لقد نجحت في تعديل أنواع مختلفة من عناصر تحكم المحتوى في مستند Word الخاص بك باستخدام Aspose.Words for .NET.
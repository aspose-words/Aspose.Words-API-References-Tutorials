---
title: تصدير إلى Markdown مع محاذاة محتوى الجدول
linktitle: تصدير إلى Markdown مع محاذاة محتوى الجدول
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تصدير محتوى الجدول بمحاذاة مختلفة لملفات Markdown باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
فيما يلي دليل تفصيلي خطوة بخطوة لشرح التعليمات البرمجية المصدر C # التالية التي تساعد في تصدير المحتوى إلى ملف Markdown مع محاذاة محتوى الجدول باستخدام مكتبة Aspose.Words لـ .NET. تأكد من تضمين مكتبة Aspose.Words في مشروعك قبل استخدام هذا الرمز.

## الخطوة 1: تعيين مسار دليل المستند

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

تأكد من تحديد المسار الصحيح إلى دليل المستندات الخاص بك حيث سيتم حفظ المستند المحرر.

## الخطوة 2: قم بإنشاء مستند ومولد مستندات

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 هنا نقوم بإنشاء مثيل لـ`Document` فئة ومثيل`DocumentBuilder` فئة تسمح لنا بمعالجة المستند وإضافة عناصر.

## الخطوة 3: أدخل خلايا في الجدول بمحاذاة فقرات مختلفة

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

نستخدم Document Builder لإدراج خلايا في الجدول وتعيين محاذاة فقرة مختلفة لكل خلية.

## الخطوة 4: قم بتعيين خيارات تصدير Markdown وحفظ المستند المعدل

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

قمنا بتعيين خيارات تصدير Markdown بمحاذاة محتوى جدول مختلفة ، ثم احفظنا المستند المعدل باستخدام كل خيار محاذاة.

### مثال على شفرة المصدر للتصدير إلى Markdown مع محاذاة محتوى الجدول باستخدام Aspose.Words for .NET

```csharp

            
	// المسار إلى دليل المستندات.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// يجعل كل الفقرات الموجودة داخل الجدول محاذاة.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// سيتم أخذ المحاذاة في هذه الحالة من الفقرة الأولى في عمود الجدول المقابل.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// احفظ المستند المعدل
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```

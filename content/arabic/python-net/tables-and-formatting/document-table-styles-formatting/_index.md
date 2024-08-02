---
title: أنماط وتنسيقات جدول المستندات باستخدام Aspose.Words Python
linktitle: أنماط وتنسيقات جدول المستندات
second_title: Aspose.Words Python إدارة المستندات API
description: تعرف على كيفية تصميم جداول المستندات وتنسيقها باستخدام Aspose.Words for Python. قم بإنشاء الجداول وتخصيصها وتصديرها باستخدام أدلة خطوة بخطوة وأمثلة التعليمات البرمجية. قم بتحسين عروض المستندات الخاصة بك اليوم!
type: docs
weight: 12
url: /ar/python-net/tables-and-formatting/document-table-styles-formatting/
---

تلعب جداول المستندات دورًا حاسمًا في تقديم المعلومات بطريقة منظمة وجذابة بصريًا. يوفر Aspose.Words for Python مجموعة قوية من الأدوات التي تسمح للمطورين بالعمل بكفاءة مع الجداول وتخصيص أنماطها وتنسيقاتها. في هذه المقالة، سوف نستكشف كيفية التعامل مع جداول المستندات وتحسينها باستخدام Aspose.Words for Python API. دعونا الغوص في!

## الشروع في العمل مع Aspose.Words لبايثون

قبل أن نتعمق في تفاصيل أنماط جدول المستندات وتنسيقه، دعنا نتأكد من إعداد الأدوات اللازمة لديك:

1. تثبيت Aspose.Words لـ Python: ابدأ بتثبيت مكتبة Aspose.Words باستخدام النقطة. يمكن القيام بذلك باستخدام الأمر التالي:
   
    ```bash
    pip install aspose-words
    ```

2. استيراد المكتبة: قم باستيراد مكتبة Aspose.Words إلى برنامج Python النصي الخاص بك باستخدام عبارة الاستيراد التالية:

    ```python
    import aspose.words
    ```

3. تحميل مستند: قم بتحميل مستند موجود أو قم بإنشاء مستند جديد باستخدام Aspose.Words API.

## إنشاء وإدراج الجداول في المستندات

لإنشاء الجداول وإدراجها في المستندات باستخدام Aspose.Words for Python، اتبع الخطوات التالية:

1.  إنشاء جدول: استخدم`DocumentBuilder` class لإنشاء جدول جديد وتحديد عدد الصفوف والأعمدة.

    ```python
    builder = aspose.words.DocumentBuilder(doc)
    table = builder.start_table()
    ```

2.  إدراج البيانات: قم بإضافة البيانات إلى الجدول باستخدام أداة الإنشاء`insert_cell`و`write` طُرق.

    ```python
    builder.insert_cell()
    builder.write("Header 1")
    builder.insert_cell()
    builder.write("Header 2")
    builder.end_row()
    ```

3. تكرار الصفوف: أضف صفوفًا وخلايا حسب الحاجة، باتباع نمط مماثل.

4.  إدراج جدول في المستند: أخيرًا، قم بإدراج الجدول في المستند باستخدام الملف`end_table` طريقة.

    ```python
    builder.end_table()
    ```

## تطبيق تنسيق الجدول الأساسي

 يمكن تحقيق التنسيق الأساسي للجدول باستخدام الطرق التي يوفرها`Table`و`Cell` الطبقات. إليك كيفية تحسين مظهر طاولتك:

1. تعيين عرض الأعمدة: اضبط عرض الأعمدة لضمان المحاذاة الصحيحة والجاذبية البصرية.

    ```python
    for cell in table.first_row.cells:
        cell.cell_format.preferred_width = aspose.words.PreferredWidth.from_points(100)
    ```

2. حشو الخلايا: أضف حشوة إلى الخلايا لتحسين التباعد.

    ```python
    for row in table.rows:
        for cell in row.cells:
            cell.cell_format.set_paddings(10, 10, 10, 10)
    ```

3. ارتفاع الصف: قم بتخصيص ارتفاعات الصف حسب الحاجة.

    ```python
    for row in table.rows:
        row.row_format.height_rule = aspose.words.HeightRule.AT_LEAST
        row.row_format.height = aspose.words.ConvertUtil.inch_to_points(1)
    ```

## جداول التصميم مع Aspose.Words

يوفر Aspose.Words for Python مجموعة من خيارات التصميم لجعل جداولك جذابة بصريًا:

1. أنماط الجدول: قم بتطبيق أنماط الجدول المحددة مسبقًا للحصول على مظهر احترافي.

    ```python
    table.style = aspose.words.StyleIdentifier.LIGHT_LIST_ACCENT_5
    ```

2. لون خلفية الخلية: قم بتغيير لون خلفية الخلية لتمييز بيانات محددة.

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(240, 240, 240)
    ```

3. تنسيق الخط: قم بتخصيص نمط الخط وحجمه ولونه لتحسين إمكانية القراءة.

    ```python
    run = cell.paragraphs[0].runs[0]
    run.font.size = aspose.words.Size(12, aspose.words.SizeUnit.POINTS)
    run.font.color = aspose.words.Color.from_rgb(0, 0, 0)
    ```

## دمج الخلايا وتقسيمها للتخطيطات المعقدة

غالبًا ما يتطلب إنشاء تخطيطات جدول معقدة دمج الخلايا وتقسيمها:

1. دمج الخلايا: دمج خلايا متعددة لإنشاء خلية واحدة أكبر.

    ```python
    table.rows[0].cells[0].cell_format.horizontal_merge = aspose.words.CellMerge.FIRST
    table.rows[0].cells[1].cell_format.horizontal_merge = aspose.words.CellMerge.PREVIOUS
    ```

2. تقسيم الخلايا: تقسيم الخلايا مرة أخرى إلى مكوناتها الفردية.

    ```python
    cell.cell_format.horizontal_merge = aspose.words.CellMerge.NONE
    ```

## ضبط ارتفاعات وعروض الصفوف والأعمدة

ضبط أبعاد الصفوف والأعمدة لتخطيط جدول متوازن:

1. ضبط ارتفاع الصف: تعديل ارتفاع الصف بناءً على المحتوى.

    ```python
    row.row_format.height_rule = aspose.words.HeightRule.AUTO
    ```

2. ضبط عرض العمود: ضبط عرض العمود تلقائيًا ليناسب المحتوى.

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_CONTENTS)
    ```

## إضافة الحدود والتظليل إلى الجداول

تحسين مظهر الجدول بإضافة الحدود والتظليل:

1. الحدود: تخصيص الحدود للجداول والخلايا.

    ```python
    table.set_borders(0.5, aspose.words.LineStyle.SINGLE, aspose.words.Color.from_rgb(0, 0, 0))
    ```

2. التظليل: قم بتطبيق التظليل على الخلايا للحصول على تأثير جذاب بصريًا.

    ```python
    cell.cell_format.shading.background_pattern_color = aspose.words.Color.from_rgb(230, 230, 230)
    ```

## العمل مع محتوى الخلية ومواءمتها

إدارة محتوى الخلية ومواءمتها بكفاءة لتحسين إمكانية القراءة:

1. محتوى الخلية: قم بإدراج محتوى، مثل النص والصور، في الخلايا.

    ```python
    builder.insert_cell()
    builder.write("Hello, Aspose!")
    ```

2. محاذاة النص: محاذاة نص الخلية حسب الحاجة.

    ```python
    cell.paragraphs[0].paragraph_format.alignment = aspose.words.ParagraphAlignment.CENTER
    ```

## التعامل مع رؤوس وتذييلات الجدول

قم بدمج الرؤوس والتذييلات في جداولك للحصول على سياق أفضل:

1. رأس الجدول: قم بتعيين الصف الأول كصف الرأس.

    ```python
    table.rows[0].row_format.is_header = True
    ```

2. تذييل الجدول: قم بإنشاء صف تذييل للحصول على معلومات إضافية

    ```python
    footer_row = table.append_row()
    footer_row.cells[0].cell_format.horizontal_merge = aspose.words.CellMerge.NONE
    footer_row.cells[0].paragraphs[0].runs[0].text = "Total"
    ```
	
## ضبط تخطيط الجدول تلقائيًا

تأكد من ضبط تخطيط الجدول الخاص بك تلقائيًا بناءً على المحتوى:

1. احتواء تلقائي للنافذة: السماح للجدول بأن يتناسب مع عرض الصفحة.

    ```python
    table.allow_auto_fit = True
    ```

2. تغيير حجم الخلايا تلقائيًا: تمكين تغيير حجم الخلية تلقائيًا لاستيعاب المحتوى.

    ```python
    table.auto_fit(auto_fit_behaviour=aspose.words.AutoFitBehaviour.AUTO_FIT_TO_WINDOW)
    ```

## تصدير الجداول إلى تنسيقات مختلفة

بمجرد أن يصبح الجدول جاهزًا، يمكنك تصديره إلى تنسيقات مختلفة، مثل PDF أو DOCX:

1. حفظ بتنسيق PDF: احفظ المستند مع الجدول كملف PDF.

    ```python
    doc.save("table_document.pdf", aspose.words.SaveFormat.PDF)
    ```

2. حفظ كملف DOCX: احفظ المستند كملف DOCX.

    ```python
    doc.save("table_document.docx", aspose.words.SaveFormat.DOCX)
    ```

## استكشاف الأخطاء وإصلاحها ونصائح لإدارة الجدول بشكل فعال

- إذا ظهرت الجداول مشوهة، فتحقق من عدم صحة عرض الأعمدة أو ارتفاعات الصفوف.
- اختبار عرض الجدول بتنسيقات مختلفة لضمان الاتساق.
- بالنسبة للتخطيطات المعقدة، خطط لدمج الخلايا وتقسيمها بعناية.

## خاتمة

يقدم Aspose.Words for Python مجموعة أدوات شاملة لإنشاء جداول المستندات وتصميمها وتنسيقها. باتباع الخطوات الموضحة في هذه المقالة، يمكنك إدارة الجداول في مستنداتك بشكل فعال، وتخصيص مظهرها، وتصديرها إلى تنسيقات مختلفة. استفد من قوة Aspose.Words لتحسين عروض المستندات الخاصة بك وتوفير معلومات واضحة وجذابة بصريًا لقرائك.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Words لـ Python؟

لتثبيت Aspose.Words لـ Python، استخدم الأمر التالي: 

```bash
pip install aspose-words
```

### هل يمكنني تطبيق أنماط مخصصة على جداولي؟

نعم، يمكنك تطبيق أنماط مخصصة على جداولك عن طريق تعديل خصائص مختلفة مثل الخطوط والألوان والحدود باستخدام Aspose.Words.

### هل من الممكن دمج الخلايا في الجدول؟

 نعم، يمكنك دمج الخلايا في جدول باستخدام`CellMerge` الخاصية المقدمة من Aspose.Words.

### كيف يمكنني تصدير جداولي إلى تنسيقات مختلفة؟

 يمكنك تصدير جداولك إلى تنسيقات مختلفة مثل PDF أو DOCX باستخدام الملف`save` الطريقة وتحديد الشكل المطلوب.

### أين يمكنني معرفة المزيد عن Aspose.Words لـ Python؟

 للحصول على وثائق ومراجع شاملة، قم بزيارة[Aspose.Words لمراجع Python API](https://reference.aspose.com/words/python-net/).

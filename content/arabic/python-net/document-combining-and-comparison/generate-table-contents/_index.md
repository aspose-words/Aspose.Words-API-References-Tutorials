---
title: إنشاء جدول محتويات شامل لمستندات Word
linktitle: إنشاء جدول محتويات شامل لمستندات Word
second_title: Aspose.Words - واجهة برمجة تطبيقات إدارة المستندات باستخدام Python
description: قم بإنشاء جدول محتويات سهل القراءة باستخدام Aspose.Words for Python. تعلم كيفية إنشاء بنية مستندك وتخصيصها وتحديثها بسلاسة.
type: docs
weight: 15
url: /ar/python-net/document-combining-and-comparison/generate-table-contents/
---

## مقدمة لجدول المحتويات

يوفر جدول المحتويات لمحة عامة عن بنية المستند، مما يسمح للقراء بالانتقال إلى أقسام معينة دون عناء. وهو مفيد بشكل خاص للمستندات الطويلة مثل أوراق البحث أو التقارير أو الكتب. من خلال إنشاء جدول المحتويات، يمكنك تحسين تجربة المستخدم ومساعدة القراء على التفاعل بشكل أكثر فعالية مع المحتوى الخاص بك.

## إعداد البيئة

 قبل أن نبدأ، تأكد من تثبيت Aspose.Words for Python. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/python/)بالإضافة إلى ذلك، تأكد من أن لديك مستند Word نموذجيًا ترغب في تحسينه باستخدام جدول المحتويات.

## تحميل مستند

```python
import asposewords

# Load the document
doc = asposewords.Document("your_document.docx")
```

## تحديد العناوين والعناوين الفرعية

لإنشاء جدول محتويات، تحتاج إلى تحديد العناوين والعناوين الفرعية داخل المستند. استخدم أنماط الفقرات المناسبة لتمييز هذه الأقسام. على سبيل المثال، استخدم "العنوان 1" للعناوين الرئيسية و"العنوان 2" للعناوين الفرعية.

```python
# Define headings and subheadings
for para in doc.get_child_nodes(asposewords.NodeType.PARAGRAPH, True):
    if para.paragraph_format.style_name == "Heading 1":
        # Add main heading
    elif para.paragraph_format.style_name == "Heading 2":
        # Add subheading
```

## إنشاء جدول المحتويات

الآن بعد أن حددنا العناوين والعناوين الفرعية، فلنبدأ في إنشاء جدول المحتويات نفسه. سننشئ قسمًا جديدًا في بداية المستند ونملأه بالمحتوى المناسب.

```python
# Create a new section for the table of contents
toc_section = doc.sections.insert_before(doc.sections[0])
toc_body = toc_section.body

# Add the title of the table of contents
toc_title = toc_body.append_paragraph("Table of Contents")
toc_title.paragraph_format.style_name = "Table of Contents Title"
```

## تخصيص جدول المحتويات

يمكنك تخصيص مظهر جدول المحتويات الخاص بك عن طريق ضبط الخطوط والأنماط والتنسيق. تأكد من استخدام تنسيق متسق في جميع أنحاء المستند للحصول على مظهر أنيق.

```python
# Customize the appearance of the table of contents
for para in toc_body.get_child_nodes(asposewords.NodeType.PARAGRAPH, False):
    para.paragraph_format.style_name = "TOC Entries"
```

## إضافة الارتباطات التشعبية

ولجعل جدول المحتويات تفاعليًا، أضف ارتباطات تشعبية تسمح للقراء بالانتقال مباشرة إلى الأقسام المقابلة في المستند.

```python
# Add hyperlinks to headings
for heading in headings:
    entry = toc_body.append_paragraph(heading.text)
    entry.paragraph_format.style_name = "TOC Entries"
    entry.hyperlink = "#" + heading.get_text().replace(" ", "_")
```

## تصميم جدول المحتويات

يتضمن تصميم جدول المحتويات تحديد أنماط الفقرات المناسبة للعنوان والإدخالات والعناصر الأخرى.

```python
# Define styles for the table of contents
toc_title.style.name = "Table of Contents Title"
doc.styles.add_style("Table of Contents Title", asposewords.StyleType.PARAGRAPH)
```

## تحديث جدول المحتويات

إذا قمت بإجراء تغييرات على بنية مستندك، فيمكنك بسهولة تحديث جدول المحتويات ليعكس هذه التغييرات.

```python
# Update the table of contents
doc.update_fields()
```

## أتمتة العملية

لتوفير الوقت وضمان الاتساق، فكر في إنشاء نص برمجي يقوم تلقائيًا بإنشاء جدول محتويات مستنداتك وتحديثه.

```python
# Automation script
def generate_table_of_contents(document_path):
    # Load the document
    doc = asposewords.Document(document_path)

    # ... (Rest of the code)

    # Update the table of contents
    doc.update_fields()
    doc.save(document_path)
```

## التعامل مع أرقام الصفحات

يمكنك إضافة أرقام الصفحات إلى جدول المحتويات لتزويد القراء بسياق أكثر تفصيلاً حول مكان العثور على أقسام معينة.

```python
# Add page numbers to table of contents
for entry in toc_body.get_child_nodes(asposewords.NodeType.PARAGRAPH, False):
    entry_text = entry.get_text()
    entry_page = doc.get_page_number(entry)
    entry_text += " - Page " + str(entry_page)
    entry.clear_contents()
    entry.append_text(entry_text)
```

## خاتمة

إن إنشاء جدول محتويات شامل باستخدام Aspose.Words for Python يمكن أن يحسن بشكل كبير من تجربة المستخدم لمستنداتك. باتباع هذه الخطوات، يمكنك تحسين إمكانية التنقل في المستندات، وتوفير وصول سريع إلى الأقسام الرئيسية، وتقديم المحتوى الخاص بك بطريقة أكثر تنظيمًا وسهولة في القراءة.

## الأسئلة الشائعة

### كيف يمكنني تعريف العناوين الفرعية ضمن جدول المحتويات؟

لتحديد العناوين الفرعية، استخدم أنماط الفقرات المناسبة في مستندك، مثل "العنوان 3" أو "العنوان 4". وسوف يقوم البرنامج النصي تلقائيًا بتضمينها في جدول المحتويات استنادًا إلى التسلسل الهرمي الخاص بها.

### هل يمكنني تغيير حجم الخط في إدخالات جدول المحتويات؟

بالتأكيد! يمكنك تخصيص نمط "مدخلات جدول المحتويات" عن طريق ضبط حجم الخط وغيره من خصائص التنسيق لتتناسب مع جماليات مستندك.

### هل من الممكن إنشاء جدول محتويات للمستندات الموجودة؟

نعم، يمكنك إنشاء جدول محتويات للمستندات الموجودة. ما عليك سوى تحميل المستند باستخدام Aspose.Words، واتباع الخطوات الموضحة في هذا البرنامج التعليمي، وتحديث جدول المحتويات حسب الحاجة.

### كيف يمكنني إزالة جدول المحتويات من مستندي؟

إذا قررت إزالة جدول المحتويات، فما عليك سوى حذف القسم الذي يحتوي على جدول المحتويات. لا تنس تحديث أرقام الصفحات المتبقية لتعكس التغييرات.
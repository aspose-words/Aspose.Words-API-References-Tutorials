---
title: التعامل مع الرؤوس والتذييلات في مستندات Word
linktitle: التعامل مع الرؤوس والتذييلات في مستندات Word
second_title: Aspose.Words Python إدارة المستندات API
description: تعلم كيفية التعامل مع الرؤوس والتذييلات في مستندات Word باستخدام Aspose.Words for Python. دليل خطوة بخطوة مع التعليمات البرمجية المصدر للتخصيص والإضافة والإزالة والمزيد. قم بتحسين تنسيق المستند الخاص بك الآن!
type: docs
weight: 16
url: /ar/python-net/document-structure-and-content-manipulation/document-headers-footers/
---
تلعب الرؤوس والتذييلات في مستندات Word دورًا حاسمًا في توفير السياق والعلامة التجارية والمعلومات الإضافية للمحتوى الخاص بك. يمكن أن تؤدي معالجة هذه العناصر باستخدام Aspose.Words for Python API إلى تحسين مظهر مستنداتك ووظائفها بشكل كبير. في هذا الدليل التفصيلي، سنستكشف كيفية التعامل مع الرؤوس والتذييلات باستخدام Aspose.Words for Python.


## الشروع في العمل مع Aspose.Words لبايثون

قبل الغوص في معالجة رأس الصفحة وتذييلها، تحتاج إلى إعداد Aspose.Words لـ Python. اتبع الخطوات التالية:

1. التثبيت: قم بتثبيت Aspose.Words for Python باستخدام النقطة.

```python
pip install aspose-words
```

2. استيراد الوحدة: قم باستيراد الوحدة المطلوبة في برنامج Python النصي الخاص بك.

```python
import aspose.words
```

## إضافة رأس وتذييل بسيط

لإضافة رأس وتذييل أساسي إلى مستند Word، اتبع الخطوات التالية:

1. إنشاء مستند: قم بإنشاء مستند Word جديد باستخدام Aspose.Words.

```python
doc = aspose.words.Document()
```

2.  إضافة رأس وتذييل: استخدم`sections` خاصية الوثيقة للوصول إلى الأقسام. ثم استخدم`headers_footers` خاصية إضافة الرؤوس والتذييلات.

```python
section = doc.sections[0]
header = section.headers_footers[aspose.words.HeaderFooterType.HEADER_PRIMARY]
footer = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_PRIMARY]
```

3. إضافة محتوى: أضف محتوى إلى الرأس والتذييل.

```python
header_paragraph = header.paragraphs.add()
header_run = header_paragraph.runs.add()
header_run.text = "This is the header text."

footer_paragraph = footer.paragraphs.add()
footer_run = footer_paragraph.runs.add()
footer_run.text = "Page number: {PAGE} of {NUMPAGES}"
```

4. حفظ المستند: احفظ المستند بالرأس والتذييل.

```python
doc.save("document_with_header_footer.docx")
```

## تخصيص محتوى الرأس والتذييل

يمكنك تخصيص محتوى الرأس والتذييل عن طريق إضافة الصور والجداول والحقول الديناميكية. على سبيل المثال:

1. إضافة الصور: أدخل الصور في الرأس أو التذييل.

```python
image_path = "path_to_your_image.png"
header_run.add_picture(image_path)
```

2. إضافة الجداول: دمج الجداول للحصول على معلومات جدولية.

```python
footer_table = footer.add_table(1, 2)
footer_table.rows[0].cells[0].text = "Copyright © 2023"
footer_table.rows[0].cells[1].text = "All rights reserved."
```

3. الحقول الديناميكية: استخدم الحقول الديناميكية لإدراج البيانات تلقائيًا.

```python
footer_run.text = "Page number: {PAGE} of {NUMPAGES} - Document created on {DATE}"
```

## رؤوس وتذييلات مختلفة للصفحات الفردية والزوجية

يمكن أن يؤدي إنشاء رؤوس وتذييلات مختلفة للصفحات الفردية والزوجية إلى إضافة لمسة احترافية إلى مستنداتك. إليك الطريقة:

1. تعيين تخطيط الصفحة الفردية والزوجية: حدد التخطيط للسماح برؤوس وتذييلات مختلفة للصفحات الفردية والزوجية.

```python
section = doc.sections[0]
section.page_setup.different_first_page_header_footer = True
section.page_setup.odd_and_even_pages_header_footer = True
```

2. إضافة رؤوس وتذييلات: قم بإضافة رؤوس وتذييلات للصفحة الأولى، والصفحات الفردية، والصفحات الزوجية.

```python
header_first = section.headers_footers[aspose.words.HeaderFooterType.HEADER_FIRST]
footer_first = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_FIRST]
header_odd = section.headers_footers[aspose.words.HeaderFooterType.HEADER_EVEN]
footer_odd = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_EVEN]
header_even = section.headers_footers[aspose.words.HeaderFooterType.HEADER_ODD]
footer_even = section.headers_footers[aspose.words.HeaderFooterType.FOOTER_ODD]
```

3. التخصيص حسب الحاجة: قم بتخصيص كل رأس وتذييل وفقًا لمتطلباتك.

## إزالة الرؤوس والتذييلات

لإزالة الرؤوس والتذييلات من مستند Word:

1. إزالة الرؤوس والتذييلات: امسح محتوى الرؤوس والتذييلات.

```python
header.clear_content()
footer.clear_content()
```

2. تعطيل الرؤوس والتذييلات المختلفة: قم بتعطيل الرؤوس والتذييلات المختلفة للصفحات الفردية والزوجية إذا لزم الأمر.

```python
section.page_setup.different_first_page_header_footer = False
section.page_setup.odd_and_even_pages_header_footer = False
```

## الأسئلة الشائعة

### كيف يمكنني الوصول إلى محتوى الرأس والتذييل؟

 للوصول إلى محتوى الرأس والتذييل، استخدم`headers_footers` خاصية قسم الوثيقة

### هل يمكنني إضافة صور إلى الرؤوس والتذييلات؟

 نعم، يمكنك إضافة صور إلى الرؤوس والتذييلات باستخدام`add_picture` طريقة.

### هل من الممكن أن يكون هناك رؤوس مختلفة للصفحات الفردية والزوجية؟

بالتأكيد، يمكنك إنشاء رؤوس وتذييلات مختلفة للصفحات الفردية والزوجية من خلال تمكين الإعدادات المناسبة.

### هل يمكنني إزالة الرؤوس والتذييلات من صفحات معينة؟

نعم، يمكنك مسح محتوى الرؤوس والتذييلات لإزالتها بشكل فعال.

### أين يمكنني معرفة المزيد عن Aspose.Words لـ Python؟

لمزيد من الوثائق والأمثلة التفصيلية، قم بزيارة[Aspose.Words لمرجع Python API](https://reference.aspose.com/words/python-net/).

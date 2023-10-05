---
title: استخدام علامات المستندات المنظمة (SDT) في Aspose.Words لـ Java
linktitle: استخدام علامات المستندات المنظمة (SDT)
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية استخدام علامات المستندات المنظمة (SDT) في Aspose.Words لـ Java باستخدام هذا الدليل الشامل. إنشاء وتعديل وربط SDTs ببيانات XML المخصصة.
type: docs
weight: 19
url: /ar/java/document-manipulation/using-structured-document-tags/
---

## مقدمة لاستخدام علامات المستندات المنظمة (SDT) في Aspose.Words لـ Java

تعد علامات المستندات المنظمة (SDT) ميزة قوية في Aspose.Words for Java والتي تتيح لك إنشاء محتوى منظم ومعالجته داخل مستنداتك. في هذا الدليل الشامل، سنرشدك عبر الجوانب المختلفة لاستخدام SDTs في Aspose.Words for Java. سواء كنت مطورًا مبتدئًا أو متمرسًا، ستجد رؤى قيمة وأمثلة عملية في هذه المقالة.

## ابدء

قبل أن نتعمق في التفاصيل، دعونا نهيئ بيئتنا وننشئ معاملة خاصة وتفاضلية أساسية. سنتناول في هذا القسم المواضيع التالية:

- إنشاء مستند جديد
- إضافة علامة مستند منظم
- حفظ الوثيقة

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإنشاء علامة مستند منظمة من النوع CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// احفظ المستند
doc.save("WorkingWithSDT.docx");
```

## التحقق من الحالة الحالية لمربع الاختيار SDT

بمجرد إضافة مربع اختيار SDT إلى مستندك، قد ترغب في التحقق من حالته الحالية برمجيًا. يمكن أن يكون هذا مفيدًا عندما تحتاج إلى التحقق من صحة إدخال المستخدم أو تنفيذ إجراءات محددة بناءً على حالة مربع الاختيار.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // تم تحديد خانة الاختيار
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## تعديل عناصر التحكم في المحتوى

في هذا القسم، سنستكشف كيفية تعديل عناصر التحكم في المحتوى داخل مستندك. سنغطي ثلاثة أنواع من عناصر التحكم في المحتوى: نص عادي، وقائمة منسدلة، وصورة.

### تعديل التحكم في محتوى النص العادي

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // امسح المحتوى الموجود
    sdtPlainText.removeAllChildren();

    // إضافة نص جديد
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### تعديل التحكم في محتوى القائمة المنسدلة

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // حدد العنصر الثاني من القائمة
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### تعديل التحكم في محتوى الصورة

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // استبدل الصورة بأخرى جديدة
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## إنشاء عنصر تحكم محتوى ComboBox

يتيح التحكم في محتوى ComboBox للمستخدمين الاختيار من قائمة الخيارات المحددة مسبقًا. لنقم بإنشاء واحدة في وثيقتنا.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## العمل مع التحكم في محتوى النص المنسق

تعد عناصر التحكم في محتوى النص المنسق مثالية لإضافة نص منسق إلى مستنداتك. دعونا ننشئ واحدًا ونحدد محتواه.

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## ضبط أنماط التحكم في المحتوى

يمكنك تطبيق الأنماط على عناصر التحكم في المحتوى لتحسين المظهر المرئي للمستند الخاص بك. دعونا نرى كيفية تعيين نمط عنصر تحكم المحتوى.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//تطبيق نمط مخصص
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## ربط SDT ببيانات XML المخصصة

في بعض السيناريوهات، قد تحتاج إلى ربط SDT ببيانات XML المخصصة لإنشاء محتوى ديناميكي. دعونا نستكشف كيفية تحقيق ذلك.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## إنشاء جدول يحتوي على أقسام متكررة تم تعيينها لبيانات XML المخصصة

يمكن أن تكون الجداول ذات الأقسام المتكررة مفيدة للغاية لعرض البيانات المنظمة. لنقم بإنشاء مثل هذا الجدول وتعيينه لبيانات XML المخصصة.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## العمل مع علامات المستندات المنظمة متعددة الأقسام

يمكن أن تمتد علامات المستندات المنظمة على أقسام متعددة في المستند. في هذا القسم، سوف نستكشف كيفية العمل مع إجراءات المعاملة الخاصة (SDT) متعددة الأقسام.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## خاتمة

توفر علامات المستندات المنظمة في Aspose.Words for Java طريقة متعددة الاستخدامات لإدارة المحتوى وتنسيقه داخل مستنداتك. سواء كنت بحاجة إلى إنشاء قوالب أو نماذج أو مستندات ديناميكية، فإن أدوات SDT توفر المرونة والتحكم الذي تحتاجه. باتباع الأمثلة والإرشادات الواردة في هذه المقالة، يمكنك الاستفادة من قوة SDTs لتحسين مهام معالجة المستندات الخاصة بك.

## الأسئلة الشائعة

### ما هو الغرض من علامات المستندات المنظمة (SDTs)؟

تخدم علامات المستندات المنظمة (SDTs) غرض تنظيم المحتوى وتنسيقه داخل المستندات، مما يسهل إنشاء القوالب والنماذج والمستندات المنظمة.

### كيف يمكنني التحقق من الحالة الحالية لـ Checkbox SDT؟

 يمكنك التحقق من الحالة الحالية لـ Checkbox SDT باستخدام`setChecked` الطريقة كما هو موضح في المقال.

### هل يمكنني تطبيق الأنماط على عناصر التحكم في المحتوى؟

نعم، يمكنك تطبيق الأنماط على عناصر التحكم في المحتوى لتخصيص مظهرها في المستند.

### هل من الممكن ربط SDT ببيانات XML المخصصة؟

نعم، يمكنك ربط SDT ببيانات XML المخصصة، مما يسمح بإنشاء محتوى ديناميكي وتعيين البيانات.

### ما هي الأقسام المتكررة في SDTs؟

تتيح لك الأقسام المتكررة في SDTs إنشاء جداول تحتوي على بيانات ديناميكية، حيث يمكن تكرار الصفوف بناءً على بيانات XML المعينة.
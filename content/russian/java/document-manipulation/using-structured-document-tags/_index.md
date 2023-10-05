---
title: Использование тегов структурированного документа (SDT) в Aspose.Words для Java
linktitle: Использование тегов структурированного документа (SDT)
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как использовать теги структурированных документов (SDT) в Aspose.Words для Java, с помощью этого подробного руководства. Создавайте, изменяйте и привязывайте SDT к пользовательским данным XML.
type: docs
weight: 19
url: /ru/java/document-manipulation/using-structured-document-tags/
---

## Введение в использование тегов структурированных документов (SDT) в Aspose.Words для Java

Теги структурированных документов (SDT) — это мощная функция Aspose.Words для Java, которая позволяет вам создавать структурированный контент в ваших документах и манипулировать им. В этом подробном руководстве мы познакомим вас с различными аспектами использования SDT в Aspose.Words for Java. Независимо от того, новичок вы или опытный разработчик, в этой статье вы найдете ценную информацию и практические примеры.

## Начиная

Прежде чем углубиться в детали, давайте настроим нашу среду и создадим базовый SDT. В этом разделе мы рассмотрим следующие темы:

- Создание нового документа
- Добавление тега структурированного документа
- Сохранение документа

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте тег структурированного документа типа CHECKBOX.
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Сохраните документ
doc.save("WorkingWithSDT.docx");
```

## Проверка текущего состояния флажка SDT

После того как вы добавили флажок SDT в документ, вы можете проверить его текущее состояние программным способом. Это может быть полезно, когда вам нужно проверить ввод пользователя или выполнить определенные действия в зависимости от состояния флажка.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // Флажок установлен
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Изменение элементов управления контентом

В этом разделе мы рассмотрим, как изменить элементы управления содержимым в вашем документе. Мы рассмотрим три типа элементов управления содержимым: обычный текст, раскрывающийся список и изображение.

### Изменение элемента управления содержимым в виде простого текста

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Очистить существующий контент
    sdtPlainText.removeAllChildren();

    // Добавить новый текст
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Изменение управления содержимым раскрывающегося списка

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Выберите второй элемент из списка
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Изменение управления содержимым изображения

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Замените изображение на новое
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Создание элемента управления содержимым ComboBox

Элемент управления содержимым ComboBox позволяет пользователям выбирать из заранее определенного списка опций. Давайте создадим его в нашем документе.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Работа с элементом управления форматированным текстом

Элементы управления содержимым форматированного текста идеально подходят для добавления форматированного текста в ваши документы. Давайте создадим его и настроим его содержимое.

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

## Настройка стилей управления контентом

Вы можете применять стили к элементам управления содержимым, чтобы улучшить внешний вид вашего документа. Давайте посмотрим, как установить стиль элемента управления содержимым.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Применить собственный стиль
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Привязка SDT к пользовательским XML-данным

В некоторых сценариях вам может потребоваться привязать SDT к пользовательским данным XML для создания динамического контента. Давайте рассмотрим, как этого добиться.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Создание таблицы с повторяющимися разделами, сопоставленными с пользовательскими данными XML

Таблицы с повторяющимися разделами могут быть чрезвычайно полезны для представления структурированных данных. Давайте создадим такую таблицу и сопоставим ее с пользовательскими данными XML.

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

## Работа с тегами многосекционного структурированного документа

Структурированные теги документа могут охватывать несколько разделов документа. В этом разделе мы рассмотрим, как работать с многосекционными SDT.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Заключение

Структурированные теги документов в Aspose.Words для Java предоставляют универсальный способ управления и форматирования содержимого ваших документов. Если вам нужно создать шаблоны, формы или динамические документы, SDT предлагают необходимую вам гибкость и контроль. Следуя примерам и рекомендациям, приведенным в этой статье, вы сможете использовать возможности SDT для улучшения задач обработки документов.

## Часто задаваемые вопросы

### Какова цель тегов структурированных документов (SDT)?

Теги структурированных документов (SDT) служат для организации и форматирования содержимого документов, упрощая создание шаблонов, форм и структурированных документов.

### Как я могу проверить текущее состояние Checkbox SDT?

 Вы можете проверить текущее состояние Checkbox SDT, используя`setChecked` метод, как показано в статье.

### Могу ли я применять стили к элементам управления содержимым?

Да, вы можете применять стили к элементам управления содержимым, чтобы настроить их внешний вид в документе.

### Можно ли привязать SDT к пользовательским данным XML?

Да, вы можете привязать SDT к пользовательским данным XML, что позволит создавать динамическое содержимое и отображать данные.

### Что такое повторяющиеся разделы в SDT?

Повторяющиеся разделы в SDT позволяют создавать таблицы с динамическими данными, строки в которых могут повторяться на основе сопоставленных данных XML.
---
title: Używanie znaczników dokumentów strukturalnych (SDT) w Aspose.Words dla Java
linktitle: Korzystanie ze znaczników dokumentów strukturalnych (SDT)
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak używać znaczników dokumentów strukturalnych (SDT) w Aspose.Words dla Java, korzystając z tego obszernego przewodnika. Twórz, modyfikuj i wiąż SDT z niestandardowymi danymi XML.
type: docs
weight: 19
url: /pl/java/document-manipulation/using-structured-document-tags/
---

## Wprowadzenie do używania znaczników dokumentów strukturalnych (SDT) w Aspose.Words dla Java

Tagi dokumentów strukturalnych (SDT) to potężna funkcja w Aspose.Words dla Java, która umożliwia tworzenie i manipulowanie uporządkowaną treścią w dokumentach. W tym obszernym przewodniku przeprowadzimy Cię przez różne aspekty używania SDT w Aspose.Words dla Java. Niezależnie od tego, czy jesteś początkującym, czy doświadczonym programistą, w tym artykule znajdziesz cenne spostrzeżenia i praktyczne przykłady.

## Pierwsze kroki

Zanim zagłębimy się w szczegóły, skonfigurujmy nasze środowisko i utwórzmy podstawowe narzędzie SDT. W tej sekcji omówimy następujące tematy:

- Tworzenie nowego dokumentu
- Dodawanie znacznika dokumentu strukturalnego
- Zapisywanie dokumentu

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Utwórz znacznik dokumentu strukturalnego typu CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Zapisz dokument
doc.save("WorkingWithSDT.docx");
```

## Sprawdzanie bieżącego stanu pola wyboru SDT

Po dodaniu pola wyboru SDT do dokumentu możesz chcieć programowo sprawdzić jego bieżący stan. Może to być przydatne, gdy trzeba sprawdzić dane wejściowe użytkownika lub wykonać określone działania w oparciu o stan pola wyboru.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // Pole wyboru jest zaznaczone
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Modyfikowanie kontroli treści

W tej sekcji omówimy, jak modyfikować elementy sterujące treścią w dokumencie. Omówimy trzy typy kontroli zawartości: zwykły tekst, lista rozwijana i obraz.

### Modyfikowanie kontroli zawartości zwykłego tekstu

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Wyczyść istniejącą zawartość
    sdtPlainText.removeAllChildren();

    // Dodaj nowy tekst
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Modyfikowanie kontroli zawartości listy rozwijanej

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Wybierz drugą pozycję z listy
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Modyfikowanie kontroli zawartości obrazu

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Zastąp obraz nowym
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Tworzenie kontrolki zawartości ComboBox

Kontrola zawartości ComboBox umożliwia użytkownikom wybieranie z predefiniowanej listy opcji. Stwórzmy taki w naszym dokumencie.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Praca z kontrolą zawartości tekstu sformatowanego

Elementy sterujące zawartością tekstu sformatowanego doskonale nadają się do dodawania sformatowanego tekstu do dokumentów. Stwórzmy taki i ustalmy jego zawartość.

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

## Ustawianie stylów kontroli treści

Możesz zastosować style do kontrolek zawartości, aby poprawić wygląd dokumentu. Zobaczmy, jak ustawić styl kontrolki zawartości.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Zastosuj niestandardowy styl
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Wiązanie SDT z niestandardowymi danymi XML

W niektórych scenariuszach może być konieczne powiązanie SDT z niestandardowymi danymi XML w celu dynamicznego generowania treści. Przyjrzyjmy się, jak to osiągnąć.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Tworzenie tabeli z powtarzającymi się sekcjami odwzorowanymi na niestandardowe dane XML

Tabele z powtarzającymi się sekcjami mogą być niezwykle przydatne do prezentacji ustrukturyzowanych danych. Utwórzmy taką tabelę i zmapujmy ją na niestandardowe dane XML.

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

## Praca z wielosekcyjnymi znacznikami dokumentów strukturalnych

Tagi dokumentu strukturalnego mogą obejmować wiele sekcji dokumentu. W tej sekcji omówimy, jak pracować z wielosekcyjnymi zestawami SDT.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Wniosek

Ustrukturyzowane znaczniki dokumentów w Aspose.Words dla Java zapewniają wszechstronny sposób zarządzania i formatowania treści w dokumentach. Niezależnie od tego, czy chcesz utworzyć szablony, formularze czy dokumenty dynamiczne, narzędzia SDT zapewniają wymaganą elastyczność i kontrolę. Postępując zgodnie z przykładami i wskazówkami zawartymi w tym artykule, możesz wykorzystać możliwości narzędzi SDT w celu usprawnienia zadań związanych z przetwarzaniem dokumentów.

## Często zadawane pytania

### Jaki jest cel znaczników dokumentów strukturalnych (SDT)?

Tagi dokumentów strukturalnych (SDT) służą do organizowania i formatowania treści w dokumentach, ułatwiając tworzenie szablonów, formularzy i dokumentów strukturalnych.

### Jak mogę sprawdzić bieżący stan SDT pola wyboru?

 Możesz sprawdzić bieżący stan SDT pola wyboru za pomocą`setChecked` sposób, jak pokazano w artykule.

### Czy mogę zastosować style do kontroli zawartości?

Tak, możesz zastosować style do Kontroli treści, aby dostosować ich wygląd w dokumencie.

### Czy można powiązać SDT z niestandardowymi danymi XML?

Tak, możesz powiązać SDT z niestandardowymi danymi XML, umożliwiając dynamiczne generowanie treści i mapowanie danych.

### Co to są powtarzające się sekcje w SDT?

Sekcje powtarzalne w narzędziach SDT umożliwiają tworzenie tabel z danymi dynamicznymi, w których wiersze mogą się powtarzać w oparciu o zmapowane dane XML.
---
title: Utilizzo dei tag di documento strutturato (SDT) in Aspose.Words per Java
linktitle: Utilizzo dei tag dei documenti strutturati (SDT)
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come utilizzare i tag di documenti strutturati (SDT) in Aspose.Words per Java con questa guida completa. Crea, modifica e associa SDT a dati XML personalizzati.
type: docs
weight: 19
url: /it/java/document-manipulation/using-structured-document-tags/
---

## Introduzione all'uso dei tag di documento strutturato (SDT) in Aspose.Words per Java

tag di documenti strutturati (SDT) sono una potente funzionalità di Aspose.Words per Java che ti consente di creare e manipolare contenuti strutturati all'interno dei tuoi documenti. In questa guida completa, ti guideremo attraverso i vari aspetti dell'utilizzo degli SDT in Aspose.Words per Java. Che tu sia un principiante o uno sviluppatore esperto, in questo articolo troverai preziosi approfondimenti ed esempi pratici.

## Iniziare

Prima di immergerci nei dettagli, configuriamo il nostro ambiente e creiamo un SDT di base. In questa sezione tratteremo i seguenti argomenti:

- Creazione di un nuovo documento
- Aggiunta di un tag al documento strutturato
- Salvataggio del documento

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crea un tag di documento strutturato di tipo CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Salva il documento
doc.save("WorkingWithSDT.docx");
```

## Controllo dello stato corrente di una casella di controllo SDT

Dopo aver aggiunto una casella di controllo SDT al documento, potresti voler controllare il suo stato corrente a livello di codice. Ciò può essere utile quando è necessario convalidare l'input dell'utente o eseguire azioni specifiche in base allo stato della casella di controllo.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // La casella di controllo è selezionata
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Modifica dei controlli del contenuto

In questa sezione esploreremo come modificare i controlli del contenuto all'interno del documento. Tratteremo tre tipi di controlli del contenuto: testo normale, elenco a discesa e immagine.

### Modifica del controllo del contenuto di testo normale

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Cancella il contenuto esistente
    sdtPlainText.removeAllChildren();

    // Aggiungi nuovo testo
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Modifica del controllo del contenuto dell'elenco a discesa

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Seleziona il secondo elemento dall'elenco
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Modifica del controllo del contenuto dell'immagine

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Sostituisci l'immagine con una nuova
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Creazione di un controllo contenuto ComboBox

Un controllo contenuto ComboBox consente agli utenti di selezionare da un elenco predefinito di opzioni. Creiamone uno nel nostro documento.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Lavorare con il controllo del contenuto Rich Text

I controlli del contenuto RTF sono perfetti per aggiungere testo formattato ai tuoi documenti. Creiamone uno e impostiamo il suo contenuto.

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

## Impostazione degli stili di controllo del contenuto

Puoi applicare stili ai controlli contenuto per migliorare l'aspetto visivo del tuo documento. Vediamo come impostare lo stile di un controllo contenuto.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Applica uno stile personalizzato
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Associazione di un SDT a dati XML personalizzati

In alcuni scenari potrebbe essere necessario associare un SDT a dati XML personalizzati per la generazione di contenuto dinamico. Esploriamo come raggiungere questo obiettivo.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Creazione di una tabella con sezioni ripetute mappate a dati XML personalizzati

Le tabelle con sezioni ripetute possono essere estremamente utili per presentare dati strutturati. Creiamo una tabella di questo tipo e la mappiamo ai dati XML personalizzati.

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

## Lavorare con tag di documenti strutturati multisezione

I tag dei documenti strutturati possono estendersi su più sezioni di un documento. In questa sezione esploreremo come lavorare con gli SDT multi-sezione.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Conclusione

tag dei documenti strutturati in Aspose.Words per Java forniscono un modo versatile per gestire e formattare il contenuto dei tuoi documenti. Che tu abbia bisogno di creare modelli, moduli o documenti dinamici, gli SDT offrono la flessibilità e il controllo di cui hai bisogno. Seguendo gli esempi e le linee guida forniti in questo articolo, puoi sfruttare la potenza degli SDT per migliorare le attività di elaborazione dei documenti.

## Domande frequenti

### Qual è lo scopo dei tag di documenti strutturati (SDT)?

I tag di documenti strutturati (SDT) hanno lo scopo di organizzare e formattare il contenuto all'interno dei documenti, semplificando la creazione di modelli, moduli e documenti strutturati.

### Come posso verificare lo stato attuale di un Checkbox SDT?

 Puoi controllare lo stato corrente di un Checkbox SDT utilizzando il file`setChecked` metodo, come dimostrato nell'articolo.

### Posso applicare stili ai controlli contenuto?

Sì, puoi applicare stili ai controlli contenuto per personalizzarne l'aspetto nel documento.

### È possibile associare un SDT a dati XML personalizzati?

Sì, puoi associare un SDT a dati XML personalizzati, consentendo la generazione di contenuti dinamici e la mappatura dei dati.

### Cosa sono le sezioni ripetute negli SDT?

Le sezioni ripetute negli SDT consentono di creare tabelle con dati dinamici, in cui le righe possono essere ripetute in base ai dati XML mappati.
---
title: Formatowanie tabel i style tabel w Aspose.Words dla Java
linktitle: Formatowanie tabel i style tabel
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak formatować tabele i stosować style tabel w Aspose.Words dla Java. Przeglądaj przewodniki krok po kroku z kodem źródłowym dotyczące efektywnego formatowania tabeli. Ulepsz układ swojego dokumentu za pomocą Aspose.Words.
type: docs
weight: 17
url: /pl/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Wprowadzenie do formatowania tabel i stylów tabel w Aspose.Words dla Java

Tabele odgrywają kluczową rolę w strukturyzowaniu i organizowaniu informacji w dokumentach. Aspose.Words dla Java zapewnia zaawansowane funkcje formatowania tabel i stosowania stylów tabel w celu zwiększenia atrakcyjności wizualnej dokumentów. W tym przewodniku krok po kroku zbadamy różne aspekty formatowania tabel i stosowania stylów tabel za pomocą Aspose.Words dla Java.

## Warunki wstępne

Zanim zagłębimy się w szczegóły, upewnij się, że masz zintegrowaną bibliotekę Aspose.Words for Java ze swoim projektem. Można go pobrać ze strony internetowej Aspose:[Pobierz Aspose.Words dla Javy](https://releases.aspose.com/words/java/).

## Uzyskaj odległość między tabelą a otaczającym tekstem

Na początek przyjrzyjmy się, jak sprawdzić odległość między tabelą a otaczającym ją tekstem w dokumencie.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Zastosuj obramowanie konturu do tabeli

Możesz wyrównać tabelę do środka strony, wyczyścić istniejące obramowania i ustawić niestandardową ramkę konspektu za pomocą tego kodu:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## Zbuduj stół z obramowaniami

Ten fragment kodu demonstruje, jak utworzyć tabelę i ustawić obramowania zarówno dla tabeli, jak i jej komórek:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Zmodyfikuj formatowanie wierszy

Dowiedz się, jak modyfikować formatowanie określonego wiersza w tabeli:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Zastosuj formatowanie wierszy

Ten przykład ilustruje, jak zastosować formatowanie do całego wiersza w tabeli:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Ustaw dopełnienie komórek

Dowiedz się, jak ustawić dopełnienie poszczególnych komórek w tabeli:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Zmodyfikuj formatowanie komórek

Dowiedz się, jak zmodyfikować formatowanie określonej komórki w tabeli:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formatuj tabelę i komórkę z różnymi obramowaniami

Dowiedz się, jak ustawić różne obramowania dla poszczególnych komórek w tabeli:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Ustaw krawędzie tabeli
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Ustaw cieniowanie komórek dla poszczególnych komórek
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Dodaj zawartość do komórek
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Wyczyść formatowanie komórek dla następnego wiersza
builder.getCellFormat().clearFormatting();
// Utwórz większe obramowanie dla pierwszej komórki tego wiersza
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Ustaw tytuł i opis tabeli

Dodaj tytuł i opis do swojej tabeli:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Krok 10: Zezwól na odstępy między komórkami

Zezwól na odstępy między komórkami i ustaw ich wartość dla tabeli:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Krok 11: Zbuduj stół ze stylem

Utwórz tabelę z predefiniowanym stylem:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Krok 12: Rozwiń formatowanie komórek i wierszy ze stylu

Dowiedz się, jak rozwinąć style tabeli, aby zastosować formatowanie do komórek i wierszy:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Krok 13: Utwórz styl tabeli

Utwórz niestandardowy styl tabeli z określonym formatowaniem:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Krok 14: Zdefiniuj formatowanie warunkowe

Zastosuj formatowanie warunkowe do wierszy w tabeli:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Krok 15: Ustaw formatowanie komórek tabeli

Ustaw specyficzne formatowanie dla poszczególnych komórek:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Krok 16: Ustaw formatowanie wierszy tabeli

Zastosuj formatowanie do całych wierszy w tabeli:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Wniosek

Aspose.Words dla Java umożliwia precyzyjne formatowanie tabel i stosowanie stylów tabel. Od modyfikowania formatowania poszczególnych komórek po tworzenie niestandardowych stylów tabel — masz narzędzia, dzięki którym Twoje dokumenty będą atrakcyjne wizualnie i uporządkowane.

## Często zadawane pytania

### Jak pobrać Aspose.Words dla Java?

 Możesz pobrać Aspose.Words dla Java ze strony internetowej Aspose:[Pobierz Aspose.Words dla Javy](https://releases.aspose.com/words/java/).

### Czy mogę zastosować różne obramowania do poszczególnych komórek w tabeli?

Tak, możesz ustawić różne obramowania dla poszczególnych komórek w tabeli za pomocą Aspose.Words dla Java, jak pokazano w tym przewodniku.

### Jaki jest cel ustawienia tytułu i opisu tabeli?

Ustawienie tytułu i opisu tabeli poprawia dostępność i organizację dokumentu, ułatwiając czytelnikom i technologiom pomocniczym zrozumienie treści.

### Jak zastosować formatowanie warunkowe do określonych wierszy tabeli?

Możesz zastosować formatowanie warunkowe do określonych wierszy tabeli, definiując niestandardowe style tabeli z regułami formatowania warunkowego, jak pokazano w tym przewodniku.

### Gdzie mogę znaleźć więcej dokumentacji i zasobów dotyczących Aspose.Words dla Java?

 Aby uzyskać obszerną dokumentację i dodatkowe zasoby, odwiedź dokumentację Aspose.Words for Java:[Aspose.Words dla dokumentacji Java](https://reference.aspose.com/words/java/).
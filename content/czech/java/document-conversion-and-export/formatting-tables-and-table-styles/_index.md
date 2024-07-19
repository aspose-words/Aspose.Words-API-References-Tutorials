---
title: Formátování tabulek a stylů tabulek v Aspose.Words pro Javu
linktitle: Formátování tabulek a stylů tabulek
second_title: Aspose.Words Java Document Processing API
description: Naučte se formátovat tabulky a používat styly tabulek v Aspose.Words for Java. Prozkoumejte podrobné průvodce se zdrojovým kódem pro efektivní formátování tabulek. Vylepšete rozvržení dokumentu pomocí Aspose.Words.
type: docs
weight: 17
url: /cs/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Úvod do formátování tabulek a stylů tabulek v Aspose.Words pro Javu

Tabulky hrají zásadní roli při strukturování a organizování informací v dokumentech. Aspose.Words for Java poskytuje výkonné funkce pro formátování tabulek a použití stylů tabulek pro zvýšení vizuální přitažlivosti vašich dokumentů. V tomto podrobném průvodci prozkoumáme různé aspekty formátování tabulek a použití stylů tabulek pomocí Aspose.Words for Java.

## Předpoklady

Než se ponoříme do podrobností, ujistěte se, že máte do projektu integrovanou knihovnu Aspose.Words for Java. Můžete si jej stáhnout z webu Aspose:[Stáhněte si Aspose.Words pro Java](https://releases.aspose.com/words/java/).

## Získejte vzdálenost mezi tabulkou a okolním textem

Nejprve prozkoumáme, jak načíst vzdálenost mezi tabulkou a okolním textem v dokumentu.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Použít ohraničení obrysu na tabulku

Pomocí tohoto kódu můžete zarovnat tabulku na střed stránky, vymazat existující ohraničení a nastavit vlastní ohraničení obrysu:

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

## Sestavte stůl s hranicemi

Tento fragment kódu ukazuje, jak vytvořit tabulku a nastavit ohraničení pro tabulku i její buňky:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Upravit formátování řádků

Přečtěte si, jak upravit formátování konkrétního řádku v tabulce:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Použít formátování řádků

Tento příklad ukazuje, jak použít formátování na celý řádek v tabulce:

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

## Nastavte odsazení buněk

Prozkoumejte, jak nastavit odsazení pro jednotlivé buňky v tabulce:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Upravit formátování buněk

Zjistěte, jak upravit formátování konkrétní buňky v tabulce:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formát tabulky a buňky s různými hranicemi

Naučte se, jak nastavit různá ohraničení pro jednotlivé buňky v tabulce:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Nastavte okraje tabulky
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Nastavte stínování buněk pro jednotlivé buňky
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Přidejte obsah do buněk
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Vymazat formátování buňky pro další řádek
builder.getCellFormat().clearFormatting();
// Vytvořte větší ohraničení pro první buňku tohoto řádku
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Nastavte název a popis tabulky

Přidejte do tabulky název a popis:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Krok 10: Povolte mezery mezi buňkami

Povolte mezery mezi buňkami a nastavte jejich hodnotu pro tabulku:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Krok 11: Sestavte stůl se stylem

Vytvořte tabulku s předdefinovaným stylem:

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

## Krok 12: Rozbalte položku Formátování na buňkách a řádcích ze Stylu

Zjistěte, jak rozšířit styly tabulek a použít formátování na buňky a řádky:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Krok 13: Vytvořte styl tabulky

Vytvořte vlastní styl tabulky se specifickým formátováním:

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

## Krok 14: Definujte podmíněné formátování

Použití podmíněného formátování na řádky v tabulce:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Krok 15: Nastavte formátování TableCell

Nastavte konkrétní formátování pro jednotlivé buňky:

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

## Krok 16: Nastavte formátování TableRow

Použít formátování na celé řádky v tabulce:

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

## Závěr

Aspose.Words for Java vám umožňuje přesně formátovat tabulky a aplikovat styly tabulek. Od úpravy formátování jednotlivých buněk až po vytváření vlastních stylů tabulek máte k dispozici nástroje, díky kterým budou vaše dokumenty vizuálně přitažlivé a uspořádané.

## FAQ

### Jak si stáhnu Aspose.Words for Java?

 Aspose.Words for Java si můžete stáhnout z webu Aspose:[Stáhněte si Aspose.Words pro Java](https://releases.aspose.com/words/java/).

### Mohu použít různá ohraničení na jednotlivé buňky v tabulce?

Ano, pomocí Aspose.Words for Java můžete nastavit různá ohraničení pro jednotlivé buňky v tabulce, jak je ukázáno v této příručce.

### Jaký je účel nastavení názvu a popisu tabulky?

Nastavení názvu tabulky a popisu zlepšuje přístupnost a organizaci vašeho dokumentu a usnadňuje čtenářům a pomocným technologiím porozumění obsahu.

### Jak mohu použít podmíněné formátování na konkrétní řádky v tabulce?

Podmíněné formátování můžete použít na konkrétní řádky v tabulce definováním vlastních stylů tabulky pomocí pravidel podmíněného formátování, jak je uvedeno v této příručce.

### Kde najdu další dokumentaci a zdroje pro Aspose.Words for Java?

 Kompletní dokumentaci a další zdroje naleznete v dokumentaci Aspose.Words for Java:[Aspose.Words pro dokumentaci Java](https://reference.aspose.com/words/java/).
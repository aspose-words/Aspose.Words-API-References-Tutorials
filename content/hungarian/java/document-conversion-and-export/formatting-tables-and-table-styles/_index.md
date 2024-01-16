---
title: Táblázatok és táblázatstílusok formázása az Aspose.Words for Java programban
linktitle: Táblázatok és táblázatstílusok formázása
second_title: Aspose.Words Java Document Processing API
description: Ismerje meg, hogyan formázhat táblázatokat és hogyan alkalmazhat táblázatstílusokat az Aspose.Words for Java programban. Fedezze fel a forráskóddal ellátott, lépésenkénti útmutatókat a hatékony táblázatformázás érdekében. Javítsa dokumentum-elrendezését az Aspose.Words segítségével.
type: docs
weight: 17
url: /hu/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Bevezetés a táblák és táblázatstílusok formázásához az Aspose.Words for Java programban

A táblázatok döntő szerepet játszanak a dokumentumokban található információk strukturálásában és rendszerezésében. Az Aspose.Words for Java hatékony szolgáltatásokat nyújt a táblázatok formázásához és táblázatstílusok alkalmazásához, hogy javítsa a dokumentumok vizuális vonzerejét. Ebben a lépésenkénti útmutatóban a táblázatok formázásának és a táblázatstílusok Aspose.Words for Java használatával történő alkalmazásának különböző szempontjait vizsgáljuk meg.

## Előfeltételek

Mielőtt belemerülnénk a részletekbe, győződjön meg arról, hogy az Aspose.Words for Java könyvtár integrálva van a projektjébe. Letöltheti az Aspose webhelyéről:[Töltse le az Aspose.Words for Java programot](https://releases.aspose.com/words/java/).

## Mérje meg a távolságot a táblázat és a környező szöveg között

Kezdésként nézzük meg, hogyan lehet lekérni a táblázat és a környező szöveg közötti távolságot a dokumentumban.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Alkalmazza a körvonalszegélyt egy táblázatra

Ezzel a kóddal egy táblázatot igazíthat az oldal közepéhez, törölheti a meglévő szegélyeket, és egyéni körvonalkeretet állíthat be:

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

## Készítsen táblázatot szegélyekkel

Ez a kódrészlet bemutatja, hogyan hozhat létre táblázatot, és hogyan állíthat be szegélyeket a táblázathoz és celláihoz:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Sorformázás módosítása

Ismerje meg, hogyan módosíthatja egy adott sor formázását egy táblázaton belül:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Sorformázás alkalmazása

Ez a példa bemutatja, hogyan alkalmazhat formázást egy táblázat teljes sorára:

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

## Állítsa be a Cell Padding

Fedezze fel, hogyan állíthat be kitöltést a táblázat egyes celláihoz:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Cellaformázás módosítása

Fedezze fel, hogyan módosíthatja egy adott cella formázását egy táblázaton belül:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formázza a táblázatot és a cellát különböző szegéllyel

Ismerje meg, hogyan állíthat be különböző szegélyeket a táblázat egyes celláihoz:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Állítsa be a táblázat határait
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Cellaárnyékolás beállítása az egyes cellákhoz
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Adjon hozzá tartalmat a cellákhoz
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Törölje a következő sor cellaformázását
builder.getCellFormat().clearFormatting();
// Hozzon létre nagyobb kereteket a sor első cellájához
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Állítsa be a táblázat címét és leírását

Adjon hozzá címet és leírást a táblázathoz:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## 10. lépés: Cellaköz engedélyezése

Cellatávolság engedélyezése és értékének beállítása egy táblázathoz:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## 11. lépés: Készítsen asztalt stílussal

Hozzon létre egy táblázatot előre meghatározott stílussal:

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

## 12. lépés: Bontsa ki a Formázást cellákon és sorokon a Stílusból

Ismerje meg, hogyan bővítheti ki a táblázatstílusokat a cellák és sorok formázásának alkalmazásához:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## 13. lépés: Hozzon létre egy táblázatstílust

Hozzon létre egyéni táblázatstílust meghatározott formázással:

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

## 14. lépés: Határozza meg a feltételes formázást

Feltételes formázás alkalmazása a táblázat soraiban:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## 15. lépés: Állítsa be a TableCell formázást

Állítson be egyedi formázást az egyes cellákhoz:

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

## 16. lépés: Állítsa be a TableRow formázást

Formázás alkalmazása a táblázat teljes soraira:

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

## Következtetés

Az Aspose.Words for Java lehetővé teszi a táblázatok formázását és a táblázatstílusok precíz alkalmazását. Az egyedi cellaformázás módosításától az egyéni táblázatstílusok létrehozásáig rendelkezésre állnak az eszközök, amelyekkel a dokumentumokat vizuálisan vonzóvá és rendszerezetté teheti.

## GYIK

### Hogyan tölthetem le az Aspose.Words for Java programot?

 Az Aspose.Words for Java letölthető az Aspose webhelyéről:[Töltse le az Aspose.Words for Java programot](https://releases.aspose.com/words/java/).

### Alkalmazhatok különböző szegélyeket egy táblázat egyes celláira?

Igen, az Aspose.Words for Java használatával különböző szegélyeket állíthat be egy táblázaton belüli egyes cellákhoz, amint az ebben az útmutatóban látható.

### Mi a célja a táblázat címének és leírásának?

A táblázat címének és leírásának beállítása javítja a dokumentum hozzáférhetőségét és rendszerezését, így az olvasók és a kisegítő technológiák könnyebben megérthetik a tartalmat.

### Hogyan alkalmazhatom a feltételes formázást a táblázat adott soraira?

Feltételes formázást alkalmazhat a táblázat adott soraira úgy, hogy egyéni táblázatstílusokat definiál feltételes formázási szabályokkal, amint az ebben az útmutatóban látható.

### Hol találok további dokumentációt és forrásokat az Aspose.Words for Java-hoz?

 Átfogó dokumentációért és további forrásokért keresse fel az Aspose.Words for Java dokumentációját:[Aspose.Words for Java Documentation](https://reference.aspose.com/words/java/).
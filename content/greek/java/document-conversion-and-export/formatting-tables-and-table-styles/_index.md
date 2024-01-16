---
title: Μορφοποίηση πινάκων και στυλ πίνακα στο Aspose.Words για Java
linktitle: Μορφοποίηση πινάκων και στυλ πίνακα
second_title: Aspose.Words Java Document Processing API
description: Μάθετε πώς να μορφοποιείτε πίνακες και να εφαρμόζετε στυλ πίνακα στο Aspose.Words για Java. Εξερευνήστε βήμα προς βήμα οδηγούς με πηγαίο κώδικα για αποτελεσματική μορφοποίηση πίνακα. Βελτιώστε τη διάταξη του εγγράφου σας με το Aspose.Words.
type: docs
weight: 17
url: /el/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Εισαγωγή στη μορφοποίηση πινάκων και στυλ πίνακα στο Aspose.Words για Java

Οι πίνακες διαδραματίζουν κρίσιμο ρόλο στη δομή και την οργάνωση των πληροφοριών στα έγγραφα. Το Aspose.Words για Java παρέχει ισχυρές δυνατότητες για τη μορφοποίηση πινάκων και την εφαρμογή στυλ πινάκων για τη βελτίωση της οπτικής ελκυστικότητας των εγγράφων σας. Σε αυτόν τον οδηγό βήμα προς βήμα, θα εξερευνήσουμε διάφορες πτυχές της μορφοποίησης των πινάκων και της εφαρμογής στυλ πινάκων χρησιμοποιώντας το Aspose.Words για Java.

## Προαπαιτούμενα

Πριν βουτήξουμε στις λεπτομέρειες, βεβαιωθείτε ότι έχετε ενσωματωμένη τη βιβλιοθήκη Aspose.Words for Java στο έργο σας. Μπορείτε να το κατεβάσετε από τον ιστότοπο Aspose:[Κατεβάστε το Aspose.Words για Java](https://releases.aspose.com/words/java/).

## Αποκτήστε απόσταση μεταξύ του πίνακα και του περιβάλλοντος κειμένου

Αρχικά, ας εξερευνήσουμε πώς να ανακτήσετε την απόσταση μεταξύ ενός πίνακα και του περιβάλλοντος κειμένου σε ένα έγγραφο.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Εφαρμογή περιγράμματος περιγράμματος σε έναν πίνακα

Μπορείτε να στοιχίσετε έναν πίνακα στο κέντρο της σελίδας, να διαγράψετε τα υπάρχοντα περιγράμματα και να ορίσετε ένα προσαρμοσμένο περίγραμμα περιγράμματος με αυτόν τον κωδικό:

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

## Φτιάξτε έναν πίνακα με σύνορα

Αυτό το απόσπασμα κώδικα δείχνει πώς να δημιουργήσετε έναν πίνακα και να ορίσετε περιθώρια τόσο για τον πίνακα όσο και για τα κελιά του:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Τροποποίηση μορφοποίησης σειράς

Μάθετε πώς μπορείτε να τροποποιήσετε τη μορφοποίηση μιας συγκεκριμένης σειράς σε έναν πίνακα:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Εφαρμογή μορφοποίησης σειράς

Αυτό το παράδειγμα δείχνει πώς να εφαρμόσετε μορφοποίηση σε μια ολόκληρη σειρά σε έναν πίνακα:

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

## Ρύθμιση γεμίσματος κυττάρων

Εξερευνήστε πώς να ρυθμίσετε την αναπλήρωση για μεμονωμένα κελιά σε έναν πίνακα:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Τροποποίηση μορφοποίησης κελιού

Ανακαλύψτε πώς μπορείτε να τροποποιήσετε τη μορφοποίηση ενός συγκεκριμένου κελιού σε έναν πίνακα:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Μορφοποίηση πίνακα και κελιού με διαφορετικά περιγράμματα

Μάθετε πώς να ορίζετε διαφορετικά περιγράμματα για μεμονωμένα κελιά σε έναν πίνακα:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Ορίστε τα περιγράμματα του πίνακα
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Ορισμός σκίασης κελιών για μεμονωμένα κελιά
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Προσθέστε περιεχόμενο στα κελιά
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Εκκαθάριση μορφοποίησης κελιών για την επόμενη σειρά
builder.getCellFormat().clearFormatting();
// Δημιουργήστε μεγαλύτερα περιγράμματα για το πρώτο κελί αυτής της σειράς
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Ορισμός τίτλου και περιγραφής πίνακα

Προσθέστε έναν τίτλο και μια περιγραφή στον πίνακά σας:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Βήμα 10: Επιτρέψτε το διάστημα κελιών

Επιτρέψτε το διάστημα κελιών και ορίστε την τιμή του για έναν πίνακα:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Βήμα 11: Δημιουργήστε έναν πίνακα με στυλ

Δημιουργήστε έναν πίνακα με προκαθορισμένο στυλ:

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

## Βήμα 12: Αναπτύξτε τη Μορφοποίηση σε κελιά και σειρές από το στυλ

Μάθετε πώς να επεκτείνετε τα στυλ πίνακα για να εφαρμόσετε μορφοποίηση σε κελιά και σειρές:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Βήμα 13: Δημιουργήστε ένα στυλ πίνακα

Δημιουργήστε ένα προσαρμοσμένο στυλ πίνακα με συγκεκριμένη μορφοποίηση:

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

## Βήμα 14: Ορισμός μορφοποίησης υπό όρους

Εφαρμογή μορφοποίησης υπό όρους σε σειρές σε έναν πίνακα:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Βήμα 15: Ορισμός μορφοποίησης TableCell

Ορίστε συγκεκριμένη μορφοποίηση για μεμονωμένα κελιά:

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

## Βήμα 16: Ορίστε τη μορφοποίηση TableRow

Εφαρμογή μορφοποίησης σε ολόκληρες σειρές σε έναν πίνακα:

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

## συμπέρασμα

Το Aspose.Words για Java σάς δίνει τη δυνατότητα να μορφοποιείτε πίνακες και να εφαρμόζετε στυλ πίνακα με ακρίβεια. Από την τροποποίηση της μορφοποίησης μεμονωμένων κελιών έως τη δημιουργία προσαρμοσμένων στυλ πίνακα, έχετε τα εργαλεία για να κάνετε τα έγγραφά σας οπτικά ελκυστικά και οργανωμένα.

## Συχνές ερωτήσεις

### Πώς μπορώ να κατεβάσω το Aspose.Words για Java;

 Μπορείτε να κατεβάσετε το Aspose.Words για Java από τον ιστότοπο Aspose:[Κατεβάστε το Aspose.Words για Java](https://releases.aspose.com/words/java/).

### Μπορώ να εφαρμόσω διαφορετικά περιγράμματα σε μεμονωμένα κελιά ενός πίνακα;

Ναι, μπορείτε να ορίσετε διαφορετικά περιγράμματα για μεμονωμένα κελιά σε έναν πίνακα χρησιμοποιώντας το Aspose.Words για Java, όπως φαίνεται σε αυτόν τον οδηγό.

### Ποιος είναι ο σκοπός της ρύθμισης τίτλου και περιγραφής πίνακα;

Η ρύθμιση τίτλου και περιγραφής πίνακα βελτιώνει την προσβασιμότητα και την οργάνωση του εγγράφου σας, διευκολύνοντας τους αναγνώστες και τις βοηθητικές τεχνολογίες να κατανοήσουν το περιεχόμενο.

### Πώς μπορώ να εφαρμόσω μορφοποίηση υπό όρους σε συγκεκριμένες σειρές ενός πίνακα;

Μπορείτε να εφαρμόσετε μορφοποίηση υπό όρους σε συγκεκριμένες σειρές σε έναν πίνακα ορίζοντας προσαρμοσμένα στυλ πίνακα με κανόνες μορφοποίησης υπό όρους, όπως φαίνεται σε αυτόν τον οδηγό.

### Πού μπορώ να βρω περισσότερη τεκμηρίωση και πόρους για το Aspose.Words για Java;

 Για ολοκληρωμένη τεκμηρίωση και πρόσθετους πόρους, επισκεφθείτε την τεκμηρίωση του Aspose.Words για Java:[Aspose.Words for Java Documentation](https://reference.aspose.com/words/java/).
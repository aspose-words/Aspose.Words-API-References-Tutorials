---
title: Χρήση σχημάτων εγγράφων στο Aspose.Words για Java
linktitle: Χρήση σχημάτων εγγράφων
second_title: Aspose.Words Java Document Processing API
description: Ξεκλειδώστε τη δύναμη των σχημάτων εγγράφων στο Aspose.Words για Java. Μάθετε να δημιουργείτε οπτικά ελκυστικά έγγραφα με παραδείγματα βήμα προς βήμα.
type: docs
weight: 14
url: /el/java/document-conversion-and-export/using-document-shapes/
---

## Εισαγωγή στη χρήση σχημάτων εγγράφων στο Aspose.Words για Java

Σε αυτόν τον περιεκτικό οδηγό, θα εμβαθύνουμε στον κόσμο των σχημάτων εγγράφων στο Aspose.Words για Java. Τα σχήματα είναι απαραίτητα στοιχεία όταν πρόκειται για τη δημιουργία οπτικά ελκυστικών και διαδραστικών εγγράφων. Είτε θέλετε να προσθέσετε μηνύματα προώθησης, κουμπιά, εικόνες ή υδατογραφήματα, το Aspose.Words για Java παρέχει τα εργαλεία για να το κάνετε αποτελεσματικά. Ας εξερευνήσουμε πώς να χρησιμοποιήσουμε αυτά τα σχήματα βήμα προς βήμα με παραδείγματα πηγαίου κώδικα.

## Ξεκινώντας με τα σχήματα εγγράφων

 Πριν μεταβούμε στον κώδικα, ας ρυθμίσουμε το περιβάλλον μας. Βεβαιωθείτε ότι έχετε ενσωματώσει το Aspose.Words for Java στο έργο σας. Εάν δεν το έχετε κάνει ήδη, μπορείτε να το κατεβάσετε από τον ιστότοπο του Aspose[Κατεβάστε το Aspose.Words για Java](https://releases.aspose.com/words/java/)

## Προσθήκη σχημάτων σε έγγραφα

### Εισαγωγή σχήματος ομάδας

 ΕΝΑ`GroupShape` σας επιτρέπει να ομαδοποιήσετε πολλά σχήματα μαζί. Δείτε πώς μπορείτε να δημιουργήσετε και να εισαγάγετε ένα`GroupShape`:

```java
Document doc = new Document();
doc.ensureMinimum();

GroupShape groupShape = new GroupShape(doc);
Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1);
accentBorderShape.setWidth(100.0);
accentBorderShape.setHeight(100.0);

groupShape.appendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
actionButtonShape.setLeft(100.0);
actionButtonShape.setWidth(100.0);
actionButtonShape.setHeight(200.0);

groupShape.appendChild(actionButtonShape);

groupShape.setWidth(200.0);
groupShape.setHeight(200.0);
groupShape.setCoordSize(new Dimension(200, 200));

DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertNode(groupShape);

doc.save("Your Directory Path" + "WorkingWithShapes.AddGroupShape.docx");
```

### Εισαγωγή σχήματος πλαισίου κειμένου

 Για να εισαγάγετε ένα σχήμα πλαισίου κειμένου, μπορείτε να χρησιμοποιήσετε το`insertShape` μέθοδος όπως φαίνεται στο παρακάτω παράδειγμα:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
    RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);

shape.setRotation(30.0);
builder.writeln();

shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
shape.setRotation(30.0);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);

doc.save("Your Directory Path" + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Χειρισμός ιδιοτήτων σχήματος

### Διαχείριση αναλογίας διαστάσεων

Μπορείτε να ελέγξετε εάν η αναλογία διαστάσεων ενός σχήματος είναι κλειδωμένη ή όχι. Δείτε πώς μπορείτε να ξεκλειδώσετε την αναλογία διαστάσεων ενός σχήματος:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Τοποθέτηση ενός σχήματος σε ένα κελί πίνακα

Εάν πρέπει να τοποθετήσετε ένα σχήμα μέσα σε ένα κελί πίνακα, μπορείτε να το πετύχετε με τον ακόλουθο κώδικα:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.startTable();
builder.getRowFormat().setHeight(100.0);
builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);

for (int i = 0; i < 31; i++) {
    if (i != 0 && i % 7 == 0)
        builder.endRow();

    builder.insertCell();
    builder.write("Cell contents");
}

builder.endTable();

Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.isLayoutInCell(true); // Εμφανίστε το σχήμα έξω από το κελί του πίνακα εάν θα τοποθετηθεί σε ένα κελί.
watermark.setWidth(300.0);
watermark.setHeight(70.0);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setRotation(-40);
watermark.setFillColor(Color.GRAY);
watermark.setStrokeColor(Color.GRAY);
watermark.getTextPath().setText("watermarkText");
watermark.getTextPath().setFontFamily("Arial");
watermark.setName("WaterMark_{Guid.NewGuid()}");
watermark.setWrapType(WrapType.NONE);

Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
builder.moveTo(run);
builder.insertNode(watermark);

doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
doc.save("Your Directory Path" + "WorkingWithShapes.LayoutInCell.docx");
```

## Εργασία με Σχήματα SmartArt

### Ανίχνευση σχημάτων SmartArt

Μπορείτε να εντοπίσετε σχήματα SmartArt σε ένα έγγραφο χρησιμοποιώντας τον ακόλουθο κώδικα:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### Ενημέρωση σχεδίων SmartArt

Για να ενημερώσετε τα σχέδια SmartArt σε ένα έγγραφο, χρησιμοποιήστε τον ακόλουθο κώδικα:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## συμπέρασμα

Σε αυτόν τον οδηγό, εξερευνήσαμε τον κόσμο των σχημάτων εγγράφων στο Aspose.Words για Java. Έχετε μάθει πώς να προσθέτετε διάφορα σχήματα στα έγγραφά σας, να χειρίζεστε τις ιδιότητές τους και να εργάζεστε με σχήματα SmartArt. Με αυτή τη γνώση, μπορείτε να δημιουργήσετε εύκολα οπτικά ελκυστικά και διαδραστικά έγγραφα.

## Συχνές ερωτήσεις

### Τι είναι το Aspose.Words για Java;

Το Aspose.Words για Java είναι μια βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να δημιουργούν, να τροποποιούν και να μετατρέπουν έγγραφα του Word μέσω προγραμματισμού. Παρέχει ένα ευρύ φάσμα δυνατοτήτων και εργαλείων για εργασία με έγγραφα σε διάφορες μορφές.

### Πώς μπορώ να κατεβάσω το Aspose.Words για Java;

 Μπορείτε να κάνετε λήψη του Aspose.Words για Java από τον ιστότοπο Aspose ακολουθώντας αυτόν τον σύνδεσμο:[Κατεβάστε το Aspose.Words για Java](https://releases.aspose.com/words/java/)

### Ποια είναι τα οφέλη από τη χρήση σχημάτων εγγράφων;

Τα σχήματα εγγράφων προσθέτουν οπτικά στοιχεία και διαδραστικότητα στα έγγραφά σας, καθιστώντας τα πιο ελκυστικά και ενημερωτικά. Με τα σχήματα, μπορείτε να δημιουργήσετε μηνύματα προώθησης, κουμπιά, εικόνες, υδατογραφήματα και άλλα, βελτιώνοντας τη συνολική εμπειρία χρήστη.

### Μπορώ να προσαρμόσω την εμφάνιση των σχημάτων;

Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των σχημάτων προσαρμόζοντας τις ιδιότητές τους όπως το μέγεθος, τη θέση, την περιστροφή και το χρώμα πλήρωσης. Το Aspose.Words για Java παρέχει εκτενείς επιλογές για προσαρμογή σχήματος.

### Είναι το Aspose.Words για Java συμβατό με το SmartArt;

Ναι, το Aspose.Words για Java υποστηρίζει σχήματα SmartArt, επιτρέποντάς σας να εργάζεστε με πολύπλοκα διαγράμματα και γραφικά στα έγγραφά σας.
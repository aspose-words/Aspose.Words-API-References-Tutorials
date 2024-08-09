---
title: Προηγμένες επιλογές αποθήκευσης εγγράφων HTML με το Aspose.Words Java
linktitle: Αποθήκευση εγγράφων HTML με
second_title: Aspose.Words Java Document Processing API
description: Σε αυτό το σεμινάριο, έχουμε καλύψει διάφορες προηγμένες επιλογές αποθήκευσης εγγράφων HTML με το Aspose.Words για Java. Αυτές οι επιλογές σάς δίνουν τη δυνατότητα να δημιουργήσετε HTML υψηλής ποιότητας
type: docs
weight: 16
url: /el/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Σε αυτό το σεμινάριο, θα εξερευνήσουμε τις προηγμένες επιλογές αποθήκευσης εγγράφων HTML που παρέχονται από το Aspose.Words για Java. Το Aspose.Words είναι ένα ισχυρό API Java για εργασία με έγγραφα του Word και προσφέρει ένα ευρύ φάσμα δυνατοτήτων για χειρισμό και μετατροπή εγγράφων.

## 1. Εισαγωγή
Το Aspose.Words για Java σάς επιτρέπει να εργάζεστε με έγγραφα του Word μέσω προγραμματισμού. Σε αυτό το σεμινάριο, θα επικεντρωθούμε σε προηγμένες επιλογές αποθήκευσης εγγράφων HTML, οι οποίες σας επιτρέπουν να ελέγχετε τον τρόπο μετατροπής των εγγράφων του Word σε HTML.

## 2. Εξαγωγή πληροφοριών μετ' επιστροφής
 Ο`exportRoundtripInformation` Η μέθοδος σάς επιτρέπει να εξάγετε έγγραφα του Word σε HTML διατηρώντας ταυτόχρονα τις πληροφορίες μετ' επιστροφής. Αυτές οι πληροφορίες μπορεί να είναι χρήσιμες όταν θέλετε να μετατρέψετε την HTML ξανά σε μορφή Word χωρίς να χάσετε λεπτομέρειες σχετικά με το έγγραφο.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Εξαγωγή γραμματοσειρών ως Base64
 Με το`exportFontsAsBase64` Με τη μέθοδο, μπορείτε να εξάγετε γραμματοσειρές που χρησιμοποιούνται στο έγγραφο ως δεδομένα κωδικοποιημένα με Base64 σε HTML. Αυτό διασφαλίζει ότι η αναπαράσταση HTML διατηρεί τα ίδια στυλ γραμματοσειράς με το αρχικό έγγραφο του Word.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Εξαγωγή Πόρων
 Ο`exportResources` Η μέθοδος σάς επιτρέπει να καθορίσετε τον τύπο του φύλλου στυλ CSS και να εξάγετε πόρους γραμματοσειράς. Μπορείτε επίσης να ορίσετε έναν φάκελο πόρων και ένα ψευδώνυμο για πόρους στο HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Μετατρέψτε τα Metafiles σε EMF ή WMF
 Ο`convertMetafilesToEmfOrWmf`Η μέθοδος σάς επιτρέπει να μετατρέψετε μετα-αρχεία στο έγγραφο είτε σε μορφή EMF είτε σε μορφή WMF, διασφαλίζοντας συμβατότητα και ομαλή απόδοση σε HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Το απόσπασμα κώδικα δεν εμφανίζεται για συντομία.
}
```

## 6. Μετατρέψτε τα Metafiles σε SVG
 Χρησιμοποιήστε το`convertMetafilesToSvg` μέθοδος μετατροπής μετα-αρχείων σε μορφή SVG. Αυτή η μορφή είναι ιδανική για την εμφάνιση διανυσματικών γραφικών σε έγγραφα HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Το απόσπασμα κώδικα δεν εμφανίζεται για συντομία.
}
```

## 7. Προσθέστε το πρόθεμα ονόματος κλάσης CSS
 Με το`addCssClassNamePrefix` μέθοδο, μπορείτε να προσθέσετε ένα πρόθεμα σε ονόματα κλάσεων CSS στο εξαγόμενο HTML. Αυτό βοηθά στην αποφυγή διενέξεων με υπάρχοντα στυλ.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Εξαγωγή διευθύνσεων URL CID για πόρους MHTML
 Ο`exportCidUrlsForMhtmlResources` Η μέθοδος χρησιμοποιείται κατά την αποθήκευση εγγράφων σε μορφή MHTML. Επιτρέπει την εξαγωγή διευθύνσεων URL Content-ID για πόρους.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Το απόσπασμα κώδικα δεν εμφανίζεται για συντομία.
}
```

## 9. Επίλυση ονομάτων γραμματοσειρών
 Ο`resolveFontNames` Η μέθοδος βοηθά στην επίλυση ονομάτων γραμματοσειρών κατά την αποθήκευση εγγράφων σε μορφή HTML, διασφαλίζοντας συνεπή απόδοση σε διαφορετικές πλατφόρμες.

```java
@Test
public void resolveFontNames() throws Exception {
    // Το απόσπασμα κώδικα δεν εμφανίζεται για συντομία.
}
```

## 10. Εξαγωγή πεδίου φόρμας εισαγωγής κειμένου ως κείμενο
 Ο`exportTextInputFormFieldAsText` Οι εξαγωγές μεθόδου σχηματίζουν πεδία ως απλό κείμενο στο HTML, καθιστώντας τα εύκολα αναγνώσιμα και επεξεργάσιμα.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Το απόσπασμα κώδικα δεν εμφανίζεται για συντομία.
}
```

## 11. Συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τις προηγμένες επιλογές αποθήκευσης εγγράφων HTML που παρέχονται από το Aspose.Words για Java. Αυτές οι επιλογές σάς δίνουν λεπτομερή έλεγχο της διαδικασίας μετατροπής, επιτρέποντάς σας να δημιουργήσετε έγγραφα HTML που μοιάζουν πολύ με τα αρχικά έγγραφα του Word.

## 12. Συχνές ερωτήσεις
Ακολουθούν ορισμένες συχνές ερωτήσεις σχετικά με την εργασία με το Aspose.Words for Java και τις επιλογές αποθήκευσης εγγράφων HTML:

### Ε1: Πώς μπορώ να μετατρέψω την HTML ξανά σε μορφή Word χρησιμοποιώντας το Aspose.Words για Java;
 Για να μετατρέψετε την HTML ξανά σε μορφή Word, μπορείτε να χρησιμοποιήσετε τα API του Aspose.Words`load` μέθοδος για να φορτώσετε το έγγραφο HTML και στη συνέχεια να το αποθηκεύσετε σε μορφή Word.

### Ε2: Μπορώ να προσαρμόσω τα στυλ CSS κατά την εξαγωγή σε HTML;
 Ναι, μπορείτε να προσαρμόσετε τα στυλ CSS τροποποιώντας τα φύλλα στυλ που χρησιμοποιούνται στο HTML ή χρησιμοποιώντας το`addCssClassNamePrefix` μέθοδος για να προσθέσετε ένα πρόθεμα στα ονόματα κλάσεων CSS.

### Ε3: Υπάρχει τρόπος να βελτιστοποιήσετε την έξοδο HTML για την προβολή Ιστού;
Ναι, μπορείτε να βελτιστοποιήσετε την έξοδο HTML για προβολή Ιστού διαμορφώνοντας επιλογές όπως η εξαγωγή γραμματοσειρών ως Base64 και η μετατροπή μετα-αρχείων σε SVG.

### Ε4: Υπάρχουν περιορισμοί κατά τη μετατροπή σύνθετων εγγράφων του Word σε HTML;
Ενώ το Aspose.Words για Java παρέχει ισχυρές δυνατότητες μετατροπής, πολύπλοκα έγγραφα του Word με περίπλοκες διατάξεις ενδέχεται να απαιτούν πρόσθετη μετα-επεξεργασία για να επιτευχθεί η επιθυμητή έξοδος HTML.

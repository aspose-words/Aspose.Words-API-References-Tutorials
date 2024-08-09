---
title: Δημιουργία προσαρμοσμένων ετικετών γραμμωτού κώδικα στο Aspose.Words για Java
linktitle: Δημιουργία προσαρμοσμένων ετικετών γραμμωτού κώδικα
second_title: Aspose.Words Java Document Processing API
description: Δημιουργήστε προσαρμοσμένες ετικέτες γραμμωτού κώδικα στο Aspose.Words για Java. Μάθετε πώς να δημιουργείτε εξατομικευμένες λύσεις γραμμικού κώδικα χρησιμοποιώντας το Aspose.Words για Java σε αυτόν τον οδηγό βήμα προς βήμα.
type: docs
weight: 10
url: /el/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Εισαγωγή στη δημιουργία προσαρμοσμένων ετικετών γραμμωτού κώδικα στο Aspose.Words για Java

Σε αυτόν τον περιεκτικό οδηγό, θα εμβαθύνουμε στη διαδικασία δημιουργίας προσαρμοσμένων ετικετών γραμμωτού κώδικα χρησιμοποιώντας το Aspose.Words για Java. Το Aspose.Words για Java είναι ένα ισχυρό API που επιτρέπει στους προγραμματιστές να χειρίζονται έγγραφα του Word μέσω προγραμματισμού. Ένα από τα αξιοσημείωτα χαρακτηριστικά του είναι η δυνατότητα εργασίας με ετικέτες barcode, καθιστώντας το ένα πολύτιμο εργαλείο για επιχειρήσεις και οργανισμούς που απαιτούν προσαρμοσμένες λύσεις barcode.

## Προαπαιτούμενα

Πριν βουτήξουμε στις λεπτομέρειες της δημιουργίας προσαρμοσμένων ετικετών γραμμωτού κώδικα, ας βεβαιωθούμε ότι έχουμε τις προϋποθέσεις:

1. Java Development Environment: Βεβαιωθείτε ότι έχετε εγκαταστήσει στο σύστημά σας Java και ένα Integrated Development Environment (IDE).

2.  Aspose.Words για Java: Κατεβάστε και εγκαταστήστε το Aspose.Words για Java από[εδώ](https://releases.aspose.com/words/java/).

3. Βασικές γνώσεις Java: Η εξοικείωση με τον προγραμματισμό Java θα είναι χρήσιμη καθώς θα γράφουμε κώδικα Java για τη δημιουργία προσαρμοσμένων ετικετών γραμμωτού κώδικα.

## Δημιουργία προσαρμοσμένων ετικετών γραμμωτού κώδικα

Τώρα, ας ξεκινήσουμε τη δημιουργία προσαρμοσμένων ετικετών γραμμωτού κώδικα χρησιμοποιώντας το Aspose.Words για Java. Θα αναλύσουμε τη διαδικασία σε βήματα και θα παρέχουμε αποσπάσματα κώδικα Java για κάθε βήμα.

## Ρύθμιση του ύψους του γραμμικού κώδικα

Για να ξεκινήσουμε, πρέπει να ρυθμίσουμε το ύψος του γραμμωτού κώδικα μας σε αναδιπλώσεις (1/1440 ίντσες). Στη συνέχεια, θα μετατρέψουμε αυτήν την τιμή σε χιλιοστά (mm). Εδώ είναι ο κώδικας για να το πετύχετε αυτό:

```java
	// Η τιμή εισόδου είναι σε 1/1440 ίντσες (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Μετατροπή σε mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Μετατροπή χρώματος εικόνας γραμμικού κώδικα

Στη συνέχεια, θα μετατρέψουμε το χρώμα της εικόνας του γραμμικού κώδικα από Word σε Aspose.BarCode. Το χρώμα εισαγωγής πρέπει να έχει τη μορφή "0xRRGGBB" (δεκαεξαδικό). Εδώ είναι ο κώδικας για τη μετατροπή:

```java
/// <περίληψη>
/// Μετατρέπει το χρώμα εικόνας γραμμικού κώδικα από Word σε Aspose.BarCode.
/// </summary>
/// <param name="inputColor"></param>
/// <returns></returns>
private static Color convertColor(String inputColor) throws Exception {
	// Η είσοδος πρέπει να είναι από "0x000000" έως "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Μετατροπή συντελεστή κλιμάκωσης γραμμωτού κώδικα

Τώρα, θα μετατρέψουμε τον συντελεστή κλιμάκωσης του γραμμικού κώδικα από ποσοστό σε κινητή τιμή. Αυτός ο παράγοντας κλιμάκωσης καθορίζει το μέγεθος του γραμμικού κώδικα. Εδώ είναι ο κώδικας για τη μετατροπή:

```java
/// <περίληψη>
/// Μετατρέπει τον παράγοντα κλιμάκωσης γραμμικού κώδικα από τοις εκατό σε float.
/// </summary>
/// <param name="scalingFactor"></param>
/// <returns></returns>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## Εφαρμογή της μεθόδου GetBarCodeImage().

 Σε αυτό το βήμα, θα εφαρμόσουμε το`getBarcodeImage` μέθοδο, η οποία δημιουργεί την εικόνα γραμμικού κώδικα με βάση τις παρεχόμενες παραμέτρους. Θα χειριστούμε διαφορετικούς τύπους γραμμωτού κώδικα, θα ορίσουμε χρώματα, θα προσαρμόσουμε τις διαστάσεις και πολλά άλλα. Εδώ είναι ο κώδικας για αυτήν τη μέθοδο:

```java
/// <περίληψη>
/// Υλοποίηση της μεθόδου GetBarCodeImage() για τη διεπαφή IBarCodeGenerator.
/// </summary>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Ελέγξτε εάν παρέχονται ο τύπος και η τιμή γραμμικού κώδικα
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Δημιουργήστε ένα BarcodeGenerator με βάση τον τύπο του barcode
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Χειριστείτε άλλους τύπους γραμμωτού κώδικα εδώ
	}
	
	// Ορίστε το κείμενο του γραμμικού κώδικα
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Ορίστε χρώματα γραμμωτού κώδικα
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Ορίστε το ύψος και τις διαστάσεις συμβόλων
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//Προσαρμόστε την τοποθεσία κειμένου κώδικα
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Πρόσθετες προσαρμογές για κωδικούς QR
	final float SCALE = 2.4f; // Εμπειρικός παράγοντας κλιμάκωσης για τη μετατροπή του γραμμικού κώδικα του Word σε Aspose.BarCode
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// Εφαρμόστε συντελεστή κλιμάκωσης
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Δημιουργήστε και επιστρέψτε την εικόνα γραμμικού κώδικα
	return generator.generateBarCodeImage();
}
```

## Εφαρμογή της μεθόδου GetOldBarcodeImage().

 Σε αυτό το βήμα, θα εφαρμόσουμε το`getOldBarcodeImage` μέθοδο, η οποία δημιουργεί εικόνες γραμμωτού κώδικα για παλιομοδίτους γραμμωτούς κώδικες. Εδώ, θα χειριστούμε έναν συγκεκριμένο τύπο γραμμικού κώδικα, όπως το POSTNET. Εδώ είναι ο κώδικας για αυτήν τη μέθοδο:

```java
/// <περίληψη>
/// Υλοποίηση της μεθόδου GetOldBarcodeImage() για τη διεπαφή IBarCodeGenerator.
/// </summary>
/// <param name="parameters"></param>
/// <returns></returns>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Τύπος σκληρού κώδικα για παλιομοδίτικο γραμμωτό κώδικα
	return generator.generateBarCodeImage();
}
```

## Σύναψη

Σε αυτό το άρθρο, εξερευνήσαμε τη διαδικασία δημιουργίας προσαρμοσμένων ετικετών γραμμωτού κώδικα χρησιμοποιώντας το Aspose.Words για Java. Καλύψαμε βασικά βήματα, από τη ρύθμιση του ύψους του γραμμικού κώδικα έως την εφαρμογή μεθόδων για τη δημιουργία γραμμωτού κώδικα. Το Aspose.Words for Java εξουσιοδοτεί τους προγραμματιστές να δημιουργούν δυναμικές και προσαρμοσμένες ετικέτες γραμμωτού κώδικα, καθιστώντας το πολύτιμο εργαλείο για διάφορους κλάδους.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω το μέγεθος του γραμμικού κώδικα που δημιουργείται;

Μπορείτε να προσαρμόσετε το μέγεθος του γραμμικού κώδικα που δημιουργείται, ρυθμίζοντας το ύψος συμβόλων και τον παράγοντα κλιμάκωσης του γραμμικού κώδικα στα παρεχόμενα αποσπάσματα κώδικα. Αυτές οι παράμετροι σάς επιτρέπουν να ελέγχετε τις διαστάσεις του γραμμωτού κώδικα σύμφωνα με τις απαιτήσεις σας.

### Μπορώ να αλλάξω τα χρώματα του barcode;

Ναι, μπορείτε να αλλάξετε τα χρώματα του γραμμικού κώδικα καθορίζοντας τα χρώματα του προσκηνίου και του φόντου στον κώδικα. Αυτή η προσαρμογή σάς επιτρέπει να ταιριάξετε την εμφάνιση του γραμμικού κώδικα με τη σχεδίαση του εγγράφου σας.

### Ποιοι τύποι γραμμωτού κώδικα υποστηρίζονται από το Aspose.Words για Java;

Το Aspose.Words για Java υποστηρίζει διάφορους τύπους γραμμωτού κώδικα, συμπεριλαμβανομένων κωδικών QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 και άλλων. Μπορείτε να επιλέξετε τον τύπο γραμμικού κώδικα που ταιριάζει στις ανάγκες της εφαρμογής σας.

### Πώς μπορώ να ενσωματώσω τον γραμμικό κώδικα που δημιουργήθηκε στο έγγραφο του Word;

Για να ενσωματώσετε τον γραμμωτό κώδικα που δημιουργήθηκε στο έγγραφο του Word, μπορείτε να χρησιμοποιήσετε τις δυνατότητες χειρισμού εγγράφων του Aspose.Words για Java. Μπορείτε να εισαγάγετε την εικόνα του γραμμικού κώδικα στο έγγραφό σας στην επιθυμητή θέση.

### Υπάρχει διαθέσιμο δείγμα κώδικα για περαιτέρω προσαρμογή;

 Ναι, μπορείτε να βρείτε δείγματα αποσπασμάτων κώδικα και πρόσθετη τεκμηρίωση στον ιστότοπο αναφοράς Aspose.Words for Java:[Aspose.Words for Java API Reference](https://reference.aspose.com/words/java/).
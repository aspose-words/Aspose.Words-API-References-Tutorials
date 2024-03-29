---
title: Υπογραφή υπάρχουσας γραμμής υπογραφής σε έγγραφο Word
linktitle: Υπογραφή υπάρχουσας γραμμής υπογραφής σε έγγραφο Word
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς να υπογράφετε μια υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στα βήματα για να χρησιμοποιήσετε τη δυνατότητα υπογραφής μιας υπάρχουσας γραμμής υπογραφής με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να υπογράψετε ψηφιακά μια γραμμή υπογραφής που υπάρχει ήδη σε ένα έγγραφο του Word. Ακολουθήστε τα παρακάτω βήματα:

## Βήμα 1: Φόρτωση του εγγράφου και πρόσβαση στη γραμμή υπογραφής

Ξεκινήστε ανεβάζοντας το έγγραφο που περιέχει την υπάρχουσα γραμμή υπογραφής:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Βήμα 2: Ρύθμιση επιλογών υπογραφής

Δημιουργήστε μια παρουσία της κλάσης SignOptions και ορίστε τις επιλογές υπογραφής, συμπεριλαμβανομένου του αναγνωριστικού γραμμής υπογραφής και της εικόνας γραμμής υπογραφής:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς την εικόνα γραμμής υπογραφής.

## Βήμα 3: Φόρτωση του πιστοποιητικού

Ξεκινήστε φορτώνοντας το πιστοποιητικό υπογραφής χρησιμοποιώντας την κλάση CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή προς το πιστοποιητικό σας και τον σχετικό κωδικό πρόσβασης.

## Βήμα 4: Υπογραφή της υπάρχουσας γραμμής υπογραφής

Χρησιμοποιήστε την κλάση DigitalSignatureUtil για να υπογράψετε την υπάρχουσα γραμμή υπογραφής:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Βεβαιωθείτε ότι έχετε καθορίσει τις σωστές διαδρομές για το έγγραφο προέλευσης, το υπογεγραμμένο έγγραφο και το πιστοποιητικό.

### Παράδειγμα πηγαίου κώδικα για την υπογραφή υπάρχουσας γραμμής υπογραφής χρησιμοποιώντας το Aspose.Words για .NET

Εδώ είναι ο πλήρης πηγαίος κώδικας για την υπογραφή μιας υπάρχουσας γραμμής υπογραφής με το Aspose.Words για .NET:


```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να υπογράψετε μια υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word με το Aspose.Words για .NET.

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να υπογράψουμε μια υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τα βήματα που παρέχονται, μπορείτε εύκολα να φορτώσετε το έγγραφο, να αποκτήσετε πρόσβαση στην υπάρχουσα γραμμή υπογραφής, να ορίσετε τις επιλογές υπογραφής και να υπογράψετε το έγγραφο. Η δυνατότητα υπογραφής μιας υπάρχουσας γραμμής υπογραφής παρέχει έναν βολικό τρόπο προσθήκης ψηφιακών υπογραφών σε προκαθορισμένες περιοχές στα έγγραφα του Word, διασφαλίζοντας την ακεραιότητα και τον έλεγχο ταυτότητας του εγγράφου. Το Aspose.Words για .NET προσφέρει ένα ισχυρό API για επεξεργασία λέξεων με ψηφιακές υπογραφές, επιτρέποντάς σας να προσαρμόσετε τη διαδικασία υπογραφής και να βελτιώσετε την ασφάλεια των εγγράφων του Word.

### Συχνές ερωτήσεις

#### Ε: Τι είναι μια υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word;

Α: Μια υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word είναι μια προκαθορισμένη περιοχή όπου μπορεί να τοποθετηθεί μια υπογραφή. Συνήθως αντιπροσωπεύεται από ένα σχήμα ή αντικείμενο στο έγγραφο και χρησιμεύει ως καθορισμένος χώρος για τον υπογράφοντα για να προσθέσει την ψηφιακή του υπογραφή.

#### Ε: Πώς μπορώ να υπογράψω μια υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

Α: Για να υπογράψετε μια υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να ακολουθήσετε τα εξής βήματα:
1.  Φορτώστε το έγγραφο χρησιμοποιώντας το`Document` κλάση και καθορίστε τη διαδρομή προς το αρχείο εγγράφου.
2.  Πρόσβαση στην υπάρχουσα γραμμή υπογραφής χρησιμοποιώντας την κατάλληλη μέθοδο ή ιδιότητα. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε`GetChild` μέθοδος ανάκτησης του σχήματος γραμμής υπογραφής.
3.  Δημιουργήστε ένα παράδειγμα του`SignOptions` τάξη και ορίστε το`SignatureLineId` ιδιοκτησία στο αναγνωριστικό της υπάρχουσας γραμμής υπογραφής.
4.  Ρυθμίστε το`SignatureLineImage` ιδιοκτησία του`SignOptions` κλάση στην εικόνα που αντιπροσωπεύει την ψηφιακή υπογραφή.
5.  Φορτώστε το πιστοποιητικό υπογραφής χρησιμοποιώντας το`CertificateHolder` τάξη και παρέχετε το απαραίτητο πιστοποιητικό και κωδικό πρόσβασης.
6.  Χρησιμοποιήστε το`DigitalSignatureUtil.Sign` μέθοδος υπογραφής του εγγράφου, παρέχοντας τις απαραίτητες παραμέτρους, συμπεριλαμβανομένων των`SignOptions` αντικείμενο.

#### Ε: Πώς μπορώ να αποκτήσω πρόσβαση στην υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET;

 Α: Για να αποκτήσετε πρόσβαση στην υπάρχουσα γραμμή υπογραφής σε ένα έγγραφο του Word χρησιμοποιώντας το Aspose.Words για .NET, μπορείτε να χρησιμοποιήσετε την κατάλληλη μέθοδο ή ιδιότητα για να ανακτήσετε το σχήμα γραμμής υπογραφής από τη δομή του εγγράφου. Για παράδειγμα, μπορείτε να χρησιμοποιήσετε το`GetChild` μέθοδος με τις κατάλληλες παραμέτρους για να λάβετε το επιθυμητό σχήμα γραμμής υπογραφής.

#### Ε: Μπορώ να προσαρμόσω την εμφάνιση της ψηφιακής υπογραφής σε μια υπάρχουσα γραμμή υπογραφής;

Α: Ναι, μπορείτε να προσαρμόσετε την εμφάνιση της ψηφιακής υπογραφής σε μια υπάρχουσα γραμμή υπογραφής παρέχοντας ένα αρχείο εικόνας που αντιπροσωπεύει την υπογραφή. Η εικόνα μπορεί να είναι ένα λογότυπο, χειρόγραφη υπογραφή ή οποιαδήποτε άλλη γραφική αναπαράσταση της υπογραφής. Μπορείτε να ορίσετε το`SignatureLineImage` ιδιοκτησία του`SignOptions` κλάση στα byte του αρχείου εικόνας.

#### Ε: Μπορώ να υπογράψω πολλές υπάρχουσες γραμμές υπογραφής σε ένα έγγραφο του Word;
 Α: Ναι, μπορείτε να υπογράψετε πολλές υπάρχουσες γραμμές υπογραφής σε ένα έγγραφο του Word. Πρέπει να ακολουθήσετε τα βήματα για κάθε γραμμή υπογραφής ξεχωριστά, ορίζοντας το κατάλληλο`SignatureLineId` και`SignatureLineImage` αξίες στο`SignOptions` αντικείμενο για κάθε γραμμή υπογραφής.

#### Ε: Τι μορφή πρέπει να είναι το αρχείο εικόνας για την ψηφιακή υπογραφή σε μια υπάρχουσα γραμμή υπογραφής;

 Α: Το αρχείο εικόνας για την ψηφιακή υπογραφή σε μια υπάρχουσα γραμμή υπογραφής μπορεί να είναι σε διάφορες μορφές, όπως PNG, JPEG, BMP ή GIF. Μπορείτε να καθορίσετε τη διαδρομή του αρχείου ή να διαβάσετε τα byte του αρχείου εικόνας και να το αντιστοιχίσετε στο`SignatureLineImage` ιδιοκτησία του`SignOptions` τάξη.

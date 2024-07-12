---
title: Μετατροπή μεταξύ μονάδων μέτρησης
linktitle: Μετατροπή μεταξύ μονάδων μέτρησης
second_title: Aspose.Words Document Processing API
description: Οδηγός βήμα προς βήμα για τη μετατροπή μεταξύ μονάδων μέτρησης σε ένα έγγραφο με το Aspose.Words για .NET.
type: docs
weight: 10
url: /el/net/programming-with-document-properties/convert-between-measurement-units/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στον πηγαίο κώδικα C# για τη μετατροπή μεταξύ μονάδων μέτρησης με το Aspose.Words για .NET. Αυτή η δυνατότητα σάς επιτρέπει να καθορίσετε περιθώρια, αποστάσεις κεφαλίδας και υποσέλιδου κ.λπ. σε διαφορετικές μονάδες μέτρησης.

## Βήμα 1: Ρύθμιση έργου

Για να ξεκινήσετε, δημιουργήστε ένα νέο έργο C# στο αγαπημένο σας IDE. Βεβαιωθείτε ότι η βιβλιοθήκη Aspose.Words for .NET αναφέρεται στο έργο σας.

## Βήμα 2: Δημιουργία του εγγράφου και του κατασκευαστή

Σε αυτό το βήμα θα δημιουργήσουμε ένα νέο έγγραφο και θα αρχικοποιήσουμε τον κατασκευαστή. Χρησιμοποιήστε τον ακόλουθο κώδικα:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Βήμα 3: Διαμόρφωση μονάδων μέτρησης

Τώρα θα μετατρέψουμε τις τιμές για περιθώρια, αποστάσεις κεφαλίδας και υποσέλιδου κ.λπ. σε διαφορετικές μονάδες μέτρησης. Χρησιμοποιήστε τον ακόλουθο κώδικα για να καθορίσετε τιμές σε συγκεκριμένες μονάδες μέτρησης:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Αυτός ο κώδικας χρησιμοποιεί το`ConvertUtil` κλάση Aspose.Words για μετατροπή των καθορισμένων τιμών σε ίντσες (`InchToPoint`). Μπορείτε επίσης να χρησιμοποιήσετε άλλες μεθόδους μετατροπής που είναι διαθέσιμες στο`ConvertUtil` κλάση για μετατροπή τιμών σε άλλες μονάδες μέτρησης.

### Παράδειγμα πηγαίου κώδικα για Μετατροπή μεταξύ μονάδων μέτρησης χρησιμοποιώντας Aspose.Words για .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Τώρα έχετε μάθει πώς να κάνετε μετατροπή μεταξύ μονάδων μέτρησης όταν καθορίζετε περιθώρια, αποστάσεις κεφαλίδας και υποσέλιδου κ.λπ. σε ένα έγγραφο χρησιμοποιώντας το Aspose.Words για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα που παρέχεται σε αυτό το σεμινάριο, μπορείτε εύκολα να καθορίσετε τις τιμές στις επιθυμητές μονάδες μέτρησης στα δικά σας έγγραφα.
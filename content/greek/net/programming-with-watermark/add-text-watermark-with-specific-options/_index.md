---
title: Προσθήκη υδατογραφήματος κειμένου με συγκεκριμένες επιλογές
linktitle: Προσθήκη υδατογραφήματος κειμένου με συγκεκριμένες επιλογές
second_title: Aspose.Words Document Processing API
description: Μάθετε πώς μπορείτε να προσθέσετε ένα υδατογράφημα κειμένου με συγκεκριμένες επιλογές χρησιμοποιώντας το Aspose.Words για .NET. Οδηγός βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε πώς να προσθέσετε ένα υδατογράφημα κειμένου με συγκεκριμένες επιλογές χρησιμοποιώντας το Aspose.Words για .NET. Το υδατογράφημα κειμένου είναι κείμενο που τοποθετείται πάνω σε ένα έγγραφο για να υποδείξει ότι είναι προσχέδιο, εμπιστευτικό κ.λπ.

## Βήμα 1: Χρήση ενός προγράμματος δημιουργίας εγγράφων

Αρχικά, θα χρησιμοποιήσουμε ένα πρόγραμμα δημιουργίας εγγράφων για να προσθέσουμε περιεχόμενο στο έγγραφό μας.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Βήμα 2: Φόρτωση του εγγράφου

Θα φορτώσουμε ένα υπάρχον έγγραφο χρησιμοποιώντας τη διαδρομή εγγράφου.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Βήμα 3: Προσθέστε υδατογράφημα κειμένου με συγκεκριμένες επιλογές

 Θα δημιουργήσουμε ένα παράδειγμα του`TextWatermarkOptions` τάξη και ορίστε τις επιθυμητές επιλογές για το υδατογράφημα κειμένου.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Βήμα 4: Αποθηκεύστε το έγγραφο

Τέλος, μπορούμε να αποθηκεύσουμε το έγγραφο με το προστιθέμενο υδατογράφημα κειμένου.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Παράδειγμα πηγαίου κώδικα για την προσθήκη υδατογραφήματος κειμένου με συγκεκριμένες επιλογές με το Aspose.Words για .NET

```csharp

	// Η διαδρομή προς τον κατάλογο εγγράφων.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Συγχαρητήρια ! Τώρα έχετε μάθει πώς να προσθέτετε υδατογράφημα κειμένου με συγκεκριμένες επιλογές χρησιμοποιώντας το Aspose.Words για .NET.


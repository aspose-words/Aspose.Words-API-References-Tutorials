---
title: PDF-Bilder überspringen
linktitle: PDF-Bilder überspringen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein PDF-Dokument laden und dabei das Laden von PDF-Bildern überspringen.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/skip-pdf-images/
---

Bei der Textverarbeitung mit PDF-Dokumenten in einer C#-Anwendung kann es aus Gründen der Leistung oder der Speicherplatzverwaltung erforderlich sein, das Laden von PDF-Bildern zu überspringen. Mit der Aspose.Words-Bibliothek für .NET können Sie das Laden von PDF-Bildern mithilfe der Ladeoptionen von PdfLoadOptions problemlos überspringen. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung von Aspose.Words für .NET C#-Quellcode zum Laden eines PDF-Dokuments, indem wir das Laden von PDF-Bildern mithilfe der Ladeoptionen von PdfLoadOptions überspringen.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Ladeoptionen konfigurieren

Der erste Schritt besteht darin, die Ladeoptionen für unser PDF-Dokument zu konfigurieren. Verwenden Sie die PdfLoadOptions-Klasse, um Ladeparameter anzugeben. In unserem Fall müssen wir die SkipPdfImages-Eigenschaft auf true setzen, um das Laden von PDF-Bildern zu überspringen. So geht's:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };
```

Wir erstellen ein neues PdfLoadOptions-Objekt und setzen die SkipPdfImages-Eigenschaft auf „true“, um das Laden von PDF-Bildern zu überspringen.

## Laden Sie ein PDF-Dokument und überspringen Sie PDF-Bilder

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das PDF-Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

In diesem Beispiel laden wir das PDF-Dokument „Pdf Document.pdf“, das sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

### Beispielquellcode für PdfLoadOptions mit der Funktion „PDF-Bilder überspringen“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurieren Sie Ladeoptionen mit der Funktion „PDF-Bilder überspringen“.
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };

// Laden Sie das PDF-Dokument und überspringen Sie die PDF-Bilder
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie man ein PDF-Dokument lädt und dabei das Laden von PDF-Bildern mit der Aspose.Words-Bibliothek für .NET überspringt. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das Überspringen des Ladens von PDF-Bildern kann die Leistung und die Speicherplatzverwaltung bei der Verarbeitung von PDF-Dokumenten verbessern.
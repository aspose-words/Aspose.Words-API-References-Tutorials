---
title: Kleine Metadateien nicht komprimieren
linktitle: Kleine Metadateien nicht komprimieren
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Funktion „Kleine Metadateien nicht komprimieren“ beim Speichern von Dokumenten aktivieren.
type: docs
weight: 10
url: /de/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

Das Komprimieren von Metadaten in einem Dokument ist eine gängige Funktion bei der Textverarbeitung mit Dateien in einer C#-Anwendung. Es kann jedoch erforderlich sein, die Metadaten kleiner Dateien nicht zu komprimieren, um deren Qualität zu erhalten. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um die Funktion „Kleine Metadateien nicht komprimieren“ in den Dokumentspeicheroptionen zu aktivieren.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Schritt 1: Dokumentverzeichnis festlegen

Der erste Schritt besteht darin, das Verzeichnis anzugeben, in dem Sie das Dokument speichern möchten. Sie müssen den vollständigen Verzeichnispfad angeben. Beispiel:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Abschnitte und Text einfügen

Anschließend können Sie Abschnitte und Text in Ihr Dokument einfügen. Verwenden Sie die von Aspose.Words bereitgestellte DocumentBuilder-Klasse, um den Inhalt Ihres Dokuments zu erstellen. Hier ist ein einfaches Beispiel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In diesem Beispiel erstellen wir ein neues leeres Dokument und verwenden dann DocumentBuilder, um eine Textzeile hinzuzufügen.

## Schritt 3: Setup-Optionen

'Anmeldung

Konfigurieren wir nun die Speicheroptionen für unser Dokument. Verwenden Sie die Klasse DocSaveOptions, um die Speichereinstellungen festzulegen. Beispiel:

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

In diesem Beispiel erstellen wir ein neues DocSaveOptions-Objekt, um Speicheroptionen festzulegen.

## Schritt 4: Aktivieren Sie die Funktion „Kleine Metadateien nicht komprimieren“

 Um die Funktion "Kleine Metadateien nicht komprimieren" zu aktivieren, müssen Sie die`Compliance` Eigenschaft des DocSaveOptions-Objekts auf den Wert`PdfCompliance.PdfA1a`. Hier ist wie:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Diese Konfiguration stellt sicher, dass die Metadaten kleiner Dateien beim Speichern des Dokuments nicht komprimiert werden.

## Schritt 5: Speichern Sie das Dokument

Abschließend können Sie das Dokument speichern mit dem`Save` Methode der Klasse Document. Geben Sie den vollständigen Pfad zur Datei und den gewünschten Dateinamen an. Beispiel:

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Ersetzen Sie „dataDir“ unbedingt durch den Pfad zu Ihrem Dokumentverzeichnis.

### Beispielquellcode für DocSaveOptions mit der Funktion „Kleine Metadateien nicht komprimieren“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Fügen Sie zwei Abschnitte mit etwas Text ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Konfigurieren Sie die Speicheroptionen mit der Funktion „Kleine Metadateien nicht komprimieren“
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Speichern Sie das Dokument mit den angegebenen Optionen
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Abschluss

In diesem Handbuch haben wir erklärt, wie Sie die Aspose.Words-Bibliothek für .NET verwenden, um beim Speichern eines Dokuments die Funktion „Kleine Metadateien nicht komprimieren“ zu aktivieren. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktion problemlos in Ihrer C#-Anwendung anwenden. Das Beibehalten unkomprimierter Metadaten kleiner Dateien kann wichtig sein, um die Qualität und Integrität von Dokumenten aufrechtzuerhalten.
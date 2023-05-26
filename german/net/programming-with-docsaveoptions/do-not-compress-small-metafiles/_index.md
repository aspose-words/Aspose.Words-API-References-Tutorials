---
title: Komprimieren Sie keine kleinen Metadateien
linktitle: Komprimieren Sie keine kleinen Metadateien
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Funktion „Kleine Metadateien nicht komprimieren“ beim Speichern von Dokumenten aktivieren.
type: docs
weight: 10
url: /de/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

Das Komprimieren von Metadaten in einem Dokument ist eine häufige Funktion beim Arbeiten mit Dateien in einer C#-Anwendung. Es kann jedoch erforderlich sein, die Metadaten kleiner Dateien nicht zu komprimieren, um deren Qualität zu erhalten. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um die Funktion „Kleine Metadateien nicht komprimieren“ in den Dokumentspeicheroptionen zu aktivieren.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Schritt 1: Dokumentverzeichnis festlegen

Der erste Schritt besteht darin, das Verzeichnis zu definieren, in dem Sie das Dokument speichern möchten. Sie müssen den vollständigen Verzeichnispfad angeben. Zum Beispiel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 2: Abschnitte und Text einfügen

Anschließend können Sie Abschnitte und Texte in Ihr Dokument einfügen. Verwenden Sie die von Aspose.Words bereitgestellte DocumentBuilder-Klasse, um den Inhalt Ihres Dokuments zu erstellen. Hier ist ein einfaches Beispiel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

In diesem Beispiel erstellen wir ein neues leeres Dokument und fügen dann mit DocumentBuilder eine Textzeile hinzu.

## Schritt 3: Setup-Optionen

'Anmeldung

Jetzt konfigurieren wir die Speicheroptionen für unser Dokument. Verwenden Sie die DocSaveOptions-Klasse, um Speichereinstellungen anzugeben. Zum Beispiel :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

In diesem Beispiel erstellen wir ein neues DocSaveOptions-Objekt, um Speicheroptionen festzulegen.

## Schritt 4: Aktivieren Sie die Funktion „Kleine Metadateien nicht komprimieren“.

 Um die Funktion „Kleine Metadateien nicht komprimieren“ zu aktivieren, müssen Sie Folgendes festlegen`Compliance` Eigenschaft des DocSaveOptions-Objekts auf den Wert`PdfCompliance.PdfA1a`. Hier ist wie:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Diese Konfiguration stellt sicher, dass Metadaten kleiner Dateien beim Speichern des Dokuments nicht komprimiert werden.

## Schritt 5: Speichern Sie das Dokument

 Abschließend können Sie das Dokument mit speichern`Save` Methode der Document-Klasse. Geben Sie den vollständigen Pfad zur Datei und den gewünschten Dateinamen an. Zum Beispiel :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Ersetzen Sie „dataDir“ unbedingt durch den Pfad zu Ihrem Dokumentverzeichnis.

### Beispielquellcode für DocSaveOptions mit der Funktion „Kleine Metadateien nicht komprimieren“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Fügen Sie zwei Abschnitte mit etwas Text ein.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Konfigurieren Sie Speicheroptionen mit der Funktion „Kleine Metadateien nicht komprimieren“.
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Speichern Sie das Dokument mit den angegebenen Optionen
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie die Aspose.Words-Bibliothek für .NET verwenden, um beim Speichern eines Dokuments die Funktion „Kleine Metadateien nicht komprimieren“ zu aktivieren. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Die Beibehaltung unkomprimierter Metadaten kleiner Dateien kann für die Aufrechterhaltung der Dokumentqualität und -integrität wichtig sein.
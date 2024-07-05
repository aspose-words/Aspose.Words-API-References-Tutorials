---
title: Bildaufzählungszeichen nicht speichern
linktitle: Bildaufzählungszeichen nicht speichern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie das Speichern von Bildaufzählungszeichen in Word-Dokumenten mit Aspose.Words für .NET deaktivieren.
type: docs
weight: 10
url: /de/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Bildaufzählungszeichen sind eine häufig verwendete Funktion in Word-Dokumenten, um benutzerdefinierte Aufzählungszeichen hinzuzufügen. In einigen Fällen kann es jedoch erforderlich sein, die Registrierung von Bildaufzählungszeichen zu deaktivieren, wenn Dokumente mit der Aspose.Words-Bibliothek für .NET bearbeitet werden. In dieser Schritt-für-Schritt-Anleitung erklären wir, wie Sie den Aspose.Words C#-Quellcode für .NET verwenden, um das Speichern von Bildaufzählungszeichen mithilfe der Speicheroptionen von DocSaveOptions zu deaktivieren.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Schritt 1: Festlegen des Dokumentverzeichnisses

Der erste Schritt besteht darin, das Verzeichnis anzugeben, in dem sich Ihre Dokumente befinden. Sie müssen den vollständigen Verzeichnispfad angeben. Beispiel:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Laden des Dokuments mit Bildaufzählungszeichen

Als Nächstes müssen Sie das Dokument mit Bildaufzählungszeichen laden. Verwenden Sie die Document-Klasse, um das Dokument aus einer Datei zu laden. Beispiel:

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

In diesem Beispiel laden wir das Dokument aus der Datei „Image bullet points.docx“

  befindet sich im Dokumentenverzeichnis.

## Schritt 3: Aufzeichnungsoptionen konfigurieren

Konfigurieren wir nun die Speicheroptionen für unser Dokument. Verwenden Sie die Klasse DocSaveOptions, um die Speichereinstellungen festzulegen. Beispiel:

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

In diesem Beispiel erstellen wir ein neues DocSaveOptions-Objekt und setzen die SavePictureBullet-Eigenschaft auf „false“, um das Speichern von Bildaufzählungszeichen zu deaktivieren.

## Schritt 4: Aktivieren Sie die Funktion „Bildaufzählungszeichen nicht speichern“

Um die Funktion „Bildaufzählungszeichen nicht speichern“ zu aktivieren, haben wir die Speicheroptionen bereits so konfiguriert, dass SavePictureBullet auf „false“ gesetzt ist. Dadurch wird sichergestellt, dass Bildaufzählungszeichen nicht im endgültigen Dokument gespeichert werden.

## Schritt 5: Speichern Sie das Dokument

Abschließend können Sie das Dokument mit der Save-Methode der Document-Klasse speichern. Geben Sie den vollständigen Pfad zur Datei und den gewünschten Dateinamen an. Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Ersetzen Sie „dataDir“ unbedingt durch den Verzeichnispfad zu Ihren Dokumenten.

## Beispielquellcode für DocSaveOptions-Speicheroptionen mit der Funktion „Bildaufzählungszeichen nicht speichern“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument mit Bildaufzählungszeichen
Document doc = new Document(dataDir + "Image bullet points.docx");

// Konfigurieren Sie Speicheroptionen mit der Funktion „Bildaufzählungszeichen nicht speichern“
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Speichern Sie das Dokument mit den angegebenen Optionen
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erläutert, wie Sie das Speichern von Bildaufzählungszeichen in einem Dokument mithilfe der Aspose.Words-Bibliothek für .NET deaktivieren. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktion problemlos in Ihrer C#-Anwendung anwenden. Das Deaktivieren des Speicherns von Bildaufzählungszeichen kann in einigen Situationen nützlich sein, um die Dokumentstruktur und -formatierung beizubehalten, ohne Bildaufzählungszeichen zu speichern.
---
title: Lesezeichendaten im Word-Dokument aktualisieren
linktitle: Lesezeichendaten aktualisieren
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Aspose.Words-Lesezeichendatenaktualisierung in der Word-Dokumentfunktion für .NET.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/update-bookmark-data/
---

In diesem Tutorial gehen wir eine Schritt-für-Schritt-Anleitung durch, um die Funktion „Lesezeichendaten in Word-Dokument aktualisieren“ von Aspose.Words für .NET zu verstehen und zu implementieren. Mit dieser Funktion können Sie den Inhalt und die Eigenschaften von Lesezeichen in einem Word-Dokument mithilfe von C#-Quellcode aktualisieren.

## Anforderungen

Bevor Sie mit dem Tutorial fortfahren, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Aspose.Words für .NET-Bibliothek installiert
- Grundkenntnisse der Programmiersprache C#
- Visual Studio oder eine andere kompatible IDE

## Schritt 1: Laden Sie das Dokument

In diesem Schritt laden wir das Word-Dokument, das die Lesezeichen enthält, die wir aktualisieren möchten. Angenommen, Sie haben das Dokument in einem bestimmten Verzeichnis gespeichert, verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Verzeichnispfad, in dem sich Ihr Dokument befindet.

## Schritt 2: Greifen Sie auf das Lesezeichen zu

Um die Lesezeichendaten zu aktualisieren, müssen wir zunächst auf das spezifische Lesezeichen im Dokument zugreifen. Jedem Lesezeichen ist ein eindeutiger Name zugeordnet. Verwenden Sie den folgenden Code, um auf ein Lesezeichen mit dem Namen „MyBookmark1“ zuzugreifen:

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

Stellen Sie sicher, dass der Name des Lesezeichens mit dem Namen in Ihrem Dokument übereinstimmt. Sie können es entsprechend Ihren Anforderungen ändern.

## Schritt 3: Lesezeicheneigenschaften und -inhalte aktualisieren

Sobald Sie auf das Lesezeichen zugegriffen haben, können Sie dessen Eigenschaften und Inhalt aktualisieren. Im folgenden Codeausschnitt aktualisieren wir den Namen und Text des Lesezeichens:

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

Sie können den Lesezeichennamen und den neuen Text nach Ihren Wünschen anpassen. Der obige Code benennt das Lesezeichen in „RenamedBookmark“ um und aktualisiert den Textinhalt.

## Schritt 4: Speichern Sie das aktualisierte Dokument

Nachdem Sie die Lesezeichendaten aktualisiert haben, müssen Sie das geänderte Dokument speichern. Verwenden Sie den folgenden Code, um das Dokument zu speichern:

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

Dieser Code speichert das geänderte Dokument unter dem Namen „UpdatedDocument.docx“ im selben Verzeichnis wie das Originaldokument.

### Beispielquellcode für die Aktualisierung von Lesezeichendaten mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Verzeichnispfad, in dem sich Ihr Dokument befindet.

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie Lesezeichendaten mit Aspose.Words für .NET aktualisieren. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, sollten Sie nun in der Lage sein, diese Funktion in Ihre C#-Anwendungen zu integrieren und Lesezeichen in Word-Dokumenten programmgesteuert zu bearbeiten.

### FAQs zum Aktualisieren von Lesezeichendaten in Word-Dokumenten

#### F: Funktioniert die Funktion zum Aktualisieren von Lesezeichendaten nur mit Lesezeichen in Word-Dokumenten?

A: Ja, die Funktion „Lesezeichendaten aktualisieren“ wurde speziell für Lesezeichen in Word-Dokumenten entwickelt. Damit können Sie den Inhalt und die Eigenschaften von Lesezeichen in einem Word-Dokument aktualisieren.

#### F: Kann ich außer Text auch andere Lesezeicheneigenschaften aktualisieren?

 A: Ja, zusätzlich zum Text können Sie auch andere Lesezeicheneigenschaften aktualisieren, z. B. den Lesezeichennamen, den Lesezeichenbereich usw. Verwenden Sie die entsprechenden Eigenschaften des`Bookmark` Objekt, um die gewünschten Eigenschaften zu aktualisieren.

#### F: Kann ich mehrere Lesezeichen im selben Dokument aktualisieren?

A: Ja, Sie können mehrere Lesezeichen im selben Dokument aktualisieren, indem Sie die Zugriffs- und Aktualisierungsschritte für jedes Lesezeichen wiederholen. Stellen Sie sicher, dass Sie für jedes Lesezeichen, das Sie aktualisieren möchten, eindeutige Lesezeichennamen verwenden.

#### F: Verändert die Funktion „Lesezeichendaten aktualisieren“ das Originaldokument?

A: Ja, die Funktion zur Aktualisierung der Lesezeichendaten ändert das Originaldokument, indem sie die Eigenschaften und den Inhalt der Lesezeichen aktualisiert. Speichern Sie unbedingt eine Kopie des Originaldokuments, bevor Sie diese Funktion anwenden.
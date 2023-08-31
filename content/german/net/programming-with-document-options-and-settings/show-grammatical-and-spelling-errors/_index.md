---
title: Zeigen Sie Grammatik- und Rechtschreibfehler an
linktitle: Zeigen Sie Grammatik- und Rechtschreibfehler an
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zum Aktivieren der Anzeige von Grammatik- und Rechtschreibfehlern in einem Dokument mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

In diesem Tutorial führen wir Sie durch den C#-Quellcode, um die Anzeige von Grammatik- und Rechtschreibfehlern mit Aspose.Words für .NET zu ermöglichen. Mit dieser Funktion können Sie Grammatik- und Rechtschreibfehler in einem Dokument anzeigen.

## Schritt 1: Projekteinrichtung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten IDE. Stellen Sie sicher, dass in Ihrem Projekt auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

In diesem Schritt laden wir das Word-Dokument, für das wir Grammatik- und Rechtschreibfehler anzeigen möchten. Verwenden Sie den folgenden Code, um das Dokument zu laden:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Ersetzen`"YOUR DOCUMENTS DIRECTORY"` mit dem tatsächlichen Pfad des Verzeichnisses, in dem sich Ihr Dokument befindet.

## Schritt 3: Fehleranzeige aktivieren

Jetzt aktivieren wir die Anzeige von Grammatik- und Rechtschreibfehlern im Dokument. Verwenden Sie den folgenden Code, um die Fehleranzeige zu aktivieren:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Dieser Code ermöglicht die Anzeige von Grammatikfehlern (`ShowGrammaticalErrors`) und Rechtschreibfehler (`ShowSpellingErrors`) im Dokument.

### Beispielquellcode zum Anzeigen von Grammatik- und Rechtschreibfehlern mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Stellen Sie sicher, dass Sie den richtigen Dokumentpfad angeben`dataDir` Variable.

Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET die Anzeige von Grammatik- und Rechtschreibfehlern in einem Dokument aktivieren. Wenn Sie der Schritt-für-Schritt-Anleitung in diesem Tutorial folgen, können Sie diese Funktion ganz einfach in Ihren eigenen Dokumenten aktivieren.
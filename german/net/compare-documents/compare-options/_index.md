---
title: Vergleichen Sie Optionen
linktitle: Vergleichen Sie Optionen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Funktion „Vergleichsoptionen“ mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/compare-documents/compare-options/
---

In diesem Tutorial erklären wir, wie Sie die Funktion „Optionen vergleichen“ mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

## Schritt 1: Dokumente mit benutzerdefinierten Optionen vergleichen

 Laden Sie zunächst zwei Dokumente zum Vergleichen. In diesem Beispiel verwenden wir die`Clone()` Methode zum Erstellen einer Kopie des Originaldokuments. Hier ist wie:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Schritt 2: Vergleichsoptionen konfigurieren

 Wir werden nun die Vergleichsoptionen konfigurieren, indem wir eine erstellen`CompareOptions` Objekt und legen Sie die verschiedenen Eigenschaften nach Bedarf fest. Hier ist wie:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Schritt 3: Dokumente mit benutzerdefinierten Optionen vergleichen

 Wir werden jetzt das verwenden`Compare()` Methode, die die benutzerdefinierten Optionen übergibt, um die beiden Dokumente zu vergleichen. Diese Methode markiert die Änderungen im Originaldokument. Hier ist wie:

```csharp
// Vergleichen Sie Dokumente mit benutzerdefinierten Optionen
docA.Compare(docB, "user", DateTime.Now, options);

// Prüfen Sie, ob die Dokumente gleich sind
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Beispielquellcode für Vergleichsoptionen mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Optionen vergleichen“ mit Aspose.Words für .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Mit diesem Code können Sie zwei Dokumente mit benutzerdefinierten Optionen vergleichen, um bestimmte Elemente beim Vergleich mit Aspose.Words für .NET zu ignorieren.


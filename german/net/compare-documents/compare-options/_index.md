---
title: Vergleichen Sie Optionen im Word-Dokument
linktitle: Vergleichen Sie Optionen im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Erläuterung des C#-Quellcodes der Funktion „Vergleichsoptionen in Word-Dokumenten“ mit Aspose.Words für .NET.
type: docs
weight: 10
url: /de/net/compare-documents/compare-options/
---
In diesem Tutorial erklären wir, wie Sie die Funktion „Vergleichsoptionen in Word-Dokumenten“ mit Aspose.Words für .NET verwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und die Änderungen anzuwenden.

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

## Abschluss

In diesem Tutorial haben wir gelernt, wie man die Vergleichsoptionen in Aspose.Words für .NET verwendet, um den Vergleichsprozess beim Vergleich zweier Dokumente anzupassen. Durch die Angabe verschiedener Optionen können Sie bestimmte Elemente ignorieren und den Vergleichsprozess flexibler gestalten. Mit dieser Funktion haben Sie eine bessere Kontrolle über den Vergleichsprozess und können ihn an Ihre spezifischen Anforderungen anpassen. Aspose.Words für .NET bietet leistungsstarke Dokumentvergleichsfunktionen, die es einfach machen, Unterschiede zwischen Dokumenten zu erkennen und bei Bedarf bestimmte Elemente zu ignorieren.

### FAQs

#### F: Was ist der Zweck der Verwendung von Vergleichsoptionen in Aspose.Words für .NET?

A: Mit den Vergleichsoptionen in Aspose.Words für .NET können Sie den Vergleichsprozess beim Vergleich zweier Dokumente anpassen. Mit diesen Optionen können Sie angeben, welche Elemente beim Vergleich ignoriert werden sollen, z. B. Formatierungsänderungen, Kopf- und Fußzeilen, Tabellen, Felder, Kommentare, Textfelder und Fußnoten.

#### F: Wie verwende ich Vergleichsoptionen in Aspose.Words für .NET?

A: Um die Vergleichsoptionen in Aspose.Words für .NET zu verwenden, führen Sie die folgenden Schritte aus:
1. Laden Sie die beiden Dokumente, die Sie vergleichen möchten, in separate Dokumentobjekte.
2.  Benutzen Sie die`Clone()` Methode zum Erstellen einer Kopie des Originaldokuments.
3.  Ein ... kreieren`CompareOptions` Objekt und legen Sie seine Eigenschaften fest, um den Vergleichsprozess anzupassen. Sie können angeben, welche Elemente beim Vergleich ignoriert werden sollen.
4.  Benutzen Sie die`Compare()` Methode für eines der Dokumente und übergeben Sie das andere Dokument und das`CompareOptions` Objekt als Parameter. Diese Methode vergleicht die Dokumente anhand der angegebenen Optionen und markiert die Änderungen im Originaldokument.
5.  Überprüf den`Revisions` Eigentum des Originaldokuments. Wenn die Anzahl Null beträgt, bedeutet dies, dass die Dokumente unter Berücksichtigung der angegebenen Optionen identisch sind.

#### F: Welche allgemeinen Optionen sind in CompareOptions verfügbar?

A: Zu den allgemeinen Optionen, die in CompareOptions verfügbar sind, gehören:
- `IgnoreFormatting`: Ignoriert Änderungen in der Formatierung.
- `IgnoreHeadersAndFooters`: Ignoriert Änderungen in Kopf- und Fußzeilen.
- `IgnoreCaseChanges`: Ignoriert Groß-/Kleinschreibung (Groß-/Kleinschreibung).
- `IgnoreTables`: Ignoriert Änderungen in Tabellen.
- `IgnoreFields`: Ignoriert Änderungen in Feldern.
- `IgnoreComments`: Ignoriert Änderungen in Kommentaren.
- `IgnoreTextboxes`Ignoriert Änderungen in Textfeldern.
- `IgnoreFootnotes`: Ignoriert Änderungen in Fußnoten.

#### F: Kann ich beim Dokumentvergleich benutzerdefinierte Optionen für bestimmte Elemente verwenden?

 A: Ja, Sie können beim Dokumentvergleich benutzerdefinierte Optionen für bestimmte Elemente verwenden. Durch Festlegen der Eigenschaften des`CompareOptions` Wenn Sie das Objekt entsprechend anpassen, können Sie auswählen, welche Elemente ignoriert und welche beim Vergleich berücksichtigt werden sollen.
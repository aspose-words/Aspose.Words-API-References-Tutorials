---
title: Erkennen und Ersetzen innerhalb von Ersetzungsmustern
linktitle: Erkennen und Ersetzen innerhalb von Ersetzungsmustern
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Ersetzungsmuster mit Erkennungen und Ersetzungen in Aspose.Words für .NET verwenden, um Word-Dokumente zu bearbeiten.
type: docs
weight: 10
url: /de/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Diese Funktion hilft, komplexe Suchmuster zu erkennen und Ersetzungen basierend auf Gruppen durchzuführen, die während der Dokumentbearbeitung erfasst wurden.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit der Verwendung von Übereinstimmungen und Ersetzungen in Ersetzungsmustern beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir mit a Text einfügen`DocumentBuilder`Objekt. In unserem Beispiel verwenden wir die`Write` Methode, um den Satz „Jason gibt Paul etwas Geld“ einzufügen. :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Schritt 3: Erkennungen und Ersetzungen in Ersetzungsmustern

 Jetzt werden wir das verwenden`Range.Replace` Funktion zum Durchführen einer Textsuche und -ersetzung mithilfe eines regulären Ausdrucks, um bestimmte Muster zu erkennen. In unserem Beispiel verwenden wir den regulären Ausdruck`([A-z]+) gives money to ([A-z]+)` Sätze erkennen, in denen jemand jemand anderem Geld gibt. Wir verwenden das Ersatzmuster`$2 takes money from $1` die Ersetzung durch Rollentausch durchzuführen. Die Verwendung von`$1` Und`$2` bezieht sich auf die vom regulären Ausdruck erfassten Gruppen:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Beispielquellcode für „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung von Übereinstimmungen und Ersetzungen in Ersetzungsmustern mit Aspose.Words für .NET zu veranschaulichen:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ von Aspose.Words für .NET verwendet wird. Wir folgten einer Schritt-für-Schritt-Anleitung, um ein Dokument zu erstellen, Text einzufügen, Suchen und Ersetzen mit regulären Ausdrücken und Ersetzungsmustern basierend auf erfassten Gruppen durchzuführen und das Dokument zu bearbeiten.

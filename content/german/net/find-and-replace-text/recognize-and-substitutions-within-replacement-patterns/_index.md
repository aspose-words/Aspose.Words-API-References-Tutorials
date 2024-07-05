---
title: Erkennen und Ersetzen innerhalb von Ersatzmustern
linktitle: Erkennen und Ersetzen innerhalb von Ersatzmustern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Ersetzungsmuster mit Erkennungen und Ersetzungen in Aspose.Words für .NET verwenden, um Word-Dokumente zu bearbeiten.
type: docs
weight: 10
url: /de/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

In diesem Artikel untersuchen wir den obigen C#-Quellcode, um zu verstehen, wie die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Diese Funktion hilft dabei, komplexe Suchmuster zu erkennen und Ersetzungen basierend auf Gruppen durchzuführen, die während der Dokumentbearbeitung erfasst wurden.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Neues Dokument erstellen

Bevor wir Übereinstimmungen und Ersetzungen in Ersetzungsmustern verwenden, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch Instanziieren eines`Document` Objekt:

```csharp
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Write` Methode zum Einfügen der Phrase „Jason gibt Paul etwas Geld.“:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Schritt 3: Erkennungen und Ersetzungen in Ersatzmustern

 Nun verwenden wir die`Range.Replace` Funktion zum Durchführen einer Textsuche und -ersetzung mithilfe eines regulären Ausdrucks, um bestimmte Muster zu erkennen. In unserem Beispiel verwenden wir den regulären Ausdruck`([A-z]+) gives money to ([A-z]+)` um Sätze zu erkennen, in denen jemand Geld an jemand anderen gibt. Wir verwenden das Ersetzungsmuster`$2 takes money from $1` die Ersetzung durch Rollentausch durchzuführen. Die Verwendung von`$1` Und`$2` bezieht sich auf die durch den regulären Ausdruck erfassten Gruppen:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Beispielquellcode für Erkennen und Ersetzen innerhalb von Ersetzungsmustern mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Veranschaulichung der Verwendung von Übereinstimmungen und Ersetzungen in Ersetzungsmustern mit Aspose.Words für .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um ein Dokument zu erstellen, Text einzufügen, Suchen und Ersetzen mithilfe von regulären Ausdrücken und Ersetzungsmustern basierend auf erfassten Gruppen durchzuführen und das Dokument zu bearbeiten.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Erkennen und Ersetzungen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET?

A: Die Funktion „Erkennen und Ersetzungen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET ermöglicht es Ihnen, komplexe Suchmuster mithilfe regulärer Ausdrücke zu erkennen und Ersetzungen basierend auf den erfassten Gruppen während der Dokumentbearbeitung durchzuführen. Sie können den übereinstimmenden Text dynamisch transformieren, indem Sie im Ersetzungsmuster auf die erfassten Gruppen verweisen.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie eine`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```

#### F: Wie kann ich mit Aspose.Words für .NET Text in ein Dokument einfügen?

 A: Sobald Sie ein Dokument haben, können Sie Text einfügen mit einem`DocumentBuilder` Objekt. Um beispielsweise die Phrase "Jason gibt Paul Geld." einzufügen, können Sie das`Write` Methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### F: Wie kann ich in Aspose.Words für .NET mit regulären Ausdrücken Text suchen und ersetzen?

 A: Um Textsuche und -ersetzung mit regulären Ausdrücken in Aspose.Words für .NET durchzuführen, können Sie den`Range.Replace` Funktion zusammen mit einem regulären Ausdrucksmuster. Sie können eine`Regex` Objekt mit dem gewünschten Muster und übergeben Sie es an den`Replace` Methode:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### F: Wie kann ich erfasste Gruppen im Ersetzungsmuster während der Textsuche und -ersetzung in Aspose.Words für .NET verwenden?

 A: Um erfasste Gruppen im Ersetzungsmuster während der Textsuche und -ersetzung in Aspose.Words für .NET zu verwenden, können Sie die`UseSubstitutions` Eigentum der`FindReplaceOptions` Objekt. Dadurch können Sie die erfassten Gruppen referenzieren mit`$1`, `$2`usw. im Ersetzungsmuster:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### F: Was zeigt der Beispielquellcode für die Funktion „Erkennen und Ersetzungen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET?

A: Der Beispielquellcode demonstriert die Verwendung der Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET. Er zeigt, wie Sie ein Dokument erstellen, Text einfügen, Textsuchen und -ersetzungen mithilfe regulärer Ausdrücke durchführen und erfasste Gruppen im Ersetzungsmuster verwenden, um den übereinstimmenden Text dynamisch zu transformieren.

#### F: Wo finde ich weitere Informationen und Beispiele zur Verwendung von regulären Ausdrücken in Aspose.Words für .NET?

A: Weitere Informationen und Beispiele zur Verwendung regulärer Ausdrücke in Aspose.Words für .NET finden Sie im[Aspose.Words für .NET API-Referenzen](https://reference.aspose.com/words/net/). Die Dokumentation bietet detaillierte Erklärungen und Codebeispiele für verschiedene Szenarien mit regulären Ausdrücken und Textmanipulation in Aspose.Words für .NET.

#### F: Kann ich während der Textsuche und -ersetzung andere Aspekte des Dokuments basierend auf den erfassten Gruppen bearbeiten?

A: Ja, Sie können während der Textsuche und -ersetzung andere Aspekte des Dokuments basierend auf den erfassten Gruppen bearbeiten. Zusätzlich zur Durchführung von Textersetzungen können Sie Formatierung, Stile, Dokumentstruktur und andere Elemente basierend auf den erfassten Gruppen mithilfe der verschiedenen von Aspose.Words für .NET bereitgestellten APIs ändern.

#### F: Gibt es irgendwelche Einschränkungen oder Überlegungen bei der Verwendung von regulären Ausdrücken und erfassten Gruppen in Aspose.Words für .NET?

A: Während reguläre Ausdrücke und erfasste Gruppen leistungsstarke Funktionen für die Textsuche und -ersetzung in Aspose.Words für .NET bieten, ist es wichtig, die Auswirkungen auf Komplexität und Leistung zu berücksichtigen. Hochkomplexe reguläre Ausdrücke und eine große Anzahl erfasster Gruppen können die Leistung beeinträchtigen. Es wird empfohlen, reguläre Ausdrücke für Ihre spezifischen Anwendungsfälle zu testen und zu optimieren, um eine effiziente Dokumentbearbeitung sicherzustellen.

#### F: Kann ich die Funktion „Erkennen und Ersetzungen innerhalb von Ersetzungsmustern“ mit anderen Sprachen als Englisch verwenden?

A: Ja, die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET kann mit anderen Sprachen als Englisch verwendet werden. Reguläre Ausdrücke sind sprachunabhängig und können so gestaltet werden, dass sie bestimmten Mustern in jeder Sprache entsprechen. Sie können das Muster des regulären Ausdrucks an Ihre gewünschte Sprache und die spezifischen Textmuster anpassen, die Sie erkennen und ersetzen möchten.
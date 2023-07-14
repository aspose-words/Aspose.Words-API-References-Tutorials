---
title: Erkennen und Ersetzen innerhalb von Ersetzungsmustern
linktitle: Erkennen und Ersetzen innerhalb von Ersetzungsmustern
second_title: Aspose.Words-Dokumentverarbeitungs-API
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

 Sobald wir ein Dokument haben, können wir mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Write` Methode, um den Satz „Jason gibt Paul etwas Geld“ einzufügen. :

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

### FAQs

#### F: Was ist die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET?

A: Mit der Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET können Sie komplexe Suchmuster mithilfe regulärer Ausdrücke erkennen und Ersetzungen basierend auf den erfassten Gruppen während der Dokumentbearbeitung durchführen. Es ermöglicht Ihnen, den übereinstimmenden Text dynamisch umzuwandeln, indem Sie auf die erfassten Gruppen im Ersetzungsmuster verweisen.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie ein instanziieren`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
Document doc = new Document();
```

#### F: Wie kann ich mit Aspose.Words für .NET Text in ein Dokument einfügen?

 A: Sobald Sie ein Dokument haben, können Sie mit a Text einfügen`DocumentBuilder` Objekt. Um beispielsweise den Satz „Jason gibt Paul Geld“ einzufügen, können Sie Folgendes verwenden`Write` Methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### F: Wie kann ich in Aspose.Words für .NET eine Textsuche und -ersetzung mithilfe regulärer Ausdrücke durchführen?

 A: Um eine Textsuche und -ersetzung mit regulären Ausdrücken in Aspose.Words für .NET durchzuführen, können Sie die verwenden`Range.Replace` Funktion zusammen mit einem regulären Ausdrucksmuster. Sie können eine erstellen`Regex` Objekt mit dem gewünschten Muster und geben Sie es an den`Replace` Methode:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### F: Wie kann ich erfasste Gruppen im Ersetzungsmuster während der Textsuche und -ersetzung in Aspose.Words für .NET verwenden?

 A: Um erfasste Gruppen im Ersetzungsmuster während der Textsuche und -ersetzung in Aspose.Words für .NET zu verwenden, können Sie Folgendes aktivieren`UseSubstitutions`Eigentum der`FindReplaceOptions` Objekt. Dadurch können Sie auf die erfassten Gruppen verweisen`$1`, `$2`usw. im Ersetzungsmuster:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### F: Was zeigt der Beispielquellcode für die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET?

A: Der Beispielquellcode demonstriert die Verwendung der Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET. Es zeigt, wie man ein Dokument erstellt, Text einfügt, eine Textsuche und -ersetzung mit regulären Ausdrücken durchführt und erfasste Gruppen im Ersetzungsmuster verwendet, um den übereinstimmenden Text dynamisch umzuwandeln.

#### F: Wo finde ich weitere Informationen und Beispiele zur Verwendung regulärer Ausdrücke in Aspose.Words für .NET?

A: Weitere Informationen und Beispiele zur Verwendung regulärer Ausdrücke in Aspose.Words für .NET finden Sie in der offiziellen Dokumentation und im Aspose.Words GitHub-Repository. Die Dokumentation bietet detaillierte Erklärungen und Codebeispiele für verschiedene Szenarien mit regulären Ausdrücken und Textmanipulation in Aspose.Words für .NET.

#### F: Kann ich andere Aspekte des Dokuments basierend auf den erfassten Gruppen während der Textsuche und -ersetzung manipulieren?

A: Ja, Sie können andere Aspekte des Dokuments basierend auf den erfassten Gruppen während der Textsuche und -ersetzung bearbeiten. Zusätzlich zum Durchführen von Textersetzungen können Sie mithilfe der verschiedenen von Aspose.Words für .NET bereitgestellten APIs Formatierungen, Stile, Dokumentstruktur und andere Elemente basierend auf den erfassten Gruppen ändern.

#### F: Gibt es irgendwelche Einschränkungen oder Überlegungen bei der Verwendung regulärer Ausdrücke und erfasster Gruppen in Aspose.Words für .NET?

A: Während reguläre Ausdrücke und erfasste Gruppen leistungsstarke Funktionen für die Textsuche und -ersetzung in Aspose.Words für .NET bieten, ist es wichtig, die Auswirkungen auf Komplexität und Leistung zu berücksichtigen. Hochkomplexe reguläre Ausdrücke und eine große Anzahl erfasster Gruppen können die Leistung beeinträchtigen. Es wird empfohlen, reguläre Ausdrücke für Ihre spezifischen Anwendungsfälle zu testen und zu optimieren, um eine effiziente Dokumentenbearbeitung sicherzustellen.

#### F: Kann ich die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ mit anderen Sprachen als Englisch verwenden?

A: Ja, die Funktion „Erkennen und Ersetzen innerhalb von Ersetzungsmustern“ in Aspose.Words für .NET kann mit anderen Sprachen als Englisch verwendet werden. Reguläre Ausdrücke sind sprachunabhängig und können so erstellt werden, dass sie bestimmten Mustern in jeder Sprache entsprechen. Sie können das Muster für reguläre Ausdrücke an Ihre gewünschte Sprache und die spezifischen Textmuster anpassen, die Sie erkennen und ersetzen möchten.
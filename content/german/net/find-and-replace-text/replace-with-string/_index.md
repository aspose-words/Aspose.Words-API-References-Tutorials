---
title: Durch Zeichenfolge ersetzen
linktitle: Durch Zeichenfolge ersetzen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text durch eine Zeichenfolge in einem Word-Dokument ersetzen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-with-string/
---
In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Durch Zeichenfolge ersetzen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Mit dieser Funktion können Sie Textersetzungen basierend auf einer bestimmten Zeichenfolge in einem Word-Dokument durchführen.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Erstellen eines neuen Dokuments

 Bevor wir mit der Zeichenfolgenersetzung beginnen, müssen wir mit Aspose.Words für .NET ein neues Dokument erstellen. Dies kann durch Instanziieren von a erfolgen`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir mit a Text einfügen`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir die`Writeln` Methode zum Einfügen der Phrase „traurig, verrückt, schlecht“:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Schritt 3: Durch eine Zeichenfolge ersetzen

 Wir benutzen das`Range.Replace`Methode zum Ersetzen von Text durch eine Zeichenfolge. In unserem Beispiel ersetzen wir alle Vorkommen des Wortes „sad“ durch „bad“, indem wir das verwenden`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Schritt 4: Speichern des bearbeiteten Dokuments

 Abschließend speichern wir das geänderte Dokument mithilfe von in einem angegebenen Verzeichnis`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Beispielquellcode für „Ersetzen durch String“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung des Ersetzens durch eine Zeichenfolge mit Aspose.Words für .NET zu veranschaulichen:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Durch Zeichenfolge ersetzen“ von Aspose.Words für .NET verwendet wird. Wir folgten einer Schritt-für-Schritt-Anleitung zum Erstellen eines Dokuments, zum Einfügen von Text, zum Ersetzen durch eine Zeichenfolge und zum Speichern des geänderten Dokuments.

### FAQs

#### F: Was ist die Funktion „Mit String ersetzen“ in Aspose.Words für .NET?

A: Mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET können Sie eine Textersetzung basierend auf einer bestimmten Zeichenfolge in einem Word-Dokument durchführen. Es ermöglicht Ihnen, Vorkommen einer bestimmten Zeichenfolge zu finden und diese durch eine andere angegebene Zeichenfolge zu ersetzen.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie ein instanziieren`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### F: Wie kann ich mit Aspose.Words für .NET Text in ein Dokument einfügen?

 A: Sobald Sie ein Dokument haben, können Sie mit a Text einfügen`DocumentBuilder` Objekt. In Aspose.Words für .NET können Sie verschiedene Methoden des verwenden`DocumentBuilder` Klasse zum Einfügen von Text an verschiedenen Stellen. Sie können zum Beispiel die verwenden`Writeln` Methode zum Einfügen von Text in eine neue Zeile. Hier ist ein Beispiel:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### F: Wie kann ich in Aspose.Words für .NET eine Textersetzung durch eine Zeichenfolge durchführen?

 A: Um in Aspose.Words für .NET Text durch eine Zeichenfolge zu ersetzen, können Sie Folgendes verwenden`Range.Replace` -Methode und geben Sie die zu ersetzende Zeichenfolge und die Zeichenfolge an, durch die sie ersetzt werden soll. Diese Methode führt einen einfachen Textabgleich durch und ersetzt alle Vorkommen der angegebenen Zeichenfolge. Hier ist ein Beispiel:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### F: Kann ich mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET eine Textersetzung unter Beachtung der Groß-/Kleinschreibung durchführen?

A: Ja, standardmäßig wird bei der Funktion „Durch String ersetzen“ in Aspose.Words für .NET die Groß-/Kleinschreibung beachtet. Dies bedeutet, dass nur Text ersetzt wird, der hinsichtlich der Groß- und Kleinschreibung genau mit der angegebenen Zeichenfolge übereinstimmt. Wenn Sie eine Ersetzung ohne Berücksichtigung der Groß-/Kleinschreibung durchführen möchten, können Sie den zu ersetzenden Text und die Ersetzungszeichenfolge so ändern, dass sie dieselbe Groß-/Kleinschreibung aufweisen, oder Sie können andere Techniken wie reguläre Ausdrücke verwenden.

#### F: Kann ich mehrere Vorkommen einer Zeichenfolge in einem Dokument mithilfe der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen?

 A: Ja, Sie können mehrere Vorkommen einer Zeichenfolge in einem Dokument mithilfe der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen. Der`Range.Replace` Die Methode ersetzt alle Vorkommen der angegebenen Zeichenfolge im Inhalt des Dokuments.

#### F: Gibt es irgendwelche Einschränkungen oder Überlegungen bei der Verwendung der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET?

A: Wenn Sie die Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET verwenden, ist es wichtig, den Kontext zu kennen und sicherzustellen, dass die Ersetzung nur dort angewendet wird, wo sie beabsichtigt ist. Stellen Sie sicher, dass die Suchzeichenfolge nicht an unerwünschten Stellen erscheint, beispielsweise in anderen Wörtern oder als Teil einer speziellen Formatierung. Berücksichtigen Sie außerdem Auswirkungen auf die Leistung bei der Textverarbeitung mit großen Dokumenten oder häufigem Ersetzen.

#### F: Kann ich Zeichenfolgen mit unterschiedlichen Längen mithilfe der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen?

A: Ja, Sie können Zeichenfolgen mit unterschiedlichen Längen mithilfe der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen. Die Ersatzzeichenfolge kann beliebig lang sein und ersetzt die exakte Übereinstimmung mit der Suchzeichenfolge. Das Dokument wird entsprechend angepasst, um die neue Zeichenfolgenlänge zu berücksichtigen.
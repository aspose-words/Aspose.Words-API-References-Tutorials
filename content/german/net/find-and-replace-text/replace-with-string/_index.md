---
title: Durch Zeichenfolge ersetzen
linktitle: Durch Zeichenfolge ersetzen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text in einem Word-Dokument durch eine Zeichenfolge ersetzen.
type: docs
weight: 10
url: /de/net/find-and-replace-text/replace-with-string/
---
In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Durch Zeichenfolge ersetzen“ in der Aspose.Words-Bibliothek für .NET verwendet wird. Mit dieser Funktion können Sie Text basierend auf einer bestimmten Zeichenfolge in einem Word-Dokument ersetzen.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Neues Dokument erstellen

 Bevor wir mit der String-Ersetzung beginnen, müssen wir ein neues Dokument mit Aspose.Words für .NET erstellen. Dies kann durch die Instanziierung eines`Document` Objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Text in das Dokument einfügen

 Sobald wir ein Dokument haben, können wir Text einfügen mit einem`DocumentBuilder` Objekt. In unserem Beispiel verwenden wir das`Writeln` Methode zum Einfügen der Phrase „traurig, verrückt, schlecht“:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Schritt 3: Durch eine Zeichenfolge ersetzen

 Wir benutzen das`Range.Replace`Methode, um Text durch eine Zeichenfolge zu ersetzen. In unserem Beispiel ersetzen wir alle Vorkommen des Wortes "traurig" durch "schlecht" mithilfe der`FindReplaceOptions` Option mit der`FindReplaceDirection.Forward` Suchrichtung:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Schritt 4: Speichern des bearbeiteten Dokuments

Abschließend speichern wir das geänderte Dokument in einem angegebenen Verzeichnis mit dem`Save` Methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Beispielquellcode für „Ersetzen durch String“ mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um die Verwendung des Ersetzens durch eine Zeichenfolge mit Aspose.Words für .NET zu veranschaulichen:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Funktion „Durch Zeichenfolge ersetzen“ von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um ein Dokument zu erstellen, Text einzufügen, durch eine Zeichenfolge zu ersetzen und das geänderte Dokument zu speichern.

### Häufig gestellte Fragen

#### F: Was ist die Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET?

A: Mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET können Sie Text auf der Grundlage einer bestimmten Zeichenfolge in einem Word-Dokument ersetzen. Sie können damit Vorkommen einer bestimmten Zeichenfolge finden und durch eine andere angegebene Zeichenfolge ersetzen.

#### F: Wie kann ich mit Aspose.Words für .NET ein neues Dokument erstellen?

 A: Um ein neues Dokument mit Aspose.Words für .NET zu erstellen, können Sie eine`Document` Objekt. Hier ist ein Beispiel für C#-Code zum Erstellen eines neuen Dokuments:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### F: Wie kann ich mit Aspose.Words für .NET Text in ein Dokument einfügen?

 A: Sobald Sie ein Dokument haben, können Sie Text einfügen mit einem`DocumentBuilder` Objekt. In Aspose.Words für .NET können Sie verschiedene Methoden des`DocumentBuilder` Klasse, um Text an verschiedenen Stellen einzufügen. Sie können beispielsweise die`Writeln` Methode zum Einfügen von Text in eine neue Zeile. Hier ist ein Beispiel:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### F: Wie kann ich in Aspose.Words für .NET Text durch eine Zeichenfolge ersetzen?

 A: Um Text durch eine Zeichenfolge in Aspose.Words für .NET zu ersetzen, können Sie den`Range.Replace` -Methode und geben Sie die zu ersetzende Zeichenfolge und die Zeichenfolge an, durch die sie ersetzt werden soll. Diese Methode führt eine einfache Textübereinstimmung durch und ersetzt alle Vorkommen der angegebenen Zeichenfolge. Hier ist ein Beispiel:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### F: Kann ich mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET einen Textersetzungsvorgang unter Berücksichtigung der Groß-/Kleinschreibung durchführen?

A: Ja, standardmäßig ist die Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET case-sensitiv. Das bedeutet, dass nur Text ersetzt wird, der in Bezug auf die Groß- und Kleinschreibung genau mit der angegebenen Zeichenfolge übereinstimmt. Wenn Sie einen case-insensitiven Ersatz durchführen möchten, können Sie den zu ersetzenden Text und die Ersatzzeichenfolge so ändern, dass sie dieselbe Groß- und Kleinschreibung haben, oder Sie können andere Techniken wie reguläre Ausdrücke verwenden.

#### F: Kann ich mehrere Vorkommen einer Zeichenfolge in einem Dokument mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen?

 A: Ja, Sie können mehrere Vorkommen einer Zeichenfolge in einem Dokument mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen. Die`Range.Replace` Methode ersetzt alle Vorkommen der angegebenen Zeichenfolge im Inhalt des Dokuments.

#### F: Gibt es irgendwelche Einschränkungen oder Überlegungen bei der Verwendung der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET?

A: Wenn Sie die Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET verwenden, ist es wichtig, den Kontext zu beachten und sicherzustellen, dass der Ersatz nur dort angewendet wird, wo er beabsichtigt ist. Stellen Sie sicher, dass die Suchzeichenfolge nicht an unerwünschten Stellen erscheint, z. B. innerhalb anderer Wörter oder als Teil einer speziellen Formatierung. Berücksichtigen Sie außerdem die Leistungseinbußen bei der Textverarbeitung mit großen Dokumenten oder häufigen Ersetzungen.

#### F: Kann ich Zeichenfolgen unterschiedlicher Länge mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen?

A: Ja, Sie können Zeichenfolgen unterschiedlicher Länge mit der Funktion „Durch Zeichenfolge ersetzen“ in Aspose.Words für .NET ersetzen. Die Ersatzzeichenfolge kann beliebig lang sein und ersetzt die genaue Übereinstimmung mit der Suchzeichenfolge. Das Dokument wird entsprechend angepasst, um die neue Zeichenfolgenlänge aufzunehmen.
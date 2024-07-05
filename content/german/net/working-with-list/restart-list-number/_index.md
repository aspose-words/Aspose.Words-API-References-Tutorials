---
title: Neustartlistennummer
linktitle: Neustartlistennummer
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Nummer einer Liste in einem Word-Dokument zurücksetzen.
type: docs
weight: 10
url: /de/net/working-with-list/restart-list-number/
---
In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Nummer einer Liste in einem Word-Dokument zurücksetzen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Erstellen des Dokuments und des Dokumentgenerators

Erstellen Sie zunächst ein neues Dokument und einen zugehörigen Dokumentgenerator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Erstellen und Anpassen der ersten Liste

Erstellen Sie als Nächstes eine Liste auf Grundlage einer vorhandenen Vorlage und passen Sie dann die Ebenen an:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Schritt 3: Elemente zur ersten Liste hinzufügen

Verwenden Sie den Dokumentgenerator, um Elemente zur ersten Liste hinzuzufügen und Listennummern zu entfernen:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Schritt 4: Erstellen und Anpassen der zweiten Liste

Um die erste Liste durch Zurücksetzen der Nummer wiederzuverwenden, erstellen Sie eine Kopie des ursprünglichen Listenlayouts:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Sie können bei Bedarf auch weitere Änderungen an der zweiten Liste vornehmen.

## Schritt 5: Elemente zur zweiten Liste hinzufügen

Verwenden Sie erneut den Dokument-Generator, um Elemente zur zweiten Liste hinzuzufügen und die Listennummern zu entfernen:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Schritt 6: Speichern Sie das geänderte Dokument

Speichern Sie abschließend das geänderte Dokument:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

So! Sie haben die Nummer einer Liste in einem Word-Dokument mit Aspose.Words für .NET erfolgreich zurückgesetzt.

### Beispiel-Quellcode zum Zurücksetzen der Listennummer

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine Liste basierend auf einer Vorlage.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Um die erste Liste wiederzuverwenden, müssen wir die Nummerierung neu starten, indem wir eine Kopie der ursprünglichen Listenformatierung erstellen.
List list2 = doc.Lists.AddCopy(list1);

// Wir können die neue Liste beliebig verändern, darunter auch eine neue Startnummer festlegen.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Häufig gestellte Fragen

#### F: Wie kann ich die Nummerierung einer Liste in Aspose.Words neu starten?

 A: Um die Nummerierung einer Liste in Aspose.Words neu zu starten, können Sie den`ListRestartAtNumber` Methode der`List` Klasse. Mit dieser Methode können Sie einen neuen Wählwert festlegen, ab dem die Liste neu gestartet werden soll. Sie können beispielsweise`list.ListRestartAtNumber(1)` , um die Nummerierung ab 1 neu zu starten.

#### F: Ist es möglich, Präfix und Suffix der neu gestarteten Listennummerierung in Aspose.Words anzupassen?

 A: Ja, Sie können Präfix und Suffix der neu gestarteten Listennummerierung in Aspose.Words anpassen. Die`ListLevel` Klasse bietet Eigenschaften wie`ListLevel.NumberPrefix` Und`ListLevel.NumberSuffix`Damit können Sie das Präfix und Suffix für jede Ebene in der Liste angeben. Mit diesen Eigenschaften können Sie das Präfix und Suffix nach Bedarf anpassen.

#### F: Wie kann ich einen bestimmten Nummerierungswert angeben, ab dem die Liste neu gestartet werden soll?

 A: Um einen bestimmten Zahlenwert anzugeben, ab dem die Liste neu gestartet werden soll, können Sie das`ListRestartAtNumber` Methode, die den gewünschten Wert als Argument übergibt. Um beispielsweise die Nummerierung bei 5 neu zu starten, können Sie verwenden`list.ListRestartAtNumber(5)`.

#### F: Ist es möglich, die mehrstufige Listennummerierung in Aspose.Words neu zu starten?

 A: Ja, Aspose.Words unterstützt die Neunummerierung mehrerer Listenebenen. Sie können die`ListRestartAtNumber` Methode auf jeder Listenebene, um die Nummerierung einzeln neu zu starten. Sie können beispielsweise`list.Levels[0].ListRestartAtNumber(1)` um die erste Listenebene von 1 neu zu starten, und`list.Levels[1].ListRestartAtNumber(1)` um die Liste der zweiten Ebene beginnend bei 1 neu zu starten, und so weiter.




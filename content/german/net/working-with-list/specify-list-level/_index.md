---
title: Listenebene angeben
linktitle: Listenebene angeben
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Listenebene in einem Word-Dokument angeben.
type: docs
weight: 10
url: /de/net/working-with-list/specify-list-level/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Listenebene in einem Word-Dokument festlegen. Wir erklären den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie dies noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie von[[Originaltext von Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Erstellen des Dokuments und des Dokumentgenerators

Erstellen Sie zunächst ein neues Dokument und einen zugehörigen Dokumentgenerator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Erstellen und Anwenden einer nummerierten Liste

Erstellen Sie als Nächstes eine nummerierte Liste basierend auf einer der Listenvorlagen von Microsoft Word und wenden Sie sie auf den aktuellen Absatz im Dokument-Generator an:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Schritt 3: Spezifikation der Listenebene

 Verwenden Sie den Dokumentgenerator`ListLevelNumber` -Eigenschaft, um die Listenebene anzugeben und dem Absatz Text hinzuzufügen:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Wiederholen Sie diese Schritte, um Listenebenen anzugeben und auf jeder Ebene Text hinzuzufügen.

## Schritt 4: Erstellen und Anwenden einer Aufzählungsliste

Sie können eine Aufzählungsliste auch mithilfe einer der Listenvorlagen von Microsoft Word erstellen und anwenden:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Schritt 5: Hinzufügen von Text zu Aufzählungslistenebenen

 Verwenden Sie die`ListLevelNumber` -Eigenschaft erneut, um die Aufzählungslistenebene anzugeben und Text hinzuzufügen:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Schritt 6: Formatierungsliste beenden

 Um die Formatierung der Liste zu beenden, setzen Sie`null` zum`List`Eigenschaft des Dokumentgenerators:

```csharp
builder. ListFormat. List = null;
```

## Schritt 7: Speichern des geänderten Dokuments

Speichern Sie das geänderte Dokument:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

So! Sie haben die Listenebene in einem Word-Dokument erfolgreich mit Aspose.Words für .NET angegeben.

### Beispielquellcode zum Festlegen der Listenebene

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Erstellen Sie eine nummerierte Liste basierend auf einer der Microsoft Word-Listenvorlagen
//und wenden Sie es auf den aktuellen Absatz des Dokument-Generators an.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Diese Liste enthält neun Level. Probieren wir sie alle aus.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Erstellen Sie eine Aufzählungsliste basierend auf einer der Microsoft Word-Listenvorlagen
//und wenden Sie es auf den aktuellen Absatz des Dokument-Generators an.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Auf diese Weise können Sie die Listenformatierung stoppen.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Häufig gestellte Fragen

#### F: Wie kann ich die Listenebene in Aspose.Words angeben?

 A: Um die Listenebene in Aspose.Words festzulegen, müssen Sie eine Instanz des`List` Klasse und geben Sie ihr eine nummerierte Liste. Dann können Sie die`Paragraph.ListFormat.ListLevelNumber` -Eigenschaft, um die Ebene jedes Listenelements anzugeben. Sie können diese Liste mit einem Abschnitt Ihres Dokuments verknüpfen, damit die Listenelemente die gewünschte Ebene haben.

#### F: Ist es möglich, das Nummerierungsformat von Listenelementen in Aspose.Words zu ändern?

 A: Ja, Sie können das Nummerierungsformat von Listenelementen in Aspose.Words ändern.`ListLevel` bietet hierfür mehrere Eigenschaften an, wie zum Beispiel`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`usw. Mit diesen Eigenschaften können Sie das Nummerierungsformat für Listenelemente festlegen, beispielsweise arabische Ziffern, römische Ziffern, Buchstaben usw.

#### F: Kann ich einer nummerierten Liste in Aspose.Words weitere Ebenen hinzufügen?

 A: Ja, es ist möglich, einer nummerierten Liste in Aspose.Words zusätzliche Ebenen hinzuzufügen.`ListLevel`Mit der Klasse können Sie Formatierungseigenschaften für jede Ebene der Liste festlegen. Sie können Optionen wie Präfix, Suffix, Ausrichtung, Einzug usw. festlegen. Auf diese Weise können Sie Listen mit mehreren Hierarchieebenen erstellen.



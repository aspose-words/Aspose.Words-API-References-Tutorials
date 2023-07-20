---
title: Geben Sie die Listenebene an
linktitle: Geben Sie die Listenebene an
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET die Listenebene in einem Word-Dokument angeben.
type: docs
weight: 10
url: /de/net/working-with-list/specify-list-level/
---

In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET die Listenebene in einem Word-Dokument festlegen. Wir erklären Ihnen den bereitgestellten C#-Quellcode und zeigen Ihnen, wie Sie ihn in Ihren eigenen Projekten implementieren.

 Stellen Sie zunächst sicher, dass Aspose.Words für .NET in Ihrer Entwicklungsumgebung installiert und konfiguriert ist. Wenn Sie es noch nicht getan haben, laden Sie die Bibliothek herunter und installieren Sie sie unter[Aspose.Releases]https://releases.aspose.com/words/net/.

## Schritt 1: Erstellen des Dokuments und Dokumentengenerators

Erstellen Sie zunächst ein neues Dokument und einen zugehörigen Dokumentgenerator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Erstellen und Anwenden einer nummerierten Liste

Erstellen Sie als Nächstes eine nummerierte Liste basierend auf einer der Listenvorlagen von Microsoft Word und wenden Sie diese auf den aktuellen Absatz im Document Builder an:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Schritt 3: Spezifikation der Listenebene

 Verwenden Sie den Document Builder`ListLevelNumber` -Eigenschaft, um die Listenebene anzugeben und Text zum Absatz hinzuzufügen:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Wiederholen Sie diese Schritte, um Listenebenen anzugeben und auf jeder Ebene Text hinzuzufügen.

## Schritt 4: Erstellen und Anwenden einer Aufzählungsliste

Sie können eine Liste mit Aufzählungszeichen auch mithilfe einer der Listenvorlagen von Microsoft Word erstellen und anwenden:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Schritt 5: Text zu Listenebenen mit Aufzählungszeichen hinzufügen

 Benutzen Sie die`ListLevelNumber` Eigenschaft erneut, um die Ebene der Aufzählungsliste anzugeben und Text hinzuzufügen:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Schritt 6: Beenden Sie die Formatierung der Liste

 Um die Listenformatierung zu stoppen, legen Sie fest`null` zum`List` Eigenschaft des Dokumentengenerators:

```csharp
builder. ListFormat. List = null;
```

## Schritt 7: Speichern des geänderten Dokuments

Speichern Sie das geänderte Dokument:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

So ! Sie haben die Listenebene in einem Word-Dokument mit Aspose.Words für .NET erfolgreich angegeben.

### Beispielquellcode zur Angabe der Listenebene

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//Erstellen Sie eine nummerierte Liste basierend auf einer der Microsoft Word-Listenvorlagen
// und wenden Sie es auf den aktuellen Absatz des Document Builders an.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Es gibt neun Level in dieser Liste, probieren wir sie alle aus.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Erstellen Sie eine Liste mit Aufzählungszeichen basierend auf einer der Microsoft Word-Listenvorlagen
// und wenden Sie es auf den aktuellen Absatz des Document Builders an.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Dies ist eine Möglichkeit, die Listenformatierung zu stoppen.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### FAQs

#### F: Wie kann ich die Listenebene in Aspose.Words angeben?

 A: Um die Listenebene in Aspose.Words anzugeben, müssen Sie eine Instanz von erstellen`List` Klasse und gib ihr eine nummerierte Liste. Dann können Sie das verwenden`Paragraph.ListFormat.ListLevelNumber` -Eigenschaft, um die Ebene jedes Listenelements anzugeben. Sie können diese Liste einem Abschnitt Ihres Dokuments zuordnen, sodass die Listenelemente die gewünschte Ebene haben.

#### F: Ist es möglich, das Nummerierungsformat von Listenelementen in Aspose.Words zu ändern?

 A: Ja, Sie können das Nummerierungsformat von Listenelementen in Aspose.Words ändern. Der`ListLevel` Die Klasse bietet hierfür mehrere Eigenschaften an, wie z`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`usw. Mit diesen Eigenschaften können Sie das Nummerierungsformat für Listenelemente festlegen, z. B. arabische Ziffern, römische Ziffern, Buchstaben usw.

#### F: Kann ich einer nummerierten Liste in Aspose.Words zusätzliche Ebenen hinzufügen?

 A: Ja, es ist möglich, einer nummerierten Liste in Aspose.Words zusätzliche Ebenen hinzuzufügen. Der`ListLevel` Mit der Klasse können Sie Formatierungseigenschaften für jede Ebene der Liste festlegen. Sie können Optionen wie Präfix, Suffix, Ausrichtung, Einzug usw. festlegen. Dadurch können Sie Listen mit mehreren Hierarchieebenen erstellen.



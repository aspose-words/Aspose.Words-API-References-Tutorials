---
title: In Abschnitt verschieben
linktitle: In Abschnitt verschieben
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Schritt-für-Schritt-Anleitung zur Verwendung von „In Abschnitt verschieben“ in Aspose.Words für .NET zum Bearbeiten von Abschnitten und Absätzen in Word-Dokumenten.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/move-to-section/
---

In diesem Beispiel führen wir Sie Schritt für Schritt durch die Verwendung der Funktion „In Abschnitt verschieben“ von Aspose.Words für .NET mithilfe des bereitgestellten C#-Quellcodes. Mit dieser Funktion können Sie durch verschiedene Abschnitte in einem Word-Dokument navigieren und diese bearbeiten. Führen Sie die folgenden Schritte aus, um diese Funktionalität in Ihre Anwendung zu integrieren.

## Schritt 1: Erstellen Sie ein neues Dokument und fügen Sie einen Abschnitt hinzu

Zuerst müssen wir ein neues Dokument erstellen und ihm einen Abschnitt hinzufügen. Verwenden Sie den folgenden Code, um diesen Schritt auszuführen:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Dieser Code erstellt ein neues leeres Dokument und fügt diesem Dokument einen Abschnitt hinzu.

## Schritt 2: Verschieben Sie den DocumentBuilder in den zweiten Abschnitt und fügen Sie Text hinzu

Als nächstes müssen wir den DocumentBuilder in den zweiten Abschnitt des Dokuments verschieben und dort Text hinzufügen. Verwenden Sie den folgenden Code, um diesen Schritt auszuführen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Dieser Code erstellt einen DocumentBuilder aus dem vorhandenen Dokument und bewegt dann den Cursor vom DocumentBuilder zum zweiten Abschnitt des Dokuments. Schließlich wird der angegebene Text zu diesem Abschnitt hinzugefügt.

## Schritt 3: Laden Sie ein Dokument mit vorhandenen Absätzen

Wenn Sie mit einem vorhandenen Dokument arbeiten möchten, das Absätze enthält, können Sie dieses Dokument mit dem folgenden Code laden:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Dieser Code lädt das angegebene Dokument (ersetzen Sie „MyDir + „Paragraphs.docx“)„“mit dem tatsächlichen Pfad zu Ihrem Dokument) und greift auf die Sammlung von Absätzen aus dem ersten Abschnitt des Dokuments zu. Die Linie`Assert.AreEqual(22, paragraphs.Count);` prüft, ob das Dokument 22 Absätze enthält.

## Schritt 4: Erstellen Sie einen DocumentBuilder für ein Dokument

Mithilfe von Positionsindizes können Sie den DocumentBuilder-Cursor zu einem bestimmten Absatz erstellen.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Schritt 5: Bewegen Sie den Cursor auf einen bestimmten Absatz


Mithilfe von Positionsindizes können Sie den DocumentBuilder-Cursor zu einem bestimmten Absatz bewegen. So geht's:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Dieser Code bewegt den Cursor des DocumentBuilders zum dritten Absatz des zweiten Abschnitts (Absatz bei Index 2) und an Position 10. Anschließend fügt er einen neuen Absatz mit etwas Text hinzu und überprüft, ob der Cursor richtig auf diesem neuen Absatz positioniert ist.

### Beispielquellcode für „Move To Move To Section“ mit Aspose.Words für .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Verschieben Sie einen DocumentBuilder in den zweiten Abschnitt und fügen Sie Text hinzu.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Erstellen Sie ein Dokument mit Absätzen.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

//Wenn wir einen DocumentBuilder für ein Dokument erstellen, befindet sich sein Cursor standardmäßig ganz am Anfang des Dokuments.
// und alle vom DocumentBuilder hinzugefügten Inhalte werden dem Dokument einfach vorangestellt.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// Sie können den Cursor an eine beliebige Stelle in einem Absatz bewegen.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Das ist alles ! Sie haben nun verstanden, wie Sie die Funktion „In Abschnitt verschieben“ von Aspose.Words für .NET mithilfe des bereitgestellten Quellcodes verwenden. Sie können diese Funktionalität jetzt in Ihre eigene Anwendung integrieren und Abschnitte und Absätze Ihrer Word-Dokumente dynamisch bearbeiten.


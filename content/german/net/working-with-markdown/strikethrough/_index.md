---
title: Durchgestrichen
linktitle: Durchgestrichen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie den durchgestrichenen Textstil mit Aspose.Words für .NET anwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/strikethrough/
---


In diesem Beispiel zeigen wir Ihnen, wie Sie den durchgestrichenen Textstil mit Aspose.Words für .NET anwenden. Durchgestrichener Text wird verwendet, um anzuzeigen, dass der Text gelöscht wurde oder nicht mehr gültig ist.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Durchgestrichenen Textstil anwenden

 Wir aktivieren den durchgestrichenen Textstil, indem wir festlegen`StrikeThrough` Eigentum der`Font` widersprechen`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Schritt 3: Durchgestrichenen Text hinzufügen

 Wir können jetzt mit dem Dokumentgenerator durchgestrichenen Text hinzufügen`Writeln` Methode.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Beispielquellcode für durchgestrichenen Text mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Machen Sie den Text durchgestrichen.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie den durchgestrichenen Textstil mit Aspose.Words für .NET anwenden.

### FAQs

#### F: Wie kann ich den durchgestrichenen Text in Aspose.Words hinzufügen?

 A: Um den durchgestrichenen Text in Aspose.Words hinzuzufügen, können Sie die verwenden`Font.StrikeThrough` Eigentum der`Run`Objekt. Sie können diese Eigenschaft auf festlegen`true` um durchgestrichenen Text zu einem bestimmten Text hinzuzufügen. Sie können zum Beispiel verwenden`run.Font.StrikeThrough=true` um den durchgestrichenen Text in das einzufügen`Run` Objekt.

#### F: Ist es möglich, den durchgestrichenen Text zu mehreren Textteilen im selben Absatz hinzuzufügen?

 A: Ja, Sie können durchgestrichenen Text zu mehreren Textteilen in einem einzigen Absatz hinzufügen, indem Sie mehrere verwenden`Run` Objekte. Sie können mehrere erstellen`Run` Objekte und legen Sie die fest`Font.StrikeThrough` Eigentum zu`true`für jedes Objekt, um den durchgestrichenen Text zu den gewünschten Textteilen hinzuzufügen. Anschließend können Sie sie mit dem zum Absatz hinzufügen`Paragraph.AppendChild(run)` Methode.

#### F: Kann ich durchgestrichenen Text zu Text hinzufügen, der sich in einer Tabelle oder Zelle in Aspose.Words befindet?

 A: Ja, Sie können durchgestrichenen Text zu Text hinzufügen, der sich in einer Tabelle oder Zelle in Aspose.Words befindet. Sie können mit den entsprechenden Methoden zu der gewünschten Zelle oder dem gewünschten Absatz springen und dann die durchgestrichene Textformatierung mithilfe der anwenden`Font.StrikeThrough` Eigentum der`Run` oder`Paragraph` Objekt.
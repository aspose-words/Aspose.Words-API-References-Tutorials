---
title: Durchgestrichen
linktitle: Durchgestrichen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET den durchgestrichenen Textstil anwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/strikethrough/
---


In diesem Beispiel zeigen wir Ihnen Schritt für Schritt, wie Sie den Textstil „Durchgestrichen“ mit Aspose.Words für .NET anwenden. Durchgestrichener Text wird verwendet, um anzuzeigen, dass der Text gelöscht wurde oder nicht mehr gültig ist.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Durchgestrichenen Textstil anwenden

Wir aktivieren den durchgestrichenen Textstil, indem wir die`StrikeThrough` Eigentum der`Font` Einwände erheben gegen`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Schritt 3: Durchgestrichenen Text hinzufügen

 Wir können nun durchgestrichenen Text hinzufügen, indem wir den Dokumentgenerator verwenden`Writeln` Methode.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Beispielquellcode für durchgestrichenen Text mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Machen Sie den Text durchgestrichen.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie den durchgestrichenen Textstil mit Aspose.Words für .NET anwenden.

### Häufig gestellte Fragen

#### F: Wie kann ich den durchgestrichenen Text in Aspose.Words hinzufügen?

 A: Um den durchgestrichenen Text in Aspose.Words hinzuzufügen, können Sie den`Font.StrikeThrough` Eigentum der`Run`Objekt. Sie können diese Eigenschaft auf`true` um bestimmten Text durchgestrichenen Text hinzuzufügen. Sie können beispielsweise`run.Font.StrikeThrough=true` , um den durchgestrichenen Text in das`Run` Objekt.

#### F: Ist es möglich, den durchgestrichenen Text mehreren Textteilen im selben Absatz hinzuzufügen?

 A: Ja, Sie können mehrere Textteile in einem einzigen Absatz durchgestrichenen Text hinzufügen, indem Sie mehrere`Run` Objekte. Sie können mehrere`Run` Objekte und legen Sie die`Font.StrikeThrough`Eigentum an`true` für jedes Objekt, um den durchgestrichenen Text an die gewünschten Textteile anzufügen. Anschließend können Sie diese mit dem`Paragraph.AppendChild(run)` Methode.

#### F: Kann ich Text in einer Tabelle oder Zelle in Aspose.Words durchgestrichenen Text hinzufügen?

 A: Ja, Sie können Text in einer Tabelle oder Zelle in Aspose.Words durchgestrichenen Text hinzufügen. Sie können mit den entsprechenden Methoden zu der gewünschten Zelle oder dem gewünschten Absatz springen und dann die Formatierung des durchgestrichenen Textes mit dem`Font.StrikeThrough` Eigentum der`Run` oder`Paragraph` Objekt.
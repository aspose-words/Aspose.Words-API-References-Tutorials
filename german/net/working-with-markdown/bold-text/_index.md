---
title: Fetter Text
linktitle: Fetter Text
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Text mit Aspose.Words für .NET fett formatieren.
type: docs
weight: 10
url: /de/net/working-with-markdown/bold-text/
---

In diesem Beispiel erklären wir Ihnen, wie Sie Text mit Aspose.Words für .NET fett formatieren. Durch die Fettschrift wird der Text besser sichtbar und hervorgehoben.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Fetter Text

 Wir können den Text fett formatieren, indem wir ihn im Document Builder festlegen`Font.Bold` Eigentum zu`true`.

```csharp
builder.Font.Bold = true;
```

## Schritt 3: Inhalte zum Dokument hinzufügen

 Jetzt können wir mithilfe der Document Builder-Methoden Inhalte zum Dokument hinzufügen, z`Writeln`, wodurch eine Textzeile hinzugefügt wird.

```csharp
builder.Writeln("This text will be bold");
```

## Beispielquellcode für fetten Text mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Machen Sie den Text fett.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET Text fett formatieren.


### FAQs

#### F: Wie kann ich Text in Aspose.Words fett formatieren?

 A: Um Text in Aspose.Words fett darzustellen, können Sie Folgendes verwenden`Font.Bold` Eigentum der`Run`Objekt. Sie können diese Eigenschaft auf festlegen`true` um einen bestimmten Text fett zu formatieren. Sie können zum Beispiel verwenden`run.Font.Bold=true` um den Text darin fett zu machen`Run` Objekt.

#### F: Ist es möglich, mehrere Textteile im selben Absatz fett zu formatieren?

 A: Ja, Sie können mehrere Textteile in einem einzelnen Absatz mit der Funktion „Mehrere“ fett formatieren`Run` Objekte. Sie können mehrere erstellen`Run` Objekte und legen Sie die fest`Font.Bold` Eigentum zu`true` für jedes Objekt, um die gewünschten Textteile fett darzustellen. Anschließend können Sie sie mit dem zum Absatz hinzufügen`Paragraph.AppendChild(run)` Methode.

#### F: Kann ich Text in einer Tabelle oder Zelle in Aspose.Words fett formatieren?

 A: Ja, Sie können Text in einer Tabelle oder Zelle in Aspose.Words fett formatieren. Sie können mit den entsprechenden Methoden zu der gewünschten Zelle oder dem gewünschten Absatz navigieren und dann die Fettformatierung mithilfe von anwenden`Font.Bold` Eigentum der`Run` oder`Paragraph` Objekt.
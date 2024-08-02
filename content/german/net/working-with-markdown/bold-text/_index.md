---
title: Fettgedruckter Text
linktitle: Fettgedruckter Text
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Text fett formatieren.
type: docs
weight: 10
url: /de/net/working-with-markdown/bold-text/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET Text fett formatieren. Durch Fettformatierung wird der Text besser sichtbar und hervorgehoben.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Fetter Text

 Wir können den Text fett formatieren, indem wir die Einstellungen des Dokument-Generators`Font.Bold`Eigentum an`true`.

```csharp
builder.Font.Bold = true;
```

## Schritt 3: Dem Dokument Inhalt hinzufügen

 Jetzt können wir dem Dokument Inhalt hinzufügen, indem wir die Methoden des Dokumentgenerators verwenden, wie zum Beispiel`Writeln`, wodurch eine Textzeile hinzugefügt wird.

```csharp
builder.Writeln("This text will be bold");
```

## Beispiel-Quellcode für fetten Text mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Machen Sie den Text fett.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET Text fett formatieren.


### Häufig gestellte Fragen

#### F: Wie kann ich Text in Aspose.Words fett machen?

 A: Um Text in Aspose.Words fett zu machen, können Sie den`Font.Bold` Eigentum der`Run` Objekt. Sie können diese Eigenschaft auf`true` um bestimmten Text fett zu machen. Sie können beispielsweise`run.Font.Bold=true` um den Text fett zu machen`Run` Objekt.

#### F: Ist es möglich, mehrere Textteile im selben Absatz fett darzustellen?

 A: Ja, Sie können mehrere Textteile in einem einzigen Absatz fett formatieren, indem Sie mehrere`Run` Objekte. Sie können mehrere`Run` Objekte und legen Sie die`Font.Bold`Eigentum an`true` für jedes Objekt, um die gewünschten Textteile fett zu machen. Anschließend können Sie sie mit dem`Paragraph.AppendChild(run)` Methode.

#### F: Kann ich Text in einer Tabelle oder Zelle in Aspose.Words fett markieren?

 A: Ja, Sie können Text in einer Tabelle oder Zelle in Aspose.Words fett formatieren. Sie können mit den entsprechenden Methoden zu der gewünschten Zelle oder dem gewünschten Absatz navigieren und dann die Fettformatierung mit dem`Font.Bold` Eigentum der`Run` oder`Paragraph` Objekt.
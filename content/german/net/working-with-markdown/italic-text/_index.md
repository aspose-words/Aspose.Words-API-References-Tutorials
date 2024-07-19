---
title: Kursiver Text
linktitle: Kursiver Text
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Text kursiv setzen.
type: docs
weight: 10
url: /de/net/working-with-markdown/italic-text/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Kursivtextfunktion mit Aspose.Words für .NET verwenden. Kursivtext wird verwendet, um bestimmte Teile eines Dokuments hervorzuheben.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Text kursiv setzen

 Wir können Text kursiv setzen, indem wir die Schriftart`Italic`Eigentum an`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Beispiel-Quellcode für kursiven Text mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Machen Sie den Text kursiv.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Kursivtextfunktion mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Wie kann ich Text in Aspose.Words kursiv setzen?

 A: Um Text in Aspose.Words kursiv zu machen, können Sie den`Font.Italic` Eigentum der`Run`Objekt. Sie können diese Eigenschaft auf`true` um bestimmten Text kursiv zu setzen. Sie können beispielsweise`run.Font.Italic=true` um den Text kursiv zu setzen, der in der`Run` Objekt.

#### F: Ist es möglich, mehrere Textteile im selben Absatz kursiv zu setzen?

 A: Ja, Sie können mehrere Textteile in einem einzigen Absatz kursiv setzen, indem Sie mehrere`Run` Objekte. Sie können mehrere`Run` Objekte und legen Sie die`Font.Italic`Eigentum an`true`für jedes Objekt, um die gewünschten Textteile kursiv zu formatieren. Anschließend können Sie sie mit dem`Paragraph.AppendChild(run)` Methode.

#### F: Kann ich Text, der sich in einer Tabelle oder Zelle in Aspose.Words befindet, kursiv schreiben?

 A: Ja, Sie können Text in einer Tabelle oder Zelle in Aspose.Words kursiv formatieren. Sie können mit den entsprechenden Methoden zu der gewünschten Zelle oder dem gewünschten Absatz navigieren und dann die Kursivformatierung mit dem`Font.Italic` Eigentum der`Run` oder`Paragraph` Objekt.
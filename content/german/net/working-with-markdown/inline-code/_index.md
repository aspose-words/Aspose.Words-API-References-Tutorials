---
title: Inline-Code
linktitle: Inline-Code
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Inline-Code erstellen.
type: docs
weight: 10
url: /de/net/working-with-markdown/inline-code/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie die Inline-Code-Funktion mit Aspose.Words für .NET verwenden. Inline-Code wird verwendet, um Codeteile innerhalb eines Absatzes visuell darzustellen.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Styling für Inline-Code hinzufügen

 Wir fügen einen benutzerdefinierten Stil für den Inline-Code hinzu, indem wir den`Styles.Add` Methode der`Document` Objekt. In diesem Beispiel erstellen wir einen Stil namens „InlineCode“ für Inline-Code mit einem Standard-Backtick.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Schritt 3: Inline-Code hinzufügen

Jetzt können wir Inline-Code mit dem benutzerdefinierten Stil „InlineCode“ hinzufügen. In diesem Beispiel fügen wir zwei Textteile mit unterschiedlicher Anzahl von Backticks hinzu.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Beispielquellcode für Inline Code mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Anzahl der Backticks fehlt, standardmäßig wird ein Backtick verwendet.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Es wird 3 Backticks geben.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Inline-Code-Funktionalität mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Wie kann ich den Inline-Code in Aspose.Words verwenden?

 A: Um Inline-Code in Aspose.Words zu verwenden, können Sie den zu formatierenden Text mit entsprechenden Tags umgeben. Sie können beispielsweise das`<code>` oder`<kbd>` Tag, um den Text zu umgeben, der als Inline-Code formatiert werden soll.

#### F: Ist es möglich, in Aspose.Words die Schriftart oder Farbe des Inline-Codes anzugeben?

 A: Ja, Sie können die Schriftart oder Farbe des Inline-Codes in Aspose.Words festlegen. Sie können den`Font.Name` Und`Font.Color` Eigenschaften der`Run` Objekt, um die Schriftart und Farbe des Inline-Codes festzulegen. Sie können beispielsweise`run.Font.Name = "Courier New"` um die Schriftart für Inline-Code festzulegen und`run.Font.Color = Color.Blue` um die Farbe festzulegen.

#### F: Kann ich den Inline-Code in einem Absatz verwenden, der andere Textelemente enthält?

 A: Ja, Sie können den Inline-Code in einem Absatz verwenden, der andere Textelemente enthält. Sie können mehrere`Run` Objekte, um verschiedene Teile des Absatzes darzustellen, und verwenden Sie dann Inline-Code-Tags, um nur die spezifischen Teile als Inline-Code zu formatieren. Anschließend können Sie sie dem Absatz hinzufügen, indem Sie den`Paragraph.AppendChild(run)` Methode.
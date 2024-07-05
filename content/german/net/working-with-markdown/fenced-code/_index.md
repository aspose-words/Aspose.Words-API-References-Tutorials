---
title: Eingezäunter Code
linktitle: Eingezäunter Code
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie die Funktion für eingezäunten Code mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/fenced-code/
---

In diesem Beispiel zeigen wir Ihnen Schritt für Schritt, wie Sie die Funktion „Fenced Code“ mit Aspose.Words für .NET verwenden. Fenced Code wird verwendet, um Codeblöcke mit einer bestimmten Formatierung darzustellen.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Einen Stil für eingezäunten Code hinzufügen

 Wir werden einen benutzerdefinierten Stil für den eingezäunten Code hinzufügen, indem wir den`Styles.Add` Methode der`Document` Objekt. In diesem Beispiel erstellen wir einen Stil namens „FencedCode“ für den eingezäunten Code.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Schritt 3: Hinzufügen von eingezäuntem Code ohne Informationen

Jetzt können wir mit dem benutzerdefinierten Stil „FencedCode“ einen eingezäunten Codeblock ohne Informationszeichenfolge hinzufügen.

```csharp
builder.Writeln("This is an fenced code");
```

## Schritt 4: Eingezäunten Code mit Info-String hinzufügen

Wir können auch einen eingezäunten Codeblock mit einer Zeichenfolge von Informationen hinzufügen, indem wir einen anderen benutzerdefinierten Stil verwenden. In diesem Beispiel erstellen wir einen Stil namens „FencedCode.C#“, um einen Block von C#-Code darzustellen.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Beispielquellcode für Fenced Code mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Häufig gestellte Fragen

#### F: Was ist abgegrenzter Code in Markdown?

A: Getrennter Code in Markdown ist eine Formatierungsmethode, die zum Anzeigen von Code in einem Markdown-Dokument verwendet wird. Dabei wird der Code mit bestimmten Trennzeichen umrahmt.

#### F: Welche Vorteile bietet abgegrenzter Code in Markdown?

A: Durch Trennzeichen getrennter Code in Markdown verbessert die Lesbarkeit des Codes und erleichtert den Lesern das Verständnis. Außerdem bleibt die Syntaxhervorhebung in einigen Markdown-Editoren erhalten.

#### F: Was ist der Unterschied zwischen abgegrenztem und eingerücktem Code in Markdown?

A: Bei durch Trennzeichen getrenntem Code werden bestimmte Trennzeichen zum Einschließen des Codes verwendet, während bei eingerücktem Code jede Codezeile mit Leerzeichen oder Tabulatoren eingerückt wird.

#### F: Wird abgegrenzter Code in Markdown von allen Markdown-Editoren unterstützt?

A: Die Unterstützung für durch Trennzeichen getrennten Code in Markdown kann je nach Markdown-Editor unterschiedlich sein. Überprüfen Sie zur Sicherheit die spezifische Dokumentation Ihres Herausgebers.


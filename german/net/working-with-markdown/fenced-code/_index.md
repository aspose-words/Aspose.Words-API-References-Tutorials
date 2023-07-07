---
title: Eingezäunter Code
linktitle: Eingezäunter Code
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie die Funktion „Fenced Code“ mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/fenced-code/
---

In diesem Beispiel führen wir Sie durch die Verwendung der Funktion „Fenced Code“ mit Aspose.Words für .NET. Umzäunter Code wird verwendet, um Codeblöcke mit einer bestimmten Formatierung darzustellen.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Hinzufügen eines Stils für eingezäunten Code

 Wir werden mithilfe von einen benutzerdefinierten Stil für den eingezäunten Code hinzufügen`Styles.Add` Methode der`Document` Objekt. In diesem Beispiel erstellen wir einen Stil namens „FencedCode“ für den eingezäunten Code.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Schritt 3: Abgeschirmten Code ohne Informationen hinzufügen

Jetzt können wir mithilfe des benutzerdefinierten Stils „FencedCode“ einen eingezäunten Codeblock ohne Informationszeichenfolge hinzufügen.

```csharp
builder.Writeln("This is an fenced code");
```

## Schritt 4: Umzäunten Code mit Info-String hinzufügen

Wir können auch einen eingezäunten Codeblock mit einer Informationszeichenfolge hinzufügen, indem wir einen anderen benutzerdefinierten Stil verwenden. In diesem Beispiel erstellen wir einen Stil namens „FencedCode.C#“, um einen Block von C#-Code darzustellen.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Beispielquellcode für Fenced Code mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### FAQs

#### F: Was ist Trenncode in Markdown?

A: Durch Trennzeichen getrennter Code in Markdown ist eine Formatierungsmethode, die zum Anzeigen von Code in einem Markdown-Dokument verwendet wird. Es besteht darin, den Code mit bestimmten Trennzeichen zu umrahmen.

#### F: Was sind die Vorteile von durch Trennzeichen getrenntem Code in Markdown?

A: Durch Trennzeichen getrennter Code in Markdown verbessert die Lesbarkeit des Codes und erleichtert den Lesern das Verständnis. Es ermöglicht auch die Beibehaltung der Syntaxhervorhebung in einigen Markdown-Editoren.

#### F: Was ist der Unterschied zwischen durch Trennzeichen getrenntem und eingerücktem Code in Markdown?

A: Durch Trennzeichen getrennter Code verwendet bestimmte Trennzeichen, um den Code einzuschließen, während bei eingerücktem Code jede Codezeile mit Leerzeichen oder Tabulatoren eingerückt wird.

#### F: Wird durch Trennzeichen getrennter Code in Markdown von allen Markdown-Editoren unterstützt?

A: Die Unterstützung für durch Trennzeichen getrennten Code in Markdown kann je nach Markdown-Editor variieren. Überprüfen Sie zur Sicherheit die spezifische Dokumentation Ihres Herausgebers.


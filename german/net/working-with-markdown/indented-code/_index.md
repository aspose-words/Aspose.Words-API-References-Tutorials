---
title: Eingerückter Code
linktitle: Eingerückter Code
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie eingerückten Code mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/indented-code/
---

In diesem Beispiel erklären wir, wie Sie die Funktion für eingerückten Code mit Aspose.Words für .NET verwenden. Eingerückter Code wird verwendet, um Codeblöcke mit einer bestimmten Formatierung visuell darzustellen.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Stil für eingerückten Code hinzufügen

 Wir werden mithilfe von einen benutzerdefinierten Stil für den eingerückten Code hinzufügen`Styles.Add` Methode der`Document` Objekt. In diesem Beispiel erstellen wir einen Stil namens „IndentedCode“ für eingerückten Code.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Schritt 3: Eingerückten Code hinzufügen

Jetzt können wir einen eingerückten Codeblock mit dem benutzerdefinierten Stil „IndentedCode“ hinzufügen.

```csharp
builder.Writeln("This is an indented code block");
```

### Beispielquellcode für eingerückten Code mit Aspose.Words für .NET

```csharp
	// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
	DocumentBuilder builder = new DocumentBuilder();

	Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
	builder.ParagraphFormat.Style = indentedCode;
	builder.Writeln("This is an indented code");
            
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Funktion für eingerückten Code mit Aspose.Words für .NET verwenden.


---
title: Inline-Code
linktitle: Inline-Code
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Code mit Aspose.Words für .NET integrieren.
type: docs
weight: 10
url: /de/net/working-with-markdown/inline-code/
---

In diesem Beispiel führen wir Sie durch die Verwendung der Inline-Code-Funktion mit Aspose.Words für .NET. Inline-Code wird verwendet, um Codeteile innerhalb eines Absatzes visuell darzustellen.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Stil für Inline-Code hinzufügen

 Wir werden mithilfe von einen benutzerdefinierten Stil für den Inline-Code hinzufügen`Styles.Add` Methode der`Document` Objekt. In diesem Beispiel erstellen wir einen Stil namens „InlineCode“ für Inline-Code mit einem Standard-Backtick.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Schritt 3: Inline-Code hinzufügen

Jetzt können wir Inline-Code mit dem benutzerdefinierten Stil „InlineCode“ hinzufügen. In diesem Beispiel fügen wir zwei Textteile mit unterschiedlicher Anzahl an Backticks hinzu.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Beispielquellcode für Inline-Code mit Aspose.Words für .NET

```csharp
	// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
	DocumentBuilder builder = new DocumentBuilder();

	//Anzahl der Backticks fehlt, standardmäßig wird ein Backtick verwendet.
	Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
	builder.Font.Style = inlineCode1BackTicks;
	builder.Writeln("Text with InlineCode style with 1 backtick");

	// Es wird 3 Backticks geben.
	Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
	builder.Font.Style = inlineCode3BackTicks;
	builder.Writeln("Text with InlineCode style with 3 backtick");
            
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Inline-Code-Funktionalität mit Aspose.Words für .NET nutzen.


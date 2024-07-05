---
title: Eingerückter Code
linktitle: Eingerückter Code
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie eingerückten Code mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/indented-code/
---

In diesem Beispiel erklären wir, wie Sie die Funktion für eingerückten Code mit Aspose.Words für .NET verwenden. Eingerückter Code wird verwendet, um Codeblöcke mit bestimmter Formatierung visuell darzustellen.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Stil für eingerückten Code hinzufügen

Wir werden einen benutzerdefinierten Stil für den eingerückten Code hinzufügen, indem wir`Styles.Add` Methode der`Document` Objekt. In diesem Beispiel erstellen wir einen Stil namens „IndentedCode“ für eingerückten Code.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Schritt 3: Eingerückten Code hinzufügen

Jetzt können wir mit dem benutzerdefinierten Stil „IndentedCode“ einen eingerückten Codeblock hinzufügen.

```csharp
builder.Writeln("This is an indented code block");
```

### Beispielquellcode für eingerückten Code mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Funktion für eingerückten Code mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Was ist eingerückter Code in Markdown?

A: Eingerückter Code in Markdown ist eine Formatierungsmethode, die zum Anzeigen von Code in einem Markdown-Dokument verwendet wird. Dabei wird jede Codezeile mit Leerzeichen oder Tabulatoren eingerückt.

#### F: Wie verwende ich eingerückten Code in Markdown?

A: Um eingerückten Code in Markdown zu verwenden, rücken Sie jede Codezeile mit Leerzeichen oder Tabulatoren ein.

#### F: Was sind die Vorteile von eingerücktem Code in Markdown?

A: Eingerückter Code in Markdown verbessert die Lesbarkeit des Codes und erleichtert den Lesern das Verständnis.

#### F: Was ist der Unterschied zwischen eingerücktem Code und Codeblöcken in Markdown?

A: Eingerückter Code wird für kleine Codeschnipsel verwendet, die in den Text eingefügt werden, während Codeblöcke dazu dienen, größere Codeteile in separater Formatierung anzuzeigen.

#### F: Wird eingerückter Code in Markdown von allen Markdown-Editoren unterstützt?

A: Die Unterstützung für eingerückten Code in Markdown kann je nach Markdown-Editor unterschiedlich sein. Überprüfen Sie zur Sicherheit die spezifische Dokumentation Ihres Herausgebers.
---
title: Zitat
linktitle: Zitat
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie Zitate mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/quote/
---

In diesem Beispiel erklären wir, wie die Anführungszeichenfunktion mit Aspose.Words für .NET verwendet wird. Anführungszeichen werden verwendet, um Textabschnitte hervorzuheben, indem sie mit einem speziellen Rahmen umgeben werden.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Den Standard-Zitierstil verwenden

Wir verwenden den Standardabsatzstil „Zitat“, um dem Text eine Zitatformatierung zuzuweisen.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Schritt 3: Stile für verschachtelte Ebenen erstellen

 Wir können Stile für verschachtelte Ebenen erstellen mit dem`Styles.Add` Methode der`Document` Objekt. In diesem Beispiel erstellen wir einen Stil namens „Quote1“, um eine verschachtelte Zitatebene darzustellen.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Beispielquellcode für Zitate mit Aspose.Words für .NET


```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Standardmäßig speichert ein Dokument den Blockzitatstil für die erste Ebene.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Erstellen Sie Stile für verschachtelte Ebenen durch Stilvererbung.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Zitatfunktion mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Was ist ein Zitat in Markdown?

A: Ein Zitat in Markdown ist eine Möglichkeit, Textpassagen aus anderen Quellen hervorzuheben oder auf berühmte Zitate zu verweisen.

#### F: Wie verwende ich Anführungszeichen in Markdown?

A: Um ein Zitat in Markdown zu verwenden, schließen Sie den Text des Zitats in spitze Klammern ein (`>`). Jede Zeile des Zitats muss mit einem Winkel beginnen.

#### F: Unterstützt Markdown-Zitate Attribute?

A: Markdown-Zitate unterstützen keine speziellen Attribute. Sie werden einfach durch die Formatierung des zitierten Textes hervorgehoben.

#### F: Können Sie Zitate in Markdown einbetten?

A: Ja, es ist möglich, Anführungszeichen in Markdown zu verschachteln, indem man eine zusätzliche Ebene von spitzen Klammern hinzufügt (`>`).
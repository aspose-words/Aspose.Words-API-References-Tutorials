---
title: Schwerpunkte
linktitle: Schwerpunkte
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET Hervorhebungen (Fett und Kursiv) verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/emphases/
---

In diesem Beispiel erklären wir, wie Hervorhebungen mit Aspose.Words für .NET verwendet werden. Hervorhebungen werden verwendet, um bestimmte Teile des Textes hervorzuheben, beispielsweise Fettdruck und Kursivschrift.

## Schritt 1: Dokumentinitialisierung

 Zunächst initialisieren wir das Dokument, indem wir eine Instanz des`Document` Klasse.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Verwenden eines Dokumentgenerators

Als Nächstes verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Text mit Hervorhebungen hinzufügen

Wir können Hervorhebungen hinzufügen, indem wir die Schrifteigenschaften des Dokumentgenerators ändern. In diesem Beispiel verwenden wir Fett- und Kursivschrift, um verschiedene Teile des Textes hervorzuheben.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Schritt 4: Speichern des Dokuments

 Abschließend können wir das Dokument im gewünschten Format speichern. In diesem Beispiel verwenden wir das`.md` Erweiterung für ein Markdown-Format.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie Hervorhebungen mit Aspose.Words für .NET verwenden.

### Beispielquellcode für Hervorhebungen mit Aspose.Words für .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Häufig gestellte Fragen

#### F: Wie markiere ich Text mit Markdown?

A: Um Text mit Markdown hervorzuheben, umgeben Sie den Text einfach mit den entsprechenden Symbolen. Verwenden Sie`*` oder`_` für Kursivschrift,`**` oder`__` für mutig, und`~~` zum Durchstreichen.

#### F: Können wir verschiedene Hervorhebungen im selben Text kombinieren?

 A: Ja, es ist möglich, verschiedene Hervorhebungen im selben Text zu kombinieren. Sie können beispielsweise ein Wort fett und kursiv markieren, indem Sie beide`**`Und`*` um das Wort herum.

#### F: Welche Hervorhebungsoptionen sind in Markdown verfügbar?

A: Die in Markdown verfügbaren Hervorhebungsoptionen sind kursiv (`*` oder`_`), deutlich (`**` oder`__`) und durchgestrichen (`~~`).

#### F: Wie gehe ich mit Fällen um, in denen der Text Sonderzeichen enthält, die von Markdown zur Hervorhebung verwendet werden?

 A: Wenn Ihr Text Sonderzeichen enthält, die von Markdown zum Hervorheben verwendet werden, können Sie diese maskieren, indem Sie ihnen ein`\` . Zum Beispiel,`\*` wird ein wörtliches Sternchen angezeigt.

#### F: Können wir das Erscheinungsbild der Hervorhebung mit CSS anpassen?

A: Hervorhebungen in Markdown werden normalerweise mit den Standardstile des Browsers gerendert. Wenn Sie Ihr Markdown in HTML konvertieren, können Sie das Erscheinungsbild der Hervorhebungen mit CSS-Regeln anpassen.
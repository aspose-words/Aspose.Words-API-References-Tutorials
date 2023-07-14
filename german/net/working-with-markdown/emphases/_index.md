---
title: Schwerpunkte
linktitle: Schwerpunkte
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie Hervorhebungen (fett und kursiv) mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/emphases/
---

In diesem Beispiel erklären wir, wie Hervorhebungen mit Aspose.Words für .NET verwendet werden. Hervorhebungen werden verwendet, um bestimmte Teile des Textes hervorzuheben, z. B. Fett- und Kursivschrift.

## Schritt 1: Dokumentinitialisierung

 Zuerst initialisieren wir das Dokument, indem wir eine Instanz davon erstellen`Document` Klasse.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Schritt 2: Verwendung eines Dokumentengenerators

Als Nächstes verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 3: Fügen Sie Text mit Hervorhebungen hinzu

Wir können Text hervorheben, indem wir die Schriftarteigenschaften des Dokumentgenerators ändern. In diesem Beispiel verwenden wir Fett- und Kursivschrift, um verschiedene Textteile hervorzuheben.

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

 Abschließend können wir das Dokument im gewünschten Format speichern. In diesem Beispiel verwenden wir die`.md` Erweiterung für ein Markdown-Format.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie Hervorhebungen mit Aspose.Words für .NET verwenden.

### Beispielquellcode für Emphases mit Aspose.Words für .NET


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

### FAQs

#### F: Wie hebe ich Text mit Markdown hervor?

A: Um Text mithilfe von Markdown hervorzuheben, umgeben Sie den Text einfach mit den entsprechenden Symbolen. Verwenden`*` oder`_` für Kursivschrift,`**` oder`__` für fett, und`~~` zum Durchstreichen.

#### F: Können wir verschiedene Hervorhebungen im selben Text kombinieren?

 A: Ja, es ist möglich, verschiedene Hervorhebungen im selben Text zu kombinieren. Beispielsweise können Sie ein Wort fett und kursiv schreiben, indem Sie beides verwenden`**` Und`*` um das Wort herum.

#### F: Welche Hervorhebungsoptionen sind in Markdown verfügbar?

A: Die in Markdown verfügbaren Hervorhebungsoptionen sind kursiv (`*` oder`_`), deutlich (`**` oder`__`) und durchgestrichen (`~~`).

#### F: Wie gehe ich mit Fällen um, in denen der Text Sonderzeichen enthält, die Markdown zum Hervorheben verwendet?

 A: Wenn Ihr Text Sonderzeichen enthält, die Markdown zum Hervorheben verwendet, können Sie diese durch ein vorangestelltes a maskieren`\` . Zum Beispiel,`\*` wird ein buchstäbliches Sternchen angezeigt.

#### F: Können wir das Erscheinungsbild der Hervorhebung mithilfe von CSS anpassen?

A: Hervorhebungen in Markdown werden normalerweise mit den Standardstilen des Browsers gerendert. Wenn Sie Ihr Markdown in HTML konvertieren, können Sie das Erscheinungsbild der Hervorhebung mithilfe von CSS-Regeln anpassen.
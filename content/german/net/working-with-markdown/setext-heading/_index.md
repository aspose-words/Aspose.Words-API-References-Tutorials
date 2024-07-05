---
title: Setext-Überschrift
linktitle: Setext-Überschrift
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie Setext-Überschriften zum Formatieren Ihrer Dokumente mit Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-markdown/setext-heading/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie die Setext-Überschriftenfunktion mit Aspose.Words für .NET verwenden. Setext-Überschriften sind eine alternative Methode zum Formatieren von Titeln in Markdown-Dokumenten.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Verwenden des Setext-Überschriftenstils

Wir verwenden den standardmäßigen Absatzstil „Überschrift 1“, um in unserem Dokument eine Überschrift der Ebene 1 zu erstellen.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Schritt 3: Stile zurücksetzen

Wir setzen zuvor angewendete Schriftstile zurück, um unerwünschte Stilkombinationen zwischen Absätzen zu vermeiden.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Schritt 4: Anpassen der Setext-Überschriftenebenen

Wir können Setext-Überschriftenebenen anpassen, indem wir neue Absatzformate basierend auf vorhandenen Überschriftenformaten hinzufügen. In diesem Beispiel erstellen wir ein Format „SetextHeading1“ basierend auf dem Format „Heading 1“, um eine Überschrift der Ebene 1 im Setext-Format darzustellen.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Schritt 5: Speichern des Dokuments

Abschließend können wir das Dokument im gewünschten Format speichern.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Beispielquellcode für Setext-Titel mit Aspose.Words für .NET

```csharp
// Der Pfad zum Dokumentverzeichnis.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Setzen Sie die Stile aus dem vorherigen Absatz zurück, um Stile zwischen Absätzen nicht zu kombinieren.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Setzen Sie die Stile aus dem vorherigen Absatz zurück, um Stile zwischen Absätzen nicht zu kombinieren.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Die Setex-Überschriftenebene wird auf 2 zurückgesetzt, wenn der Basisabsatz eine Überschriftenebene größer als 2 hat.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### Häufig gestellte Fragen

#### F: Was ist ein Setext Markdown-Header?

A: Ein Setext Markdown-Header ist eine alternative Möglichkeit, Überschriften in einem Markdown-Dokument zu erstellen. Er verwendet Unterstriche (= oder -), um verschiedene Überschriftenebenen anzuzeigen.

#### F: Wie verwende ich Setext Markdown-Header?

A: Um Setext Markdown-Überschriften zu verwenden, platzieren Sie Unterstriche unter dem Titeltext. Verwenden Sie Gleichheitszeichen (=) für eine Überschrift der Ebene 1 und Bindestriche (-) für eine Überschrift der Ebene 2.

#### F: Gibt es Einschränkungen bei der Verwendung von Setext Markdown-Headern?

A: Setext Markdown-Überschriften unterliegen Einschränkungen hinsichtlich der Überschriftenhierarchie und sind optisch nicht so deutlich erkennbar wie Standard-Markdown-Überschriften.

#### F: Kann ich das Erscheinungsbild von Setext Markdown-Kopfzeilen anpassen?

A: In Standard-Markdown ist es nicht möglich, das Erscheinungsbild von Setext-Markdown-Headern anzupassen. Ihr Erscheinungsbild basiert auf den verwendeten Unterstrichen.

#### F: Werden Setext Markdown-Header von allen Markdown-Editoren unterstützt?

A: Die Unterstützung für Setext Markdown-Header kann je nach Markdown-Editor unterschiedlich sein. Überprüfen Sie zur Sicherheit die spezifische Dokumentation Ihres Herausgebers.
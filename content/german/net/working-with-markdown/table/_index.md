---
title: Tisch
linktitle: Tisch
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET eine Tabelle erstellen.
type: docs
weight: 10
url: /de/net/working-with-markdown/table/
---


In diesem Beispiel zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET eine Tabelle erstellen. Eine Tabelle ist eine Datenstruktur, die Informationen in Zeilen und Spalten organisiert.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Schritt 2: Zellen und Daten hinzufügen

 Wir fügen unserer Tabelle Zellen und Daten hinzu, indem wir`InsertCell` Methode und die`Writeln` Methode des Dokumentgenerators.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Beispielquellcode zum Erstellen einer Tabelle mit Aspose.Words für .NET

```csharp
// Verwenden Sie einen Dokument-Generator, um dem Dokument Inhalt hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Fügen Sie die erste Zeile hinzu.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// Fügen Sie die zweite Zeile hinzu.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET eine Tabelle erstellen.

### Häufig gestellte Fragen

#### F: Wie erstelle ich eine Tabelle in Markdown?

A: Um eine Tabelle in Markdown zu erstellen, verwenden Sie die Pipe-Syntax (`|`zum Abgrenzen von Zellen und Bindestrichen (`-`), um Tabellenüberschriften abzugrenzen.

#### F: Können wir das Erscheinungsbild einer Tabelle in Markdown anpassen?

A: In Standard-Markdown sind die Anpassungsoptionen für Tabellen begrenzt. Einige Markdown-Editoren ermöglichen es Ihnen jedoch, Tabellen CSS-Stile hinzuzufügen, um ihr Erscheinungsbild anzupassen.

#### F: Wie füge ich Zellen in einer Tabelle in Markdown zusammen?

A: Das Zusammenführen von Zellen in einer Tabelle in Markdown hängt vom verwendeten Markdown-Editor ab. Einige Markdown-Editoren unterstützen das Zusammenführen von Zellen mit einer bestimmten Syntax.

#### F: Unterstützen Tabellen in Markdown CSS-Styling?

A: In Standard-Markdown bieten Tabellen keine direkte Unterstützung für CSS-Stile. Einige Markdown-Editoren ermöglichen es Ihnen jedoch, Tabellen CSS-Stile hinzuzufügen, um ihr Erscheinungsbild anzupassen.

#### F: Können wir in Markdown Links oder Text im Inline-Format in die Zellen einer Tabelle einfügen?

A: Ja, Sie können mit der entsprechenden Markdown-Syntax Links oder Inline-Text zu Tabellenzellen in Markdown hinzufügen.
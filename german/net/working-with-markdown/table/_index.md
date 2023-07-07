---
title: Tisch
linktitle: Tisch
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET eine Tabelle erstellen.
type: docs
weight: 10
url: /de/net/working-with-markdown/table/
---


In diesem Beispiel zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET eine Tabelle erstellen. Eine Tabelle ist eine Datenstruktur, die Informationen in Zeilen und Spalten organisiert.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Schritt 2: Zellen und Daten hinzufügen

 Wir werden unserer Tabelle Zellen und Daten hinzufügen`InsertCell` Methode und die`Writeln` Methode des Dokumentengenerators.

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
// Verwenden Sie einen Dokumentersteller, um dem Dokument Inhalte hinzuzufügen.
DocumentBuilder builder = new DocumentBuilder();

// Fügen Sie die erste Zeile hinzu.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// Fügen Sie die zweite Reihe hinzu.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

Herzlichen Glückwunsch! Sie haben nun gelernt, wie Sie mit Aspose.Words für .NET eine Tabelle erstellen.

### FAQs

#### F: Wie erstelle ich eine Tabelle in Markdown?

A: Um eine Tabelle in Markdown zu erstellen, verwenden Sie die Syntax von Pipes (`|`), um Zellen und Bindestriche abzugrenzen (`-`), um Tabellenüberschriften abzugrenzen.

#### F: Können wir das Erscheinungsbild einer Tabelle in Markdown anpassen?

A: Im Standard-Markdown sind die Optionen zur Tabellenanpassung begrenzt. Bei einigen Markdown-Editoren können Sie jedoch CSS-Stile zu Tabellen hinzufügen, um deren Erscheinungsbild anzupassen.

#### F: Wie füge ich Zellen in einer Tabelle in Markdown zusammen?

A: Das Zusammenführen von Zellen in einer Tabelle in Markdown hängt vom verwendeten Markdown-Editor ab. Einige Markdown-Editoren unterstützen das Zusammenführen von Zellen mithilfe einer bestimmten Syntax.

#### F: Unterstützen Tabellen in Markdown CSS-Stil?

A: Im Standard-Markdown bieten Tabellen keine direkte Unterstützung für CSS-Stile. Bei einigen Markdown-Editoren können Sie jedoch CSS-Stile zu Tabellen hinzufügen, um deren Erscheinungsbild anzupassen.

#### F: Können wir in Markdown Links oder Text im Inline-Format in die Zellen einer Tabelle einfügen?

A: Ja, Sie können Tabellenzellen in Markdown mithilfe der entsprechenden Markdown-Syntax Links oder Inline-Text hinzufügen.
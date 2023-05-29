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

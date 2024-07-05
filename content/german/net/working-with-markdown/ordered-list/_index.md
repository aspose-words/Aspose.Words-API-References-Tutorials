---
title: Bestellliste
linktitle: Bestellliste
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in der Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Words für .NET geordnete Listen erstellen.
type: docs
weight: 10
url: /de/net/working-with-markdown/ordered-list/
---

In diesem Beispiel erklären wir, wie Sie die Funktion „Sortierte Liste“ mit Aspose.Words für .NET verwenden. Mit geordneten Listen können Sie Elemente sequenziell mit Zahlen organisieren.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um ein neues Dokument zu erstellen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Anwenden des geordneten Listenformats

 Wir wenden das geordnete Listenformat mithilfe des Dokumentgenerators an.`ApplyBulletDefault`Methode. Wir können das Nummerierungsformat auch anpassen, indem wir zu den Listenebenen gehen und das gewünschte Format festlegen.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Schritt 3: Elemente zur Liste hinzufügen

 Wir können Elemente zur Liste hinzufügen, indem wir den Dokumentgenerator verwenden`Writeln` Methode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Schritt 4: Liste einrücken

 Wir können die Liste einrücken, indem wir den Dokumentgenerator verwenden`ListIndent` Methode.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Schritt 5: Speichern des Dokuments

Abschließend können wir das Dokument im gewünschten Format speichern.

### Beispielquellcode für geordnete Liste mit Aspose.Words für .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie die Funktion „geordnete Liste“ mit Aspose.Words für .NET verwenden.


### Häufig gestellte Fragen

#### F: Wie erstelle ich eine geordnete Liste in Markdown?

A: Um eine geordnete Liste in Markdown zu erstellen, beginnen Sie jedes Listenelement mit einer Nummer, gefolgt von einem Punkt (`1.`, `2.`, `3.`), gefolgt von einem Leerzeichen.

#### F: Können wir geordnete Listen in Markdown verschachteln?

A: Ja, es ist möglich, geordnete Listen in Markdown zu verschachteln, indem Sie vor jedem verschachtelten Listenelement vier versetzte Leerzeichen hinzufügen.

#### F: Wie kann ich die Nummerierung geordneter Listen anpassen?

A: In Standard-Markdown wird die geordnete Listennummerierung automatisch generiert. Einige Markdown-Editoren ermöglichen jedoch die Anpassung mithilfe bestimmter Erweiterungen.

#### F: Unterstützen geordnete Listen in Markdown Einrückungen?

A: Ja, geordnete Listen in Markdown unterstützen Einrückungen. Sie können mit Leerzeichen oder Tabulatoren eine Linksverschiebung hinzufügen.

#### F: Können zu Listenelementen Links oder Inline-Text hinzugefügt werden?

A: Ja, Sie können mit der entsprechenden Markdown-Syntax Links oder Inline-Text zu Listenelementen hinzufügen.